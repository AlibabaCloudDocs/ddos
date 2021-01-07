# Change the CNAME record to redirect traffic to Sec-Traffic Manager

After you use Sec-Traffic Manager to create a scheduling rule for a domain name, you must change the CNAME record of the domain name to redirect traffic to Sec-Traffic Manager. The rule takes effect only after you change the CNAME record. This topic describes how to change the CNAME record of a domain name to redirect traffic to Sec-Traffic Manager. In this example, the DNS resolution service is provided by Alibaba Cloud DNS.

A scheduling rule is added by using Sec-Traffic Manager. For more information, see [Overview](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Sec-Traffic Manager/Overview.md).

After you add a scheduling rule by using Sec-Traffic Manager, Sec-Traffic Manager generates a CNAME. To redirect inbound traffic to Sec-Traffic Manager, you must change the CNAME record of the domain name of the website to map the domain name to the CNAME that is assigned by Sec-Traffic Manager.

In the following example, the domain name is managed by [Alibaba Cloud DNS](https://www.alibabacloud.com/product/dns).

If you use third-party DNS services, log on to the system of the DNS provider to modify the DNS records. The following example is for reference only.

Assume that the domain name that is specified in the scheduling rule is `bgp.gftest.top`. The following procedure describes how to change and add DNS records in the Alibaba Cloud DNS console.

1.  Log on to the [Alibaba Cloud DNS console](https://dns.console.aliyun.com).

2.  On the Manage DNS page, find the domain name `ddostest.com` and click **Configure** in the Actions column.

    ![DNS records](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9197449951/p45866.png)

3.  On the DNS Settings page, find the A record or CNAME record whose Host is **bgp** and click **Edit** in the Actions column.

    **Note:** If you cannot find the DNS record that you want to manage in the list, you can click **Add Record** to add the record.

    ![Modify the record](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9197449951/p45867.png)

4.  In the Edit Record or Add Record panel, set the **Type** parameter to **CNAME** and the **Value** parameter to the CNAME that is assigned by Sec-Traffic Manager.

    ![Change the DNS record](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9197449951/p45868.png)

    To query the CNAME, log on to the [Anti-DDoS Pro](https://yundun.console.aliyun.com/?p=ddoscoo) console and choose **Provisioning** \> **Sec-Traffic Manager**.

    ![General](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9197449951/p89082.png)

5.  Click **OK** and wait for the settings to take effect.

6.  Check whether the website can be accessed.


