# Associate a website business with Anti-DDoS Premium for protection {#task1814 .task}

After purchasing an Anti-DDoS Premium instance, you can associate your website domain with the instance to protect against DDoS attacks.

**Note:** If you want to associate a non-website business, such as a game client, a mobile game, or an app with Anti-DDoS Premium, see [Add a non-website business to Anti-DDoS Premium for protection](reseller.en-US/Anti-DDoS Premium Service/Quick Start/Add a non-website business to Anti-DDoS Premium for protection.md#).

1.  Log on to the [Anti-DDoS Premium console](https://yundun.console.aliyun.com/?p=ddosdip).
2.  Go to the **Provisioning** \> **Website** page, and click **Add Website**.
3.  On the Website Configuration page that appears, set parameters for the website to be protected, and click **Add website**. 

    |Parameter|Configuration method|
    |---------|--------------------|
    |**Function Plan**|Select a function plan. Valid values:     -   Standard Function
    -   Enhanced Function
 |
    |**Instance**|Select an instance. Anti-DDoS Premium instances are displayed based on the specified **function plan**. **Note:** If no instances are displayed, instances that have the selected function plan are unavailable. You can choose to purchase an instance that has the enhanced function plan or upgrade an existing standard function instance.

 This instance is to be associated with the website domain. **Note:** A domain can be associated with a maximum of eight Anti-DDoS Premium instances that have the same function plan.

 |
    |**Website domain**|Set the domain of the website that you want to protect. **Note:** 

    -   You can set wildcard domains, such as `*.aliyun.com`. Anti-DDoS Premium automatically matches the subdomain of the wildcard domain.
    -   If you enter a wildcard domain and a specific domain, such as `*.aliyun.com` and `www.aliyun.com`, Anti-DDoS Premium will use the forwarding rules and protection policies of the specific domain whenever possible.
 |
    |**Protocol**|Select the protocols supported by the website. Valid values:     -   HTTP \(Selected by default\)
    -   HTTPS \(Selected by default\)
    -   Websocket
    -   Websockets
 **Note:** If your website supports HTTPS, you must select HTTPS. Select other protocols as needed.

 |
    |**Enable HTTP/2**|If your business supports HTTP/2, you can enable HTTP/2. **Note:** To enable HTTP/2 protection, the following requirements must be met:

    -   Your website has been associated with an Anti-DDos Premium instance of the enhanced function plan.
    -   You have selected **HTTPS**.
 |
    |**Origin server**|Select the address type of the origin server and specify the address. Supported address types are as follows:     -   **IP:** You can enter a maximum of 20 IP addresses of the origin server. When multiple origin server IP addresses are specified, Anti-DDoS Premium uses IP Hash load balancing to forward traffic back to the origin server.
    -   **Domain:** If you want to use Anti-DDoS Premium and WAF together for enhanced protection, you can select Domain and enter the CNAME record provided by your WAF instance.
 |
    |**Origin server ports**|Specify the server ports based on the protocols you have selected. **Note:** The forwarding port is the same as the port of the origin server.

     -   When **HTTP** or **Websocket** is selected, the port is set to 80 by default.
    -   When **HTTPS** or **Websockets** is selected, the port is set to 443 by default.

**Note:** The port for HTTP/2 is the same as the port for HTTPS.

 You can customize ports. Click **Custom** to specify available ports.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/188414/156436702345781_en-US.png)

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/188414/156436702345782_en-US.png)

    -   Instances that have the standard function plan: The port range is 80 or 8080 if you select HTTP or Websocket. The port range is 443 or 8443 if you select HTTPS or Websockets .
    -   Instances that have the enhanced function plan: The following figures show the available ports for HTTP and Websocket, and ports for HTTPS and Websockets in sequence.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/188414/156436702445783_en-US.png)

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/188414/156436702449775_en-US.png)

 |

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79670/156436702435231_en-US.png)

4.  Contact the DNS service provider of your website to modify the DNS record of the website domain. 

    Change the DNS record to the dedicated IP address of the Anti-DDoS Premium instance to redirect business traffic from your website to this instance.

    **Note:** If you want to verify whether the forwarding rule set for the Anti-DDoS Premium instance takes effect before business traffic redirection, click **Return to Website List**. After you verify that the forwarding rule works as expected, change the DNS record to redirect business traffic to the Anti-DDoS Premium instance.

    1.  Log on to the [Anti-DDoS Premium console](https://yundun.console.aliyun.com/?p=ddosdip). In the left-side navigation pane, click **Instance List**. On the page that appears, find the Anti-DDoS Premium instance that protects the website, and record the dedicated IP address of the instance.
    2.  Contact the DNS service provider of your website to modify the A record of the website domain to point to the dedicated IP address. 

        The configuration pages of different DNS service providers are different. The following figure is for reference only.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79670/156436702435255_en-US.png)

    3.  After the DNS configuration takes effect, all business traffic is redirected from your website to the Anti-DDoS Premium instance for protection. 

        **Note:** It takes about 10 minutes for the DNS configurations to take effect. We recommend that you change the DNS record during the off-peak hours.

5.  Configure origin server protection. For more information, see [Protect origin servers that use Anti-DDoS Pro](../reseller.en-US/Anti-DDoS Pro Service/Best Practice/Protect origin sites that use Anti-DDoS Pro.md#). 

    **Note:** DDoS attacks may send traffic that bypasses Anti-DDoS Premium to flood the origin server, which may throw the origin IP address into the black hole routing status. It can prevent your origin server against small-scale HTTP flood and Web attacks, but cannot prevent large-scale DDoS attacks.


