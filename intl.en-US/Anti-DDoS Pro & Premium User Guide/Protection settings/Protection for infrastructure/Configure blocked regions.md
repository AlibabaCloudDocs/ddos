# Configure blocked regions

This topic describes how to configure and enable the Blocked Regions policy. This policy allows you to block requests initiated from IP addresses in specific regions \(regions inside and outside China\) for an Anti-DDoS Pro or Anti-DDoS Premium instance. Anti-DDoS Pro or Anti-DDoS Premium instances that use the enhanced function plan support this policy. After you enable this policy, requests from the specified regions to access Anti-DDoS Pro or Anti-DDoS Premium instances are dropped.

An Anti-DDoS Pro or Anti-DDoS Premium instance that uses the enhanced function plan is available. For more information, see [Purchase mitigation plans for Anti-DDoS Pro and Anti-DDoS Premium](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Purchase mitigation plans for Anti-DDoS Pro and Anti-DDoS Premium.md).

**Note:** In the top navigation bar of the Anti-DDoS Pro or Anti-DDoS Premium console, you can select the **Mainland China** or **Outside Mainland China** region to switch between the Anti-DDoS Pro and Anti-DDoS Premium consoles. Then, you can configure and manage Anti-DDoS Pro or Anti-DDoS Premium instances as required. Make sure that you select the required region when you use Anti-DDoS Pro or Anti-DDoS Premium.

This policy directly drops requests initiated from IP addresses in specific regions \(regions inside and outside China\) to block the sources of requests. If most requests are sent from regions inside China that include Hong Kong S.A.R, Macao S.A.R, and Taiwan to an Anti-DDoS Pro or Anti-DDoS Premium instance, deny requests from regions outside China.

**Note:** This policy takes effect on Anti-DDoS Pro or Anti-DDoS Premium instances. You must configure this policy separately for each Anti-DDoS Pro or Anti-DDoS Premium instance.

Blocked Regions and Diversion from Origin Server

The Blocked Regions policy blocks requests from specific regions in scrubbing centers. This policy drops blocked requests near the destination servers. Anti-DDoS Pro or Anti-DDoS Premium instances identify and filter requests based on the region of the source IP addresses. This policy cannot reduce the volume of attack traffic. Therefore, it is suitable for blocking attacks that consume system resources.

The Diversion from Origin Server policy drops requests from specific regions based on the attack source by using core routers on the network provided by an ISP. For more information, see [Configure diversion from the origin server](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Protection settings/Protection for infrastructure/Configure diversion from the origin server.md).

**Note:** The Diversion from Origin Server policy is available only for Anti-DDoS Pro.

Blocked Regions and Blocked Regions \(Domain Names\)

The Blocked Regions policy configured for Anti-DDoS Pro or Anti-DDoS Premium instances has a higher priority than the Blocked Regions \(Domain Names\) policy when they are used together.

For example, if you have enabled Blocked Regions for an Anti-DDoS Pro or Anti-DDoS Premium instance to block requests from regions outside China, users outside China cannot access domain names associated with this instance regardless of whether Blocked Regions \(Domain Names\) is enabled for the domain names. If you want to block regions outside China for some services, we recommend that you configure blocked regions for domain names rather than Anti-DDoS Pro or Anti-DDoS Premium instances. For more information, see [Configure blocked regions for domain names](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Protection settings/Protection for website services/Configure blocked regions for domain names.md).

1.  Log on to the [Anti-DDoS Pro console](https://yundun.console.aliyun.com/?p=ddoscoo).

2.  In the top navigation bar, select the region where your instance resides.

    -   **Mainland China**: If you select this region, the **Anti-DDoS Pro console** appears.
    -   **Outside Mainland China**: If you select this region, the **Anti-DDoS Premium console** appears.
    You can switch the region to configure and manage Anti-DDoS Pro or Anti-DDoS Premium instances. Make sure that you select the required region when you use Anti-DDoS Pro or Anti-DDoS Premium.

3.  In the left-side navigation pane, choose **Mitigation Settings** \> **General Policies**.

4.  On the **Protection for Infrastructure** tab, select the target instance from the list on the left side.

    **Note:** You can also search for instances by instance ID or description.

5.  In the **Blocked Regions** section, click **Change Settings**.

    ![Blocked Regions](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/4297449951/p72957.png)

6.  In the Configure Blocked Regions pane, select the regions that you want to block and then click **OK**.

7.  Go back to the **Blocked Regions** section and turn on **Status** to apply the settings.


