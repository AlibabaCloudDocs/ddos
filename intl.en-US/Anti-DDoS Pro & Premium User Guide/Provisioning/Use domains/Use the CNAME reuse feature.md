# Use the CNAME reuse feature

If you want to add multiple domain names that are hosted by the same server to an Anti-DDoS Premium instance, we recommend that you apply for CNAME reuse. This feature allows you to configure the instance only once and map multiple domain names hosted by the same server to a CNAME. After CNAME reuse is enabled, you can modify the CNAME to map the domain names hosted by the same server to the CNAME assigned by Anti-DDoS Premium.

## Prerequisites

A [ticket](https://workorder-intl.console.aliyun.com/?#/ticket/add/?productId=80) is submitted to apply for CNAME reuse. In this topic, CNAME reuse is enabled.

**Note:** Only Anti-DDoS Premium supports CNAME reuse.

## Scenarios

CNAME reuse is suitable for the following scenarios:

-   Customers, such as agents, independent software vendors \(ISVs\), and distributors, want to add a large number of domain names to an Anti-DDoS Premium instance. Most of the domain names are hosted by the same server and the number of domain names frequently changes.
-   Multiple second-level domain names are required for the promotion and search engine optimization \(SEO\) of the same service.
-   Multiple alternative domain names are required for a service.

## Limits

The following table describes the limits of CNAME reuse.

|Item|Description|
|----|-----------|
|Protocol|HTTP and HTTPS are supported.|
|Origin server|The domain names that are mapped to the same CNAME must be hosted by the same origin server.|

## Enable CNAME reuse

You can use the CNAME reuse feature together with Sec-Traffic Manager. If you enable CNAME reuse, you can choose whether to use Sec-Traffic Manager. For more information about Sec-Traffic Manager, see [Overview](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Sec-Traffic Manager/Overview.md).

-   To use the CNAME reuse feature together with Sec-Traffic Manager, you must select a scheduling rule. Then, the CNAME configured in the scheduling rule is reused.
-   If you do not use Sec-Traffic Manager, the CNAME assigned by Anti-DDoS Premium is reused.

Configuration descriptions in this topic are based on the following assumptions:

-   The origin server has two IP addresses: 1.1.1.1 and 2.2.2.2.
-   IP address 1.1.1.1 hosts three domain names: a.test, b.test, and c.test.

The following procedure describes how to use the CNAME reuse feature to add multiple domain names, such as a.test, b.test, and c.test, that are hosted on the IP address 1.1.1.1 to an Anti-DDoS Premium instance.

1.  Enable CNAME reuse when you configure a website.

    1.  Log on to the [Anti-DDoS Premium console](https://yundun.console.aliyun.com/?p=ddoscoo).

    2.  In the top navigation bar, select **Outside Mainland China**.

    3.  In the left-side navigation pane, choose **Provisioning** \> **Website Config**.

    4.  Add a domain name and enable CNAME reuse, or enable this feature for an existing domain name. For more information about how to add a domain name, see [Add a website](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Use domains/Add a website.md).

        Assume that the IP address of the origin server is 1.1.1.1 and the domain name is a.test.

        ![Enable CNAME reuse for a domain name](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/4097449951/p65277.png)

2.  Specify whether to use Sec-Traffic Manager. Update the CNAME of the protected domain name.

    When you enable CNAME reuse, you must specify whether to use Sec-Traffic Manager.

    -   Enable CNAME reuse without Sec-Traffic Manager
        1.  In the Select Traffic Scheduling Rule dialog box, click **Without Sec-Traffic Manager** and then **OK**.

            ![Enable CNAME reuse without Sec-Traffic Manager](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/3705078061/p65278.png)

        2.  After a domain name is added, note the CNAME assigned for the domain name.
        3.  Go to the DNS provider that has the protected domain name and update the DNS records for all the domain names \(a.test, b.test, and c.test\) that are hosted on the IP address 1.1.1.1. Use the obtained CNAME to enable CNAME reuse.
    -   Enable CNAME reuse with Sec-Traffic Manager
        1.  In the Select Traffic Scheduling Rule dialog box, click **With Sec-Traffic Manager**, specify a Sec-Traffic Manager rule, and then click **OK**.

            ![Enable CNAME reuse with Sec-Traffic Manager](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/3705078061/p65279.png)

            If you enable CNAME reuse with Sec-Traffic Manager, the Sec-Traffic Manager rule must be associated with the IP address of the origin server and the IP address of the Anti-DDoS Premium instance used in the website configuration. The IP address of the origin server is 1.1.1.1 in this example. If no rules are available, click **Create Sec-Traffic Manager Rule** to create a rule.

            **Note:** The IP address of the Anti-DDoS Premium instance in the Sec-Traffic Manager rule must be the same as that used in the website configuration.

            ![Sec-Traffic Manager rule](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/5097449951/p65248.png)

        2.  After you specify a Sec-Traffic Manager rule, note the CNAME of the rule.

            ![CNAME reuse](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/5097449951/p65286.png)

        3.  Go to the DNS provider that has the protected domain name and update the DNS records of all the domain names \(a.test, b.test, and c.test\) that are hosted on the IP address 1.1.1.1. Use the obtained CNAME to enable CNAME reuse.
3.  To add domain names that are hosted on another IP address of the origin server \(2.2.2.2\), repeat Step 1 and Step 2.


## Disable CNAME reuse

You can disable CNAME reuse on the Website Config page.

**Note:** Before you disable this feature, make sure that the service traffic of all the domain names mapped to the CNAME is no longer rerouted to your Anti-DDoS Premium instance. Otherwise, the inbound traffic cannot be forwarded to the origin server.

1.  Log on to the [Anti-DDoS Pro console](https://yundun.console.aliyun.com/?p=ddoscoo).

2.  In the top navigation bar, select **Outside Mainland China**.

3.  In the left-side navigation pane, choose **Provisioning** \> **Website Config**.

4.  Find the required domain and disable CNAME reuse.

5.  Specify whether to retain the website configuration and the Sec-Traffic Manager rule.

    -   If you retain the website configuration, the traffic forwarding rules still take effect.
    -   If you retain the Sec-Traffic Manager rule, Sec-Traffic Manager still takes effect.

