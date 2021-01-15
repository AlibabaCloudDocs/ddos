# Obtain the actual source IP addresses of requests

After you add a service to Anti-DDoS Pro or Anti-DDoS Premium, Anti-DDoS Pro or Anti-DDoS Premium scrubs and forwards service requests to the origin server. The source IP addresses of the requests are changed to the IP address of the Anti-DDoS Pro or Anti-DDoS Premium instance. This topic describes how to obtain the actual source IP addresses of requests.

## Non-website service provided by using a port

**Note:**

-   If your origin server is an Elastic Compute Service \(ECS\) instance that was created after October 2018, the source IP addresses that you obtain on the origin server are the actual source IP addresses of requests.
-   If your origin server is an ECS instance that was created before October 2018, you cannot directly obtain the actual source IP addresses of requests. Submit a [ticket](https://workorder-intl.console.aliyun.com/?#/ticket/add/?productId=80) to contact technical support.

For example, after you add a non-website service to Anti-DDoS Pro or Anti-DDoS Premium, Anti-DDoS Pro or Anti-DDoS Premium connects to the origin server by using a three-way handshake process. Anti-DDoS Pro or Anti-DDoS Premium sends the last ACK packet that contains the information, such as the source port number and IP address, in the TCP Option field. The size of the information is 6 bytes. The following figure shows the information in the ACK packet.

![TCP Option](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/8410860161/p183502.png)

The value of `Magic Number` indicates the source port number, which is a hexadecimal string. In this example, the source port number is `c4 06`. You can also obtain the source IP address, which is indicated by the next four bytes after the source port number. In this example, the source IP address is `65 ** ** 85`. Then, you can convert c4 06 and 65 \*\* \*\* 85 to decimal values to obtain the actual source port number and IP address. In this example, the actual source port number is 50182 and the actual source IP address is 101.\*\*\*.\*\*\*.133.

The methods that are used to obtain the actual source IP addresses of requests vary based on the network architecture of your service. For more information, see the following table.

|Network architecture|Description|
|--------------------|-----------|
|Anti-DDoS Pro or Anti-DDoS Premium + ECS instance|-   If service requests are forwarded by using a TCP port, the origin server can obtain the actual source IP addresses. You do not need to perform additional configuration.

You can configure security group rules for the ECS instance based on the source IP addresses. For example, you can allow or deny inbound traffic from a specific IP address.

-   If service requests are forwarded by using a UDP port, the origin server cannot obtain the actual source IP addresses. |
|Anti-DDoS Pro or Anti-DDoS Premium + SLB instance + ECS instance|-   If service requests are forwarded by using a TCP port, the origin server can obtain the actual source IP addresses. You do not need to perform additional configuration.

**Note:** You must add the back-to-origin IP addresses of Anti-DDoS Pro or Anti-DDoS Premium to the whitelist of the Server Load Balancer \(SLB\) instance. For more information, see [Allow back-to-origin IP addresses to access the origin server](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Allow back-to-origin IP addresses to access the origin server.md) and [Enable access control](/intl.en-US/Classic Load Balancer/User Guide/Access control/Enable access control.md).

-   If service requests are forwarded by using a UDP port, the origin server cannot obtain the actual source IP addresses.

**Note:** If the private IP address of the ECS instance is modified or the ownership of the ECS instance is transferred to you by another user, the origin server cannot obtain the actual source IP addresses. In this case, submit a [ticket](https://workorder-intl.console.aliyun.com/?#/ticket/add/?productId=80) to contact technical support. |
|Anti-DDoS Pro or Anti-DDoS Premium + Server that is not deployed on Alibaba Cloud|In some cases, the origin server can obtain the actual source IP addresses. For more information, see [Obtain the actual source IP addresses of requests to the origin server that is not deployed on Alibaba Cloud](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Best practices/Obtain the actual source IP addresses of requests to the origin server that is not
         deployed on Alibaba Cloud.md).|

## Website service provided by using a domain name

By default, if service requests are forwarded to the origin server by a Layer 7 proxy server, such as an Anti-DDoS Pro or Anti-DDoS Premium instance, the source IP addresses obtained by the origin server are the back-to-origin IP addresses of the Anti-DDoS Pro or Anti-DDoS Premium instance. The actual source IP addresses are recorded in the `X-Forwarded-For` field. The format is `X-Forwarded-For: Actual source IP address, Back-to-origin IP address of Anti-DDoS Pro or Anti-DDoS Premium`.

If the requests pass through more than one proxy server, for example, Web Application Firewall \(WAF\) and Alibaba Cloud CDN \(CDN\), the `X-Forwarded-For` field in the HTTP request header records the actual source IP addresses and the IP addresses of all proxy servers. The format is `X-Forwarded-For: Actual source IP address, IP address of proxy server 1, IP address of proxy server 2, IP address of proxy server 3, ...`.

A common web application server can use the `X-Forwarded-For` field to obtain the actual source IP addresses of requests.

You can use the following methods to obtain the `X-Forwarded-For` field in different programming languages:

-   ASP

    ```
    Request.ServerVariables("HTTP_X_FORWARDED_FOR")
    ```

-   ASP.NET \(C\#\)

    ```
    Request.ServerVariables["HTTP_X_FORWARDED_FOR"]
    ```

-   PHP

    ```
    `$_SERVER["HTTP_X_FORWARDED_FOR"]
    ```

-   JSP

    ```
    request.getHeader("HTTP_X_FORWARDED_FOR")
    ```


In the `X-Forwarded-For` field, the IP address before the first comma \(,\) is the actual source IP address of a request.

**Note:** For more information about how to obtain the actual source IP addresses in common web services, such as NGINX, IIS 6, IIS 7, Apache, and Tomcat, see [Retrieve actual IP addresses of clients](/intl.en-US/Website Access/Retrieve actual IP addresses of clients.md).

