# Change DNS records to protect website services

After you add a website to Anti-DDoS Pro or Anti-DDoS Premium, you must change the DNS records to map the domain name of the website to a CNAME that is assigned by Anti-DDoS Pro or Anti-DDoS Premium or to the IP address of an Anti-DDoS Pro or Anti-DDoS Premium instance. This way, the traffic that is destined for the website is redirected to Anti-DDoS Pro or Anti-DDoS Premium for protection. This topic describes how to change the DNS records of a website. DNS records can be CNAME or A records. In this example, the DNS resolution service is provided by the free edition of Alibaba Cloud DNS.

-   A website is added to Anti-DDoS Pro or Anti-DDoS Premium. For more information, see [Add a website](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Use domains/Add a website.md).
-   The back-to-origin IP addresses of the Anti-DDoS Pro or Anti-DDoS Premium instance are added to the whitelist of the origin server. If you deploy third-party security software, such as a firewall, on your origin server, add the back-to-origin IP addresses to the whitelist of the security software. For more information, see [Allow back-to-origin IP addresses to access the origin server](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Allow back-to-origin IP addresses to access the origin server.md).
-   The traffic forwarding settings are in effect. Before you switch service traffic to the Anti-DDoS Pro or Anti-DDoS Premium instance, we recommend that you use your local computer to verify that the instance can forward traffic to the origin server. For more information, see [Verify the forwarding configuration on your local machine](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Use domains/Verify the forwarding configuration on your local machine.md).

    **Warning:** If you switch your service traffic to the Anti-DDoS Pro or Anti-DDoS Premium instance before the forwarding settings take effect, your service may be interrupted.


## Access methods

When you change the DNS records, you can map the domain name of the website to a CNAME that is assigned by Anti-DDoS Pro or Anti-DDoS Premium or to the IP address of the Anti-DDoS Pro or Anti-DDoS Premium instance. To obtain the two addresses, you can log on to the [Anti-DDoS Pro](https://yundun.console.aliyun.com/?p=ddoscoo) console and choose **Provisioning** \> **Website Config**.

![cname](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/5197449951/p68206.png)

The following list describes the differences between the access methods that use the CNAME record and the A record:

-   If you use the CNAME record, you need to change DNS records only once. If the IP address of the Anti-DDoS Pro or Anti-DDoS Premium instance changes, the instance automatically redirects traffic based on the CNAME record. If your website is associated with multiple instances, Anti-DDoS Pro or Anti-DDoS Premium automatically schedules traffic to these instances.
-   If you use the A record, you must change DNS records each time the IP address of the instance changes. If your website is associated with multiple instances, you must manually schedule traffic to these instances.

We recommend that you use the CNAME record. You can use the A record only if the CNAME record is unavailable or conflicts with other DNS records.

## Procedure

In the following example, your domain name is hosted on [Alibaba Cloud DNS](https://www.alibabacloud.com/product/dns).

**Note:** Alibaba Cloud DNS provides basic DNS services free of charge. It also offers other value-added services in the paid editions. If you activated a paid edition of Alibaba Cloud DNS for your website, we recommend that you enable NS Mode Access to redirect traffic to Anti-DDoS Pro or Anti-DDoS Premium. For more information, see [Enable NS Mode Access to protect a website](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Provisioning settings/Enable NS Mode Access to protect a website.md).

If you use a third-party DNS service, log on to the system of the DNS provider to change the DNS records. The following example is only for reference.

Assume that you add the domain name `bgp.ddostest.com` to Anti-DDoS Pro or Anti-DDoS Premium. The following procedure describes how to change and add DNS records in the Alibaba Cloud DNS console.

1.  Log on to the [Alibaba Cloud DNS console](https://dns.console.aliyun.com).

2.  On the Manage DNS page, find the domain name `ddostest.com` and click **Configure** in the Actions column.

3.  On the DNS Settings page, find the A or CNAME record whose Host is **bgp** and click **Edit** in the Actions column.

    **Note:** If you cannot find the DNS record that you want to manage in the list, you can click **Add Record** to add the record.

4.  In the Add Record or Edit Record panel, select a record type and change the record.

    -   CNAME record: Set the **Type** parameter to **CNAME** and the **Value** parameter to the CNAME that is assigned by Anti-DDoS Pro or Anti-DDoS Premium for the domain name. This record type is recommended.

        **Note:** To obtain the CNAME, log on to the [Anti-DDoS Pro](https://yundun.console.aliyun.com/?p=ddoscoo) console and choose **Provisioning** \> **Website Config**.

    -   A record: Set the **Type** parameter to **A** and the **Value** parameter to the IP address of the Anti-DDoS Pro or Anti-DDoS Premium instance with which the domain name is associated.

        **Note:** To obtain the IP address, log on to the [Anti-DDoS Pro](https://yundun.console.aliyun.com/?p=ddoscoo) console and choose **Provisioning** \> **Website Config**.

5.  Click **Confirm** and wait for the settings to take effect.

6.  Check whether the website is accessible.

    If an exception occurs during website access, see [How do I handle the issues of slow response, high latency, and access failure on websites that are protected by an Anti-DDoS Pro or Anti-DDoS Premium instance?]().


## References

After you add your website to Anti-DDoS Pro or Anti-DDoS Premium, you can perform the following operations:

-   Enable Sec-Traffic Manager and configure scheduling rules between Anti-DDoS Pro or Anti-DDoS Premium and protected cloud resources. These rules trigger Anti-DDoS Pro or Anti-DDoS Premium only in specific scenarios. For more information, see [Overview](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Sec-Traffic Manager/Overview.md).
-   Change the public IP address of the Elastic Compute Service \(ECS\) instance where your origin server resides. If the IP address of your origin server is exposed, attackers may bypass Anti-DDoS Pro or Anti-DDoS Premium to attack the origin server. To protect against this type of attack, you can change the IP address of the ECS origin server in the Anti-DDoS Pro or Anti-DDoS Premium console. For more information, see [Change the public IP address of an ECS origin server](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Change the public IP address of an ECS origin server.md).

