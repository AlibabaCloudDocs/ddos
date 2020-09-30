---
keyword: [Anti-DDoS Origin, Enterprise edition, WAF, DDoS attacks, web attacks, HTTP flood attacks]
---

# Use Anti-DDoS Origin and WAF

This topic describes how to use Anti-DDoS Origin and Web Application Firewall \(WAF\) to provide protection. This solution protects your website against Layer 4 distributed denial of service \(DDoS\) attacks, Layer 7 web attacks, and HTTP flood attacks.

-   An Elastic Compute Service \(ECS\) instance is created and has web applications installed. The ECS instance has a public IP address, and your website has a domain name.

    **Note:** If your website provides services in mainland China, the domain name of your website must have an Internet Content Provider \(ICP\) license. Otherwise, you cannot add the domain name to WAF instances in mainland China to protect your website. For more information, see [ICP filing application overview]().

-   An Anti-DDoS Origin Enterprise instance is purchased. For more information, see [Purchase an Anti-DDoS Origin Enterprise instance](/intl.en-US/Anti-DDoS Origin User Guide/Purchase an Anti-DDoS Origin Enterprise instance.md).

    **Note:** When you purchase an Anti-DDoS Origin Enterprise instance, you must select a region. Make sure that the Anti-DDoS Origin Enterprise instance and the ECS instance reside in the same region.

-   A WAF instance is purchased. For more information, see [Purchase a WAF instance](/intl.en-US/Pricing/Subscription/Purchase a WAF instance.md).

You can use Anti-DDoS Origin Enterprise to mitigate DDoS attacks for your website. If your website encounters web attacks and HTTP flood attacks, we recommend that you use WAF to protect your website. For more information about WAF, see [What is Alibaba Cloud WAF?](/intl.en-US/Product Introduction/What is Alibaba Cloud WAF?.md).

If you use Anti-DDoS Origin Enterprise and WAF to protect your website, you must add your website to WAF and then add the IP address of the WAF instance to Anti-DDoS Origin Enterprise for protection. In this case, all service traffic is first scrubbed by WAF, and only normal traffic is forwarded to the origin server. Attack traffic, such as DDoS attacks, web attacks, and HTTP flood attacks, is blocked.

## Procedure

1.  Add your website to WAF.

    1.  Log on to the [WAF console](https://yundun.console.aliyun.com/?&p=wafnext).

    2.  In the top navigation bar, select the **Mainland China** or **International** region.

        WAF automatically determines the specific region based on the location of the origin server.

    3.  In the left-side navigation pane, choose **Asset Center** \> **Website Access**.

    4.  Click **Add Domain Name**.

        You can add your website in two modes: CNAME and transparent proxy. In CNAME mode, the website can be automatically or manually added. In transparent proxy mode, only origin servers that are deployed in the China \(Beijing\) region are supported.

        This topic describes how to add a website in CNAME mode. For more information about the mode for adding a website , see [Add domain names](/intl.en-US/Website Access/Website access with CNAME/Add domain names.md) and [Website access]().

    5.  On the **Add Domain Name** page, click **Manually Add Other Websites**. If the **Add Domain Name** page does not appear, skip this step.

    6.  Complete the configurations in the **Enter your website information** step of the **Add Domain Name** wizard and click **Next**.

        You must specify the following website parameters:

        -   **Domain Name**: Enter the domain name of the website.
        -   **Protocol Type**: Select the protocol supported by the website. If your website supports **HTTPS**, select HTTPS and upload the certificate after you add the website. For more information, see [Upload HTTPS certificates](/intl.en-US/Website Access/Website access with CNAME/Add domain names.md).
        -   **Destination Server \(IP Address\)**: Select **IP** and enter the public IP address of the ECS instance.
        -   **Destination Server Port**: After you specify Protocol Type, the server port is automatically matched. You can also specify a non-standard server port. For more information, see [Supported custom ports](/intl.en-US/Website Access/Supported custom ports.md).
        -   **Does a layer 7 proxy \(DDoS Protection/CDN, etc.\) exist in front of WAF**: Select **No**.

            If you configure a Layer 7 proxy such as Anti-DDoS Pro, Anti-DDoS Premium, or Content Delivery Network \(CDN\) before WAF, the requests from a client are forwarded to the Layer 7 proxy before they reach WAF. Anti-DDoS Origin Enterprise is not a Layer 7 proxy. In this case, select No.

        For more information about the website parameters, see [Add domain names](/intl.en-US/Website Access/Website access with CNAME/Add domain names.md).

    7.  Click **Completed. Return to the website list**.

        A CNAME record is created for the added website. You can obtain the CNAME record of WAF from the website list.

        ![CNAME record ](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/7801549951/p97144.png)

    8.  Run the `ping the CNAME record of WAF` command on your computer to obtain the IP address of the WAF instance.

2.  Configure your origin server to allow the back-to-origin Classless Inter-Domain Routing \(CIDR\) blocks of WAF.

    For more information, see [Allow access from WAF back-to-origin CIDR blocks](/intl.en-US/Website Access/Website access with CNAME/Allow access from WAF back-to-origin CIDR blocks.md).

3.  Change the DNS settings to resolve the domain name of the website to the CNAME record of WAF that you obtain in Step 1.

    For more information, see [Change the DNS settings](/intl.en-US/Website Access/Website access with CNAME/Change the DNS settings.md).

    After you change the DNS settings, all requests sent to your website are forwarded to WAF for traffic scrubbing. WAF blocks web attacks and HTTP flood attacks and only forwards normal traffic to the origin server.

    The WAF instance cannot mitigate volumetric DDoS attacks. If your service encounters volumetric DDoS attacks, the performance of the WAF instance deteriorates, which affects service forwarding. Therefore, you must use an Anti-DDoS Origin Enterprise with the WAF instance to protect your service from DDoS attacks.

4.  Add the IP address of the WAF instance to your Anti-DDoS Origin Enterprise instance for protection.

    For more information, see [Add a cloud service to Anti-DDoS Origin Enterprise for protection](/intl.en-US/Anti-DDoS Origin User Guide/Instances/Add a cloud service to Anti-DDoS Origin Enterprise for protection.md).

    After you add the IP address of the WAF instance, the Anti-DDoS Origin Enterprise instance provides [unlimited protection](/intl.en-US/DDoS Protection Guide/Terms.md). The Anti-DDoS Origin Enterprise instance automatically scrubs service traffic to mitigate DDoS attacks.


