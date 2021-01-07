# Change the CNAME record to redirect traffic to Sec-Traffic Manager

After you use Sec-Traffic Manager to create a scheduling rule for a domain name, you must change the CNAME record of the domain name to redirect traffic to Sec-Traffic Manager. The rule takes effect only after you change the CNAME record. This topic describes how to change the CNAME record of a domain name to redirect traffic to Sec-Traffic Manager. In this example, the DNS resolution service is provided by Alibaba Cloud DNS.

A scheduling rule is added by using Sec-Traffic Manager. For more information, see [Overview](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Sec-Traffic Manager/Overview.md).

After you add a scheduling rule by using Sec-Traffic Manager, Sec-Traffic Manager generates a CNAME. To redirect inbound traffic to Sec-Traffic Manager, you must change the CNAME record of the domain name of the website to map the domain name to the CNAME that is assigned by Sec-Traffic Manager.

In the following example, your domain name is hosted on [Alibaba Cloud DNS](https://www.alibabacloud.com/product/dns).

If you use a third-party DNS service, log on to the system of the DNS provider to change the DNS records. The following example is only for reference.

Assume that the domain name that is specified in the scheduling rule is `bgp.ddostest.com`. The following procedure describes how to change and add DNS records in the Alibaba Cloud DNS console.

1.  Log on to the [Alibaba Cloud DNS console](https://dns.console.aliyun.com).

2.  On the Manage DNS page, find the domain name `ddostest.com` and click **Configure** in the Actions column.

3.  On the DNS Settings page, find the A or CNAME record whose Host is **bgp** and click **Edit** in the Actions column.

    **Note:** If you cannot find the DNS record that you want to manage in the list, you can click **Add Record** to add the record.

4.  In the Edit Record or Add Record panel, set the **Type** parameter to **CNAME** and the **Value** parameter to the CNAME that is assigned by Sec-Traffic Manager.

    To query the CNAME, log on to the [Anti-DDoS Pro](https://yundun.console.aliyun.com/?p=ddoscoo) console and choose **Provisioning** \> **Sec-Traffic Manager**.

5.  Click **Confirm** and wait for the settings to take effect.

6.  Check whether the website is accessible.

    If an exception occurs during website access, see [How do I handle the issues of slow response, high latency, and access failure on websites that are protected by an Anti-DDoS Pro or Anti-DDoS Premium instance?]().


