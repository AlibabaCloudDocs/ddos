# Configure session persistence

After you add non-website services to Anti-DDoS Pro or Anti-DDoS Premium, issues such as logon timeout or disconnections may occur. In this case, you can enable the session persistence feature. This feature forwards requests from the same client to the same backend server within a specified period. This topic describes how to configure session persistence for a port forwarding rule.

A port forwarding rule for a non-website service is configured on the Port Config page. For more information, see [Create forwarding rules](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Use ports/Create forwarding rules.md).

## Enable session persistence

1.  Log on to the [Anti-DDoS Pro console](https://yundun.console.aliyun.com/?p=ddoscoo).

2.  In the top navigation bar, select the region where your instance resides.

    -   **Mainland China**: If you select this region, the **Anti-DDoS Pro console** appears.
    -   **Outside Mainland China**: If you select this region, the **Anti-DDoS Premium console** appears.
    You can switch the region to configure and manage Anti-DDoS Pro or Anti-DDoS Premium instances. Make sure that you select the required region when you use Anti-DDoS Pro or Anti-DDoS Premium.

3.  In the left-side navigation pane, choose **Provisioning** \> **Port Config**.

4.  On the **Port Config** page, select the instance, find the forwarding rule that you want to manage, and then click **Change** in the **Session Persistence** column.

    **Note:** You can also enable session persistence for more than one forwarding rule of an instance at a time. For more information, see [Configure session persistence and health checks for more than one rule at a time](#section_qm6_zi5_600).

    ![Port Config](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/3813067061/p69479.png)

5.  In the **Session Persistence** dialog box, set **Timeout Period** and click **Complete**. The timeout period is measured in seconds, and the valid value ranges from 30 to 3600.

    After the session persistence feature is enabled, the status of **Session Persistence** changes to **Enabled**.

    ![Enabled](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/3058989061/p189964.png)


## Configure session persistence and health checks for more than one forwarding rule

1.  Log on to the [Anti-DDoS Pro console](https://yundun.console.aliyun.com/?p=ddoscoo).

2.  In the top navigation bar, select the region where your instance resides.

    -   **Mainland China**: If you select this region, the **Anti-DDoS Pro console** appears.
    -   **Outside Mainland China**: If you select this region, the **Anti-DDoS Premium console** appears.
    You can switch the region to configure and manage Anti-DDoS Pro or Anti-DDoS Premium instances. Make sure that you select the required region when you use Anti-DDoS Pro or Anti-DDoS Premium.

3.  In the left-side navigation pane, choose **Provisioning** \> **Port Config**.

4.  On the **Port Config** page, select the instance that you want to manage and choose **Batch Operations** \> **Create Session Persistence/Health Check Settings**.

    ![Create Session Persistence/Health Check Settings](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6567989061/p190055.png)

5.  In the **Create Session Persistence/Health Check Settings** dialog box, enter the required information as shown in the sample file and click **OK**.

    ![Session Persistence/Health Check Settings](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/3197449951/p69485.png)

    **Note:** You can export health check settings to a TXT file, modify the settings in the TXT file, and then copy and paste the settings to the Create Session Persistence/Health Check Settings dialog box. For more information, see [Export multiple port configurations](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Use ports/Export multiple port configurations.md).

    The formats of session persistence and health check settings must meet the following requirements:

    -   Each line represents a forwarding rule.
    -   From left to right, the fields in each forwarding rule indicate the following parameters: forwarding port, forwarding protocol, session persistence timeout period, health check type, port, response timeout period, check interval, unhealthy threshold, healthy threshold, path, and domain name. The supported forwarding protocols are TCP, HTTP, and UDP. The session persistence timeout period is measured in seconds, and the valid value ranges from 30 to 3600. Fields are separated by spaces.

        For more information, see [\#d8e32](#d8e32).

    -   Forwarding ports must be the ports that are specified in forwarding rules.
    -   If a forwarding rule uses UDP, we recommend that you configure a UDP health check. If a forwarding rule uses TCP, we recommend that you configure a TCP health check \(Layer 4 health check\) or HTTP health check \(Layer 7 health check\).
    -   If you configure an HTTP health check, the Path parameter is required, but the Domain parameter is optional.

