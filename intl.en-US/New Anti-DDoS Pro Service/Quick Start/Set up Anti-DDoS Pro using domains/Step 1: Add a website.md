# Step 1: Add a website {#task_221010 .task}

After you buy an Anti-DDoS Pro instance, you must add your website in the Anti-DDoS Pro console. To set up an Anti-DDoS Pro instance to protect your service, you need to enter your domain information in the Anti-DDoS Pro console.

You have purchased an Anti-DDoS Pro instance. To view your instance, go to the **Management** \> **Instances** page. For more information about purchasing Anti-DDoS Pro instances, see[Buy Anti-DDoS Pro instances](reseller.en-US/New Anti-DDoS Pro Service/Pricing/Buy Anti-DDoS Pro instances.md#).

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/188414/156159950945786_en-US.png)

1.   Log on to the [Anti-DDoS Pro console](https://partners-yundunnext.console.aliyun.com/?p=ddoscoo#/domain). 
2.   In the left-side navigation pane, select **Management** \> **Websites**. 
3.   On the Websites page, click **Add Domain**.![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/188414/156159950945721_en-US.png)

  
4.   On the Add Domain page, complete the configuration under the **Enter Site Information** tab. The configuration details are as follows: 

    |Item|Description|
    |----|-----------|
    | **Protection Package** |The type of Anti-DDoS Pro instance that you want to assocaite with the domain. Valid values:     -   Standard
    -   Enhanced
 |
    | **Instance** |Available instances are listed based on the specified **Protection Package**. **Note:** If no instance is displayed, it means you have no instance under the specified Protection Package. We recommend that you buy an Enhanced instance or upgrade the existing Standard intance to the Enhanced type.

 Select one or more instacnes to associate with the domain. **Note:** You can associate a domain with a maximum of eight Anti-DDoS Pro instances. Besides, these instances must under the same Protection Package.

 |
    | **Domain** |The domain of the website that you want to protect. **Note:** 

    -   Supports wildcard domains, such as `*.aliyun.com`. Anti-DDoS Pro automatically matches all subdomains for the wildcard domain.
    -   If you enter a wildcard domain and a specific domain name, such as `*.aliyun.com` and `www.aliyun.com`, Anti-DDoS Pro will use the redirection rules and protections policies of the specific domain name.
 |
    | **Protocol** |The protocols supported by your website. Valid values:     -   HTTP \(Selected by default\)
    -   HTTPS \(Selected by default\)
    -   Websocket
    -   Websockets
 **Note:** If your website supports HTTPS encrypted connections, you must select HTTPS. Select other protocols if applicable.

 |
    | **Server Address** |Select the address type of the origin server and specify the address. Supported address types are as follows:     -    **Origin Server IP**: You can enter up to 20 IP addresses of the origin server. When multiple origin server IPs are specified, Anti-DDoS Pro uses IP hash load balancing to forward traffic back to the origin server.
    -    **Origin Server Domain**: If you want to use Anti-DDoS Pro and WAF together for enhanced protection, you can select Origin Server Domain and enter the CNAME provided by your WAF instance.
 |
    | **Origin server ports** |The server ports are automatically assigned based on the protocols you have selected. **Note:** The forwarding port is the same as the port of the origin server.

     -   When **HTTP** or **Websocket** is selected, the port is set to 80 by default.
    -   When **HTTPS** or **Websockets** is selected, the port is set to 443 by default.
 Anti-DDoS Pro allows you to specify custom ports. You can click **Custom** to select ports other than the default ones.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/188414/156159951045781_en-US.png)

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/188414/156159951045782_en-US.png)

    -   Standard instance: The optional HTTP/Websocket ports are 80 and 8080. The optional HTTPS/Websockets ports are 443 and 8443.
    -   Enhanced instance: The optional HTTP/Websocket and HTTPS/Websockets ports are described in the following figures.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/188414/156159951045783_en-US.png)

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/188414/156159951049775_en-US.png)

 |

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/188414/156159951045722_en-US.png)

5.   Click **Add**. 

After a domain is added, you are automatically directed to the **Modify DNS Records** page. You can click **Back** to go to the Websites page and view the newly added domain information.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/188414/156159951145724_en-US.png)

Anti-DDoS Pro automatically **associates each domain with an Anti-DDoS Pro instance IP address**. You need to change the A record value of your domain to the Anti-DDoS Pro instance IP address. The incoming traffic to your site is then forwarded to your Ant-DDoS Pro Instance.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/188414/156159951145725_en-US.png)

-    [Step 2: Change DNS records](reseller.en-US/New Anti-DDoS Pro Service/Quick Start/Set up Anti-DDoS Pro using domains/Step 2: Change DNS records.md#) 
-    [Upload SSL certificates](reseller.en-US/New Anti-DDoS Pro Service/User Guide/Upload SSL certificates.md#): If your website supports the HTTPS protocol, you must upload your SSL certificate to enable Anti-DDoS Pro to filter HTTPS requests.

