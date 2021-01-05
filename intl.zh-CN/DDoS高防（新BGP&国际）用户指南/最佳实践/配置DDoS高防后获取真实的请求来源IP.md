# 配置DDoS高防后获取真实的请求来源IP

Web业务部署DDoS高防后，到达源站的所有业务流量都由DDoS高防转发，请求来源IP默认是DDoS高防实例的IP地址。本文介绍了这种情况下如何获取真实的请求来源IP。

## 配置端口接入的业务（非网站防护）

**说明：**

-   2018年10月后创建的ECS实例，默认支持获取真实的请求来源IP，即在源站ECS服务器上看到的请求来源IP就是真实的访问源IP。
-   2018年10月前创建的ECS实例，默认情况下无法获取真实的请求来源IP，您需要提交[工单](https://workorder-intl.console.aliyun.com/?#/ticket/add/?productId=80)申请开通相关配置。

业务四层端口接入后，高防节点和源站经过三次握手，在最后一个ACK数据包的TCP Option中插入了源端口号和源IP等信息，共占6个字节。具体位置如下图所示。

![TCP Option](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/1493965061/p183502.png)

其中，`Magic Number`表示端口号（使用十六进制表示，示例中为`c4 06`），通过端口号可以定位到IP地址信息（端口号后的连续四个字节，示例中为`65 ** ** 85`）。通过十六进制转为十进制，可以获得对应的端口号和IP地址（示例中端口为50182，源IP地址为101.\*\*\*.\*\*\*.133）。

根据业务的网络架构不同，获取真实请求来源IP的方式也不同，具体请参见下表说明。

|网络架构|说明|
|----|--|
|DDoS高防-\>阿里云ECS|-   通过TCP端口转发流量的情况，默认支持获取真实的请求来源IP，无需您做任何改动。源站服务器上看到的请求来源IP就是真实的访问源IP。

您可以基于请求来源IP设置ECS的安全组策略，例如放行或拒绝指定IP的入方向流量。

-   如果您使用UDP端口转发，则ECS源站不支持获取真实的请求来源IP。 |
|DDoS高防-\>负载均衡SLB-\>阿里云ECS|-   通过TCP端口转发流量的情况，默认支持获取真实的请求来源IP，无需您做任何改动。源站服务器上看到的请求来源IP就是真实的访问源IP。

**说明：** 您必须将DDoS高防的回源IP添加到负载均衡SLB的访问控制白名单中。更多信息，请参见[放行DDoS高防回源IP](/intl.zh-CN/DDoS高防（新BGP&国际）用户指南/接入DDoS高防/放行DDoS高防回源IP.md)、[开启访问控制](/intl.zh-CN/传统型负载均衡CLB/用户指南/访问控制/开启访问控制.md)。

-   如果您使用UDP端口转发，则ECS源站不支持获取真实的请求来源IP。

**说明：** 如果您修改了ECS的私网IP地址或者进行过ECS过户，则不支持获取真实的请求来源IP。遇到这种情况，请您提交[工单](https://workorder-intl.console.aliyun.com/?#/ticket/add/?productId=80)联系我们协助解决。 |
|DDoS高防-\>非阿里云ECS服务器|部分情况下支持获取真实的请求来源IP。更多信息，请参见[云外主机获取真实请求来源IP](/intl.zh-CN/DDoS高防（新BGP&国际）用户指南/最佳实践/云外主机获取真实请求来源IP.md)。|

## 配置域名接入的业务（网站防护）

当七层代理服务器（例如DDoS高防）将用户的访问请求转发到后端服务器时，源站看到的请求来源默认是七层代理服务器（例如DDoS高防）的回源IP，而真实的请求来源IP被记录在HTTP头部的`X-Forwarded-For`字段中，格式为`X-Forwarded-For: 用户真实IP, 高防代理IP`。

如果访问请求到后端服务器间经过了一台以上代理服务器（例如经过WAF、CDN等代理服务器），则HTTP头部的`X-Forwarded-For`字段记录了真实的请求来源IP和所有经过的代理服务器IP，格式为`X-Forwarded-For: 用户真实IP, 代理服务器1-IP, 代理服务器2-IP, 代理服务器3-IP, …`。

因此，常见的Web应用服务器都可以通过`X-Forwarded-For`字段的内容获取真实的请求来源IP。

针对不同的编程语言，常用的获取`X-Forwarded-For`内容的方式如下：

-   ASP

    ```
    Request.ServerVariables(“HTTP_X_FORWARDED_FOR”)
    ```

-   ASP.NET（C\#）

    ```
    Request.ServerVariables[“HTTP_X_FORWARDED_FOR”]
    ```

-   PHP

    ```
    `$_SERVER[“HTTP_X_FORWARDED_FOR”]
    ```

-   JSP

    ```
    request.getHeader(“HTTP_X_FORWARDED_FOR”)
    ```


获取到`X-Forwarded-For`字段的内容后，以英文逗号（,）作为分隔符，截取其中的第一个IP地址，即可获取真实的请求来源IP。

**说明：** 关于常见Web服务器（例如Nginx、IIS 6、IIS 7、Apache、Tomcat）获取真实访问IP的具体配置方法，请参见[获取客户端真实IP](/intl.zh-CN/接入WAF/获取客户端真实IP.md)。

