# Configure blocked regions for domain names

This topic describes how to configure blocked regions \(domain names\) for protected websites on an Anti-DDoS Pro or Anti-DDoS Premium instance. After you configure blocked regions, access requests from IP addresses that reside within the blocked regions are blocked.

-   A website is added to Anti-DDoS Pro or Anti-DDoS Premium and is associated with an instance that uses the enhanced function plan. For more information, see [Add a website](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Use domains/Add a website.md).
-   Mitigation is enabled in the latest version of Anti-DDoS Pro or Anti-DDoS Premium.

If you configure an Anti-DDoS Pro or Anti-DDoS Premium instance to protect your websites and most requests are sent from regions inside China to your instance, you can block requests from regions outside China. You can also block other regions based on your requirements. To block regions, you only need to enable this feature and specify the regions that you want to block.

Precautions

-   This feature is supported only for websites. We recommend that you configure traffic block policies on the Protection for Infrastructure tab to protect non-website assets. For more information, see [Configure diversion from the origin server](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Protection settings/Protection for infrastructure/Configure diversion from the origin server.md) and [Configure blocked regions](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Protection settings/Protection for infrastructure/Configure blocked regions.md). Only Anti-DDoS Pro supports diversion from the origin server.
-   The specified blocked regions take effect only on domain names. If you want to block regions for individual domain names, you must specify the regions you want to block for each domain name separately.
-   This feature only identifies and filters requests from IP addresses that are in the blocked regions. It cannot reduce the volume of traffic.

1.  Log on to the [Anti-DDoS Pro console](https://yundun.console.aliyun.com/?p=ddoscoo).

2.  In the top navigation bar, select the region where your services are deployed.

    -   **Mainland China**: Anti-DDoS Pro
    -   **Outside Mainland China**: Anti-DDoS Premium
3.  In the left-side navigation pane, choose **Mitigation Settings** \> **General Policies**.

4.  On the **General Policies** page, click the **Protection for Website Services** tab. On the tab that appears, select the domain name that you want to configure from the left-side list.

5.  In the **Blocked Regions \(Domain Names\)** section, click **Change Settings**.

    ![Specify the regions that you want to block](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/0986328951/p69848.png)

6.  In the **Configure Blocked Regions** pane, select the regions that you want to block on the **China** or **Outside China** tabs and then click **OK**.

    ![Block region settings](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/5676420061/p143565.png)

7.  Go back to the **Blocked Regions \(Domain Names\)** section and turn on **Status** to apply the configuration.


After this feature is enabled, the configuration takes effect immediately on all Anti-DDoS Pro or Anti-DDoS Premium instances that are associated with the specified domain names.

