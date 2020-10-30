# Assets

Anti-DDoS Origin Basic is enabled by default. It provides a protection capacity of up to 5 Gbit/s for Elastic Compute Service \(ECS\) instances, Server Load Balancer \(SLB\) instances, and elastic IP addresses \(EIPs\) under your Alibaba Cloud account. Protection against distributed denial of service \(DDoS\) attacks for the preceding assets is provided free of charge. The Assets page shows the assets that belong to an Alibaba Cloud account and their protection status along with traffic trends. These assets include ECS instances, SLB instances, and EIPs. The information allows you to obtain an overview of the security risks from DDoS attacks on your assets. You can also use the information to improve protection of your assets.

1.  Log on to the [Alibaba Cloud Anti-DDoS Basic console](https://yundun.console.aliyun.com/?p=ddosnext).

2.  On the top of the Assets page, select a region.

3.  On the Assets page, view protection information in the **DDoS Attack Protection Information** section.

    ![DDoS Attack Protection Information](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/9118858951/p72752.png)

    In the **DDoS Attack Protection Information** section, you can perform the following operations:

    -   Click **Default Basic Protection Threshold** to view default blackhole triggering thresholds for different assets that reside in each region.
    -   Click **Blackholing** to view the blackhole filtering policy of Alibaba Cloud.
    -   Click **Anti-DDoS Origin** to go to the **Manage Instances** page. You can purchase Anti-DDoS Origin instances as needed. For more information, see [Purchase an Anti-DDoS Origin Enterprise instance](/intl.en-US/Anti-DDoS Origin User Guide/Purchase an Anti-DDoS Origin Enterprise instance.md).
4.  Click the **ECS**, **SLB**, **EIP \(including NAT\)**, or **Others** tab based on the type of cloud services that you want to protect.

    **Note:** The **Others** tab shows all the on-demand Anti-DDoS Origin instances under your account. On-demand instances can protect servers in on-premises data centers outside China and cloud assets based on CIDR blocks. You can manually enable or disable protection in the console or by using API operations. For more information, see [Enable traffic rerouting to an on-demand instance](/intl.en-US/Anti-DDoS Origin User Guide/Enable traffic rerouting to an on-demand instance.md) and [ModifyOnDemaondDefenseStatus](/intl.en-US/API reference/Anti-DDoS Origin/API reference (2017-11-20)/On-demand instances/ModifyOnDemaondDefenseStatus.md).

5.  In the list of assets, view the protection status of each asset.

    The Assets page lists all assets in a region and provides further details about protection against DDoS attacks for each asset. The details include **Status**, **Protection Capacity**, and **Cleaning Trigger Value**.

    -   **Status** indicates the security status of an instance. Available states include **Normal**, **Cleaning**, and **Black Hole Activated**.
        -   If an instance is in the Cleaning state, you can manually cancel traffic scrubbing. For more information, see [Cancel traffic cleaning](/intl.en-US/Anti-DDoS Origin User Guide/Cleaning settings/Cancel traffic cleaning.md).
        -   If an instance is in the Black Hole Activated state, you can view the blackhole events. For more information, see [View the time when a black hole is enabled for an instance and the reason for enabling the black hole](/intl.en-US/Anti-DDoS Origin User Guide/Black hole policies/View the time when a black hole is enabled for an instance and the reason for enabling the black hole.md).
    -   **Protection Capacity** indicates the capacity of an instance to mitigate DDoS attacks. The capacity indicates the maximum bandwidth of DDoS attacks that the instance can mitigate. If the bandwidth consumed by DDoS attacks exceeds the protection capacity of an instance, blackhole filtering is triggered. As a result, all traffic that is destined for the instance is routed to a blackhole. For more information about how to improve the protection capacity of an instance, see [Step 6](#step_v0x_iwy_dq6).
    -   **Cleaning Trigger Value** indicates the minimum bandwidth that must be reached before traffic scrubbing is triggered. The bandwidth is measured in Mbit/s and packets per second \(PPS\). For more information, see [Configure a cleaning threshold](/intl.en-US/Anti-DDoS Origin User Guide/Cleaning settings/Configure a cleaning threshold.md).
6.  Improve the protection capacity of a specific asset.

    -   Enable Anti-DDoS Origin

        If you have purchased an Anti-DDoS Origin Enterprise instance in the current region, you can perform the following operations to enable Anti-DDoS Origin for a specific asset.

        Anti-DDoS Origin Enterprise instances provide account-level DDoS mitigation for all your assets and services. This helps mitigate DDoS attack risks on the cloud. Enterprises can protect their large-scale services at controllable costs, without the need to change their service architecture or increase latency. For more information, see [What is Anti-DDoS Origin?](/intl.en-US/Product Introduction on Alibaba DDoS Protection/Anti-DDoS Origin/What is Anti-DDoS Origin?.md)

        The procedure used to configure Anti-DDoS Origin for different assets, such as ECS, SLB, and EIP assets, is similar. The following procedure describes how to enable Anti-DDoS Origin for an ECS instance. You can use this example as a reference for other types of assets.

        1.  Select the ECS instance for which you want to enable Anti-DDoS Origin from the ECS instance list and click **Add Anti-DDoS Origin**.

            ![Enable Anti-DDoS Origin](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/9118858951/p72717.png)

        2.  In the Anti-DDoS Origin instance list, find the required instance and click **Add** in the Operation column.

            ![Anti-DDoS Origin instance list](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/9118858951/p72719.png)

        3.  In the OK message, click **OK**.

            ![Confirmation](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/9118858951/p72720.png)

    -   Activate Anti-DDoS Pro or Anti-DDoS Premium

        If your services face a high risk of DDoS attacks, we recommend that you activate Anti-DDoS Pro or Anti-DDoS Premium. For example, if your services experience frequent DDoS attacks, volumetric DDoS attacks, or DDoS attacks that severely affect your services, you can activate Anti-DDoS Pro or Anti-DDoS Premium. Anti-DDoS Pro and Anti-DDoS Premium defend against volumetric DDoS attacks. For more information, see [What are Anti-DDoS Pro and Anti-DDoS Premium?](/intl.en-US/Product Introduction on Alibaba DDoS Protection/What are Anti-DDoS Pro and Anti-DDoS Premium?.md)

        In the left-side navigation pane, click **Anti-DDoS Services**. Then, click **Anti-DDoS Pro** or **Anti-DDoS Premium** to go to the related console.

        -   Anti-DDoS Pro is ideal for services that are deployed in mainland China.
        -   Anti-DDoS Premium is ideal for services that are deployed outside mainland China.

