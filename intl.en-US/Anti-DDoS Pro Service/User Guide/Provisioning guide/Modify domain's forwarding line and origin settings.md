# Modify domain's forwarding line and origin settings {#concept_70457_zh .concept}

Generally, each Anti-DDoS Pro instance has at least one Anti-DDoS Pro ISP line, and you may have multiple Anti-DDoS Pro instances under your Alibaba Cloud account. Therefore, you may have multiple available Anti-DDoS Pro ISP lines.

When you configure a domain to be protected by an Anti-DDoS Pro instance, at least one Anti-DDoS Pro ISP line and an origin site is set in the forwarding line.

However, in practice, you may change the domain’s forwarding line and origin settings in Anti-DDoS Pro according to your business.

For example, you can change the domain’s forwarding line and origin settings to fulfill the following requirements:

-   Add Anti-DDoS Pro lines in a domain’s forwarding line. For example, add a China Unicom forwarding line for one domain that has only one China Telecom forwarding line.
-   Make all requests from China Unicom to be forwarded by the Anti-DDoS Pro China Unicom line, to avoid latency due to requests being forwarded by other Anti-DDoS Pro ISP lines.
-   Make requests from China Unicom to be forwarded by multiple Anti-DDoS Pro China Unicom lines. Then, request flow can be assigned to multiple Anti-DDoS Pro lines evenly.

## Prerequisites {#section_l9f_3o2_c5g .section}

Your domain must already be configured to be protected by Anti-DDoS Pro instances.

**Note:** If your domain has not been configured in Anti-DDoS Pro, see [Set up HTTP protection for web service](reseller.en-US/Anti-DDoS Pro Service/Quick Start/Web service/Step 1. Set up HTTP protection.md#) or [Set up HTTPS protection for web service](reseller.en-US/Anti-DDoS Pro Service/Quick Start/Web service/(Optional) Step 1: Set up HTTPS protection.md#) to configure your domain to be protected by existing Anti-DDoS Pro instance.

To change the domain’s forwarding line and origin settings in Anti-DDoS Pro, follow these steps:

**Note:** We recommend that you get familiar with the procedure by using test domains before you change the settings for your business domains. Additionally, we recommend that you change the settings during low demand periods.

1.  Log on to the [Anti-DDoS Pro console](https://partners-intl.console.aliyun.com/#/ddospro), and go to **Access** \> **Web Service**.
2.  Locate the domain, and click **Origin Edit** under the **Domain Info** area to open the Origin Edit webpage.

    **Note:** You can also click **Edit** under the **Instance & ISP Line** area of the domain, to open the Origin Edit webpage.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79540/156592537434932_en-US.png)

3.  Change the domain’s forwarding line and origin settings according to your requirements.
    -   Add a forwarding line
        1.  Click **Add Forwarding Line**, to add a new forwarding line for the domain.

            For example, add a China Unicom forwarding line on the basis of the existing China Telecom forwarding line.

        2.  In the Add Forwarding Line dialog box, select **Mode** and enter the origin site information, and then click **Next**.
        3.  Choose unoccupied Anti-DDoS Pro lines, and click **ON**.

            **Note:** You can choose multiple Anti-DDoS Pro lines.

            **Note:** In the Add Forwarding Line dialog box, all Anti-DDoS Pro ISP lines that have the same ISP with the forwarding lines that are configured for the domain are grayed out and displayed as occupied. For example, if the domain has a China Unicom forwarding line configured, all Anti-DDoS Pro China Unicom lines are displayed as occupied. You can change the Anti-DDoS Pro lines for an ISP that has a forwarding line configured by using the **Edit IP** functionality. For more information, see the Edit IP section.

        4.  Click **OK**, and the new forwarding line is displayed in the Origin Edit webpage.
    -   Edit Anti-DDoS Pro IP
        1.  Locate a forwarding line, click **Edit IP** to change the Anti-DDoS Pro lines for the forwarding line.
            -   Enable Anti-DDoS Pro IP: In the Edit IP dialog box, choose an Anti-DDoS Pro IP and click **ON**.

                **Note:** You can enable multiple Anti-DDoS Pro IPs for one forwarding line, and then requests can be assigned to multiple Anti-DDoS Pro IPs evenly.

            -   Remove Anti-DDoS Pro IP: In the Edit IP dialog box, choose an Anti-DDoS Pro IP and click **remove**.

                **Note:** If the **remove** button of an Anti-DDoS Pro IP is grayed out, the Anti-DDoS Pro IP has been used and the resolution switch is turned on in the forwarding line.

                If you have to remove this Anti-DDoS IP, turn off the resolution switch of the Anti-DDoS Pro IP in the Origin Edit webpage, and then remove the Anti-DDoS Pro IP in the Edit IP dialog box.

    -   Edit origin IP
        1.  Locate a forwarding line, click **Edit Origin IP** to change the origin site information.
        2.  In the Edit Origin IP dialog box, select **Mode** and enter the origin site information, and then click **OK**.

            **Note:** The origin site information modification takes five minutes to take effect.

    -   Delete a forwarding line

        Locate a forwarding line, click **Delete** to delete the forwarding line. After you delete the forwarding line, Anti-DDoS Pro ISP lines that have the same ISP with the forwarding line are no longer occupied in the Add Forwarding Line dialog box.

        **Note:** If the forwarding line is the last forwarding line of the domain, you cannot delete this line.


