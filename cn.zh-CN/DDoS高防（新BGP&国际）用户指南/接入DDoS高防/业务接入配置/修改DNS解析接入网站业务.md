# 修改DNS解析接入网站业务

在DDoS高防添加网站配置后，您必须将网站域名的DNS解析记录修改为高防CNAME地址或IP，才能使您用户访问网站的流量切换到DDoS高防实例进行防护。本文以网站域名解析托管在阿里云云解析DNS（免费版）为例，介绍了手动修改域名解析（CNAME或A记录）以接入DDoS高防的操作方法。

-   网站已接入DDoS高防。更多信息，请参见[添加网站](/cn.zh-CN/DDoS高防（新BGP&国际）用户指南/接入DDoS高防/域名接入/添加网站.md)。
-   源站服务器已放行DDoS高防回源IP。如果您的源站服务器上部署了非阿里云安全软件（例如，第三方防火墙），请将DDoS高防的回源IP地址加入安全软件的白名单，避免DDoS高防的回源流量被源站服务器上的安全软件误拦截。更多信息，请参见[放行DDoS高防回源IP](/cn.zh-CN/DDoS高防（新BGP&国际）用户指南/接入DDoS高防/放行DDoS高防回源IP.md)。
-   验证转发配置生效。强烈建议您在切换网站访问流量前，在本地验证DDoS高防实例的业务转发配置已经生效。更多信息，请参见[本地验证转发配置生效](/cn.zh-CN/DDoS高防（新BGP&国际）用户指南/接入DDoS高防/域名接入/本地验证转发配置生效.md)。

    **警告：** 如果转发配置未生效就执行业务切换，将可能导致业务中断。


## 接入方式说明

手动修改DNS解析接入网站业务时，您可以选择将网站域名的解析指向高防CNAME地址或关联高防IP（网站域名的高防CNAME地址和关联高防IP地址均可在[DDoS高防控制台](https://yundun.console.aliyun.com/?p=ddoscoo)的**接入管理** \> **域名接入**页面查询）。

![cname](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/7741919951/p68206.png)

接入方式的区别如下：

-   使用CNAME解析接入DDoS高防，只需完成一次解析修改，即使后续网站的关联高防IP发生变化，无需重新修改解析，DDoS高防将通过CNAME自动完成调度。在网站关联多个高防IP时，DDoS高防自动在多IP间切换流量。
-   使用A记录解析接入，则当网站的关联高防IP发生变化时，您必须重新修改解析。在网站关联多个高防IP时，您必须手动在多IP间切换流量。

我们推荐您使用CNAME方式接入，仅在CNAME解析不被支持或与别的记录存在冲突时，再选择A记录方式接入。

## 操作步骤

以下操作描述建立在您的域名DNS托管在[阿里云云解析DNS](https://wanwang.aliyun.com/domain/dns)。

**说明：** 云解析DNS是阿里云提供的域名解析服务，支持免费的公共DNS服务和付费版增值服务。如果您的域名已开通付费版云解析DNS服务，我们推荐您使用NS接入（即自动修改DNS）的方式接入DDoS高防。更多信息，请参见[NS方式接入网站业务](/cn.zh-CN/DDoS高防（新BGP&国际）用户指南/接入DDoS高防/业务接入配置/NS方式接入网站业务.md)。

如果您使用其他DNS服务商的域名解析服务，请登录服务商系统修改网站域名的解析记录，下文内容仅供参考。

假设在DDoS高防控制台已添加网站的域名为`bgp.gftest.top`。以下操作示例描述了在云解析DNS控制台修改、新增域名解析的步骤。

1.  登录[阿里云云解析DNS控制台](https://dns.console.aliyun.com)。

2.  在域名解析页面，定位到要操作的域名（本示例中为`gftest.top`），单击其操作列下的**解析设置**。

    ![解析设置](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/0707947061/p45866.png)

3.  在解析设置页面，定位到要修改的解析记录（本示例中对应主机记录为**bgp**的A记录或CNAME记录），单击其操作列下的**修改**。

    **说明：** 如果要操作的解析记录不在记录列表中，您可以单击**添加记录**。

    ![修改记录](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/0707947061/p45867.png)

4.  在修改记录（或添加记录）页面，选择一种接入方式，修改解析记录。

    -   （推荐）CNAME解析接入：选择**记录类型**为**CNAME**，并将**记录值**修改为域名对应的DDoS高防CNAME地址。

        **说明：** 您可以在[DDoS高防控制台](https://yundun.console.aliyun.com/?p=ddoscoo)的**接入管理** \> **域名接入**页面查询域名对应的DDoS高防CNAME地址。

        ![修改记录](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/0707947061/p45868.png)

    -   A记录解析接入：选择**记录类型**为**A**，并将**记录值**修改为域名的关联高防IP。

        **说明：** 您可以在[DDoS高防控制台](https://yundun.console.aliyun.com/?p=ddoscoo)的**接入管理** \> **域名接入**页面查询域名的关联高防IP。

        ![a记录](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/6017947061/p67888.png)

5.  单击**确认**，等待修改后的解析设置生效。

6.  使用浏览器测试网站访问是否正常。

    如果网站访问出现异常，请参见[业务接入高防后存在卡顿、延迟、访问不通等问题]()。


## 相关操作

业务接入DDoS高防后，您可以根据需要完成以下任务：

-   启用流量调度器，设置DDoS高防与云资源间的联动规则，仅在特定场景下触发并切换启用DDoS高防。更多信息，请参见[概述](/cn.zh-CN/DDoS高防（新BGP&国际）用户指南/接入DDoS高防/流量调度器/概述.md)。
-   更换源站ECS公网IP。如果您的源站IP不慎暴露，攻击者有可能绕过高防直接攻击源站，这种情况下，您可以通过DDoS高防更换后端ECS的IP。更多信息，请参见[更换源站ECS公网IP](/cn.zh-CN/DDoS高防（新BGP&国际）用户指南/接入DDoS高防/更换源站ECS公网IP.md)。

