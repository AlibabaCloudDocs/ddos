# Step 2: Configure service traffic forwarding

After you add a website to an Anti-DDoS Pro or Anti-DDoS Premium instance, you must modify the DNS records of the domain name for the website to reroute the traffic directed to your website to the instance. The instance scrubs the traffic and forwards normal traffic to the origin server. This topic describes how to modify the CNAME record of a domain name. In this example, the DNS resolution service is provided by Alibaba Cloud DNS.

-   A domain name is added to an Anti-DDoS Pro or Anti-DDoS Premium instance. For more information, see [Step 1: Add forwarding rules](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Quick Start/Set up Anti-DDoS Pro using domains/Step 1: Add forwarding rules.md).
-   The back-to-origin IP addresses of the Anti-DDoS Pro or Anti-DDoS Premium instance are added to the whitelist of the origin server. If you deploy third-party security software, such as a firewall, on your origin server, add the back-to-origin IP addresses to the whitelist of the security software. For more information, see [Allow back-to-origin IP addresses to access the origin server](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Allow back-to-origin IP addresses to access the origin server.md).
-   The traffic forwarding settings are in effect. Before you switch service traffic to the Anti-DDoS Pro or Anti-DDoS Premium instance, we recommend that you use your local computer to verify that the instance can forward traffic to the origin server. For more information, see [Verify the forwarding configuration on your local machine](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Use domains/Verify the forwarding configuration on your local machine.md).

    **Warning:** If you switch your service traffic to the Anti-DDoS Pro or Anti-DDoS Premium instance before the forwarding settings take effect, your service may be interrupted.


In the following example, your domain name is hosted on [Alibaba Cloud DNS](https://www.alibabacloud.com/product/dns).

**Note:** Alibaba Cloud DNS provides basic DNS services free of charge. It also offers other value-added services in the paid editions. If you activated a paid edition of Alibaba Cloud DNS for your website, we recommend that you enable NS Mode Access to redirect traffic to Anti-DDoS Pro or Anti-DDoS Premium. For more information, see [Enable NS Mode Access to protect a website](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Provisioning settings/Enable NS Mode Access to protect a website.md).

If you use a third-party DNS service, log on to the system of the DNS provider to change the DNS records. The following example is only for reference.

Assume that you add the domain name `bgp.ddostest.com` to Anti-DDoS Pro or Anti-DDoS Premium. The following procedure describes how to change and add DNS records in the Alibaba Cloud DNS console.

1.  Log on to the [Alibaba Cloud DNS console](https://dns.console.aliyun.com).

2.  On the Manage DNS page, find the domain name `ddostest.com` and click **Configure** in the Actions column.

3.  On the DNS Settings page, find the A or CNAME record whose Host is **bgp** and click **Edit** in the Actions column.

    **Note:** If you cannot find the DNS record that you want to manage in the list, you can click **Add Record** to add the record.

4.  In the Edit Record or Add Record dialog box, set **Type** to **CNAME** and change **Value** to the CNAME assigned by Anti-DDoS Pro or Anti-DDoS Premium.

5.  Click **Confirm** and wait for the settings to take effect.


[Step 3: Configure protection policies](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Quick Start/Set up Anti-DDoS Pro using domains/Step 3: Configure protection policies.md)

