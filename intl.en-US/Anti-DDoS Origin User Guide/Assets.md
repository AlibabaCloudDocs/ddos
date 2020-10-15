# Assets

Anti-DDoS Origin Basic is enabled by default. It provides a protection capacity of up to 5 Gbit/s for Elastic Compute Service \(ECS\) instances, Server Load Balancer \(SLB\) instances, and elastic IP addresses \(EIPs\) under your Alibaba Cloud account. Protection against distributed denial of service \(DDoS\) attacks for the preceding assets is provided free of charge. The Assets page shows a list of assets that belong to an Alibaba Cloud account and their protection status and traffic trends. These assets include ECS instances, SLB instances, and EIPs. The information allows you to obtain an overview of security risks from DDoS attacks for your assets. You can use the information to improve protection for an asset.

1.  Log on to the [Alibaba Cloud Anti-DDoS Basic console](https://yundun.console.aliyun.com/?p=ddosnext).

2.  On the top of the Assets page, select a region.

3.  On the Assets page, view **information about protection against DDoS attacks**.

    ![DDoS Attack Protection Information](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/9118858951/p72752.png)

    In the **DDoS Attack Protection Information** section, you can perform the following operations:

    -   Click **Default Basic Protection Threshold** to view default black hole triggering thresholds for different assets that reside in each region.
    -   Click **Blackholing** to view Alibaba Cloud black hole policies.
    -   Click **Anti-DDoS Origin** to go to the **Manage Instances** page. You can purchase Anti-DDoS Origin instances as needed. For more information, see [Purchase an Anti-DDoS Origin Enterprise instance](/intl.en-US/Anti-DDoS Origin User Guide/Purchase an Anti-DDoS Origin Enterprise instance.md).
4.  Click the **ECS**, **SLB**, **EIP \(including NAT\)**, or **Others** tab based on the type of cloud service that you want to protect.

    **Note:** The **Others** tab shows all the on-demand Anti-DDoS Origin instances under your account. On-demand instances can protect servers in on-premises data centers outside China and cloud assets based on CIDR blocks. You can manually enable or disable protection in the console or by calling API operations. For more information, see [Enable traffic rerouting to an on-demand instance](/intl.en-US/Anti-DDoS Origin User Guide/Enable traffic rerouting to an on-demand instance.md) and [ModifyOnDemaondDefenseStatus](/intl.en-US/API reference/Anti-DDoS Origin/API reference (2017-11-20)/On-demand instances/ModifyOnDemaondDefenseStatus.md).

5.  In a list of assets, view the protection status of each asset.

    The Assets page lists all assets in a region and provides further details about protection against DDoS attacks for each asset. The details include **Status**, **Protection Capacity**, and **Cleaning Trigger Value**.

    -   **Status** indicates the security state of an instance. Available states include **Normal**, **Cleaning**, and **Black Hole Activated**.
        -   If an instance is in the Cleaning state, you can cancel traffic scrubbing. For more information, see [Cancel traffic cleaning](/intl.en-US/Anti-DDoS Origin User Guide/Cleaning settings/Cancel traffic cleaning.md).
        -   If an instance is in the Black Hole Activated state, you can view the black hole events. For more information, see [View the time when a black hole is enabled for an instance and the reason for enabling the black hole](/intl.en-US/Anti-DDoS Origin User Guide/Black hole policies/View the time when a black hole is enabled for an instance and the reason for enabling the black hole.md).
    -   **Protection Capacity** indicates the capacity of an instance to protect against DDoS attacks. This capacity means the maximum bandwidth of DDoS attacks that can be defended against. If the bandwidth that DDoS attacks consume exceeds the protection capacity of an instance, a black hole is triggered, and all packets that are routed to the instance are dropped. For more information about how to improve the protection capacity of an instance, see Step 6.
    -   **Cleaning Trigger Value** indicates the minimum bandwidth that must be reached before traffic scrubbing is triggered. The bandwidth is measured in Mbit/s and packets per second \(PPS\). For more information, see [Configure a cleaning threshold](/intl.en-US/Anti-DDoS Origin User Guide/Cleaning settings/Configure a cleaning threshold.md).
6.  Improve the protection capacity of a specific asset.

    -   Enable Anti-DDoS Origin

        If you have purchased an Anti-DDoS Origin Enterprise instance in the current region, you can perform the following operations to enable Anti-DDoS Origin for a specific asset.

        Anti-DDoS Origin Enterprise instances provide an account-level DDoS mitigation service for your assets and business to mitigate DDoS attack risks on the cloud. Enterprises can safeguard their large businesses at controllable costs, without the need to change the business architecture or increase latency. For more information, see [What is Anti-DDoS Origin?](/intl.en-US/Product Introduction on Alibaba DDoS Protection/Anti-DDoS Origin/What is Anti-DDoS Origin.md)

        The procedure used to configure Anti-DDoS Origin for different types of assets \(ECS, SLB, and EIP\) is similar. The following procedure describes how to enable Anti-DDoS Origin for an ECS instance. You can use this example as a reference for other types of assets.

        1.  Select the ECS instance for which you want to enable Anti-DDoS Origin from the ECS instance list and click **Add Anti-DDoS Origin**.

            ![Enable Anti-DDoS Origin](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/9118858951/p72717.png)

        2.  In the Anti-DDoS Origin instance list, find the required instance and click **Add** in the Operation column.

            ![Anti-DDoS Origin instance list](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/9118858951/p72719.png)

        3.  In the OK message, click **OK**.

            ![Confirmation](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/9118858951/p72720.png)

    -   Activate Anti-DDoS Pro or Anti-DDoS Premium.

        If your business faces high risks of DDoS attacks, we recommend that you activate Anti-DDoS Pro or Anti-DDoS Premium. For example, if your business experiences frequent DDoS attacks, volumetric DDoS attacks, or DDoS attacks have severely affected your business, you can activate Anti-DDoS Pro or Anti-DDoS Premium.

        Anti-DDoS Pro and Anti-DDoS Premium provide 8-line bandwidth resources of the Border Gateway Protocol \(BGP\) type at the Tbit/s level. The bandwidth resources are exclusive for mainland China. This allows you to defend against a huge number of DDoS attacks.

        In the left-side navigation pane, choose **Anti-DDoS Services** \> **Anti-DDoS Pro** or **Anti-DDoS Premium** to go to the related console.

        -   Anti-DDoS Pro is ideal for businesses that are deployed in mainland China.
        -   Anti-DDoS Premium is ideal for businesses that are deployed outside mainland China.

