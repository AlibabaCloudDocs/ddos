# Step 2: Configure port forwarding and DDoS mitigation policies

This topic describes how to configure port forwarding policies, such as session persistence and health checks for multiple origin server IP addresses. The topic also describes how to configure DDoS mitigation policies for non-website services. The DDoS mitigation policies include False Source, Speed Limit for Destination, Packet Length Limit, and Speed Limit for Source.

A port forwarding rule is created. For more information, see [Step 1: Create a port forwarding rule](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Quick Start/Set up Anti-DDoS Pro using IPs and ports/Step 1: Create a port forwarding rule.md).

You can configure port forwarding policies and DDoS mitigation policies for non-website services based on your business requirements to improve the forwarding capability of Anti-DDoS Pro or Anti-DDoS Premium.

Anti-DDoS Pro or Anti-DDoS Premium supports the following features:

-   You can configure a session persistence policy to forward requests from a specific IP address to the same backend server.
-   You can enable the health check feature to check the availability of backend servers. This ensures that requests from clients are forwarded to healthy servers.
-   You can configure DDoS mitigation policies to limit the connection speeds and packet lengths of non-website services that are protected by Anti-DDoS Pro or Anti-DDoS Premium. This protects your non-website services against connection-oriented DDoS attacks that consume low bandwidth.

1.  Log on to the [Anti-DDoS Pro console](https://yundun.console.aliyun.com/?p=ddoscoo).

2.  In the top navigation bar, select the region where your instance resides.

    -   **Mainland China**: If you select this region, the **Anti-DDoS Pro console** appears.
    -   **Outside Mainland China**: If you select this region, the **Anti-DDoS Premium console** appears.
    You can switch the region to configure and manage Anti-DDoS Pro or Anti-DDoS Premium instances. Make sure that you select the required region when you use Anti-DDoS Pro or Anti-DDoS Premium.

3.  In the left-side navigation pane, choose **Provisioning** \> **Port Config**.

4.  On the Port Config page, select an instance, find the forwarding rule that you want to manage, and then configure the session persistence, health check, and DDoS mitigation policies for non-website services based on your business requirements.

    ![Port Config](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9887449951/p93615.png)

    -   **Session Persistence**
        1.  Click **Change** in the **Session Persistence** column.
        2.  In the Session Persistence dialog box, enable or disable session persistence based on your business requirements.
            -   To enable session persistence, set the **Timeout Period** parameter and click **Complete**.
            -   To disable session persistence, click **Disable Session Persistence**.
    -   **Health Check**

        1.  Click **Change** in the **Health Check** column.
        2.  In the Health Check dialog box, configure the parameters. For more information about the parameters, see [Configure a health check](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Use ports/Configure a health check.md).

            ![Health Check ](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/2197449951/p49648.png)

        3.  Click **Complete**.
        To disable a health check, click **Change** in the Health Check column. In the Health Check dialog box, click **Disable Health Check**.

    -   Protection for non-website services
        1.  Click **Change** in the **Anti-DDoS Protection Policy** column.
        2.  On the Protection for Non-website Services tab, configure DDoS mitigation policies based on your business requirements. You can configure the following policies:

            ![Protection for Non-website Services ](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/2397449951/p36886.png)

            -   **False Source**: verifies and filters DDoS attacks that are initiated from forged IP addresses.
            -   **Speed Limit for Destination**: The data transfer rate of the port used by the instance that exceeds the maximum visit frequency is limited based on the IP address and port of an Anti-DDoS Pro or Anti-DDoS Premium instance. The data transfer rates of other ports are not limited.
            -   **Packet Length Limit**: specifies the minimum and maximum lengths of packets that are allowed to pass through. Packets with invalid lengths are discarded.
            -   **Speed Limit for Source**: The data transfer rate of a source IP address from which access requests exceed the maximum visit frequency is limited based on the IP address and port of an Anti-DDoS Pro or Anti-DDoS Premium instance. The data transfer rates of source IP addresses from which access requests do not exceed the maximum visit frequency are not limited. This policy also supports the blacklist policy. This is when an IP address is added to the blacklist. It applies to IP addresses from which access requests exceed the maximum visit frequency five times within 60 seconds. You can also specify the blocking period.
            For more information, see [Create an anti-DDoS protection policy](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Protection settings/Protection for non-website services/Create an anti-DDoS protection policy.md).


[Step 3: View the protection data of a port](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Quick Start/Set up Anti-DDoS Pro using IPs and ports/Step 3: View the protection data of a port.md)

