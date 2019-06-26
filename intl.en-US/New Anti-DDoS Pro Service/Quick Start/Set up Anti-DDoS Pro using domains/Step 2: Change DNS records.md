# Step 2: Change DNS records {#task_221012 .task}

This topic describes how to change A records in the Alibaba Cloud DNS console to forward incoming traffic to your site to your Anti-DDoS Pro instance.

Make sure to complete the following tasks before you change DNS records.

-   You have added your website in the Anti-DDoS Pro console. For more information, see [Step 1: Add a website](reseller.en-US/New Anti-DDoS Pro Service/Quick Start/Set up Anti-DDoS Pro using domains/Step 1: Add a website.md#).
-   If you are using additional firewalls to protect your origin server, disable the firewalls or add the back-to-origin IP addresses used by your Anti-DDoS Pro instance to the whitelist. For more information, see [Add Anti-DDoS Pro back-to-origin CIDR blocks to the whitelist](reseller.en-US/New Anti-DDoS Pro Service/User Guide/Add Anti-DDoS Pro back-to-origin CIDR blocks to the whitelist.md#).

    After the incoming traffic to your site is forwarded to the IP address of your Anti-DDoS Pro instance, the instance scrubs your traffic and uses the back-to-origin IP addresses to forward normal traffic back to your origin server. Therefore, if the back-to-origin IP addresses used by your Anti-DDoS Pro instance are not added to the whitelist of your firewall, normal traffic to your site may be blocked by mistake, making your website inaccessible.

-   Verify that your forwarding configuration works as expected. Before you change DNS records to forward incoming traffic to Anti-DDoS Pro, we recommend that you verify that your Anti-DDoS Pro instance can forward traffic back to the origin server. For more information, see [Verify forwarding configurations](../../../../reseller.en-US/Anti-DDoS Pro Service/Quick Start/Web service/Step 3. Verify local settings.md#).

The following example assumes that your domain is managed by Alibaba Cloud DNS. If you are using other domain name resolution services, log on to the DNS server and change the A record value of your domain to the IP addresses of your Anti-DDoS Pro instance.

**Note:** Alibaba Cloud provides free and paid versions of Alibaba Cloud DNS. If your domain is managed under a paid version of Alibaba Cloud DNS, we recommend that you use NS records to set up your Anti-DDoS Pro instance. For more information, see [Use NS records to set up Anti-DDoS Pro](reseller.en-US/New Anti-DDoS Pro Service/User Guide/Use NS records to set up Anti-DDoS Pro.md#).

Assume that you added the following domain in step 1: `bgp.ddostest.com`. The following example describes how to change or add A records in the Alibaba Cloud DNS console.

1.   Log on to the [Alibaba Cloud DNS console](https://dns.console.aliyun.com) [Alibaba Cloud DNS console](https://partners-dns.console.aliyun.com). 
2.   On the Manage DNS page, select domain `doctest.com`, and click **Configure** in the Actions column.![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/188415/156154088945866_en-US.png)

  
3.   On the DNS Settings page, select the A record whose host is **bpg**, and click **Edit** in the Actions column. 

    **Note:** If you cannot find the A record in the list, you can click **Add Record**.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/188415/156154088945867_en-US.png)

4.   On the Edit Record or Add Record dialog box, change the **Value** to the IP address of your Anti-DDoS Pro instance. 

    **Note:** After you add a domain in the Anti-DDoS Pro console, the domain is automatically associated with an Anti-DDoS Pro instance. To view the IP address of the Anti-DDoS Pro instance associated with your domain, go to the [Anti-DDoS Pro console](https://yundunnext.console.aliyun.com/?p=ddoscoo) [Anti-DDoS Pro console](https://partners-yundunnext.console.aliyun.com/?p=ddoscoo) and select **Management** \> **Websites**. For more information, see [Step 1: Add a website](reseller.en-US/New Anti-DDoS Pro Service/Quick Start/Set up Anti-DDoS Pro using domains/Step 1: Add a website.md#).

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/188415/156154088945904_en-US.png)

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/188415/156154088945868_en-US.png)

5.   Click **OK** and wait for the configuration to take effect. 

 [Step 3: Configure DDoS protection policies](reseller.en-US/New Anti-DDoS Pro Service/Quick Start/Set up Anti-DDoS Pro using domains/Step 3: Configure DDoS protection policies.md#) 

