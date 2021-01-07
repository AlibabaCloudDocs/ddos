# Configure a health check

Anti-DDoS Pro and Anti-DDoS Premium provide Layer 4 and Layer 7 health checks for protected non-website services. The health check feature is suitable for services that have more than one origin server IP address. This feature is used to check the availability of the backend servers. After you add a port forwarding rule to Anti-DDoS Pro or Anti-DDoS Premium, you can enable the health check feature for the forwarding rule.

-   A port forwarding rule for a non-website service is configured on the Port Config page.

    For more information, see [Create forwarding rules](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Use ports/Create forwarding rules.md).

-   The IP addresses of origin servers are configured in the port forwarding rule.

    **Note:** If you configure only one IP address of the origin server in a port forwarding rule, we recommend that you do not enable the health check feature.


The health check feature is suitable for services that have more than one origin server IP address. When Anti-DDoS Pro or Anti-DDoS Premium forwards traffic to backend servers, this feature verifies the availability of the backend servers. Therefore, traffic is forwarded to healthy backend servers to ensure that the services run properly. For more information, see [Health check overview](/intl.en-US/Classic Load Balancer/User Guide/Health check/Health check overview.md).

## Enable the health check feature

1.  Log on to the [Anti-DDoS Pro console](https://yundun.console.aliyun.com/?p=ddoscoo).

2.  In the top navigation bar, select the region where your instance resides.

    -   **Mainland China**: If you select this region, the **Anti-DDoS Pro console** appears.
    -   **Outside Mainland China**: If you select this region, the **Anti-DDoS Premium console** appears.
    You can switch the region to configure and manage Anti-DDoS Pro or Anti-DDoS Premium instances. Make sure that you select the required region when you use Anti-DDoS Pro or Anti-DDoS Premium.

3.  In the left-side navigation pane, choose **Provisioning** \> **Port Config**.

4.  On the **Port Config** page, select the instance, find the forwarding rule that you want to manage, and then click **Change** in the **Health Check** column.

    **Note:** To configure the health check feature for more than one forwarding rule at a time, you can select the rules and choose Batch Operations \> Create Session Persistence/Health Check Settings. For more information, see [Configure session persistence and health checks for more than one forwarding rule](#section_2o8_zof_4gn).

    ![Health Check](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/2813067061/p69505.png)

5.  In the **Health Check** dialog box, configure the parameters and click **Complete**.

    ![Health Check](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/2197449951/p49648.png)

    Anti-DDoS Pro or Anti-DDoS Premium allows you to configure Layer 4 and Layer 7 health checks. The following table describes the parameters.

    **Note:** You can configure advanced options for Layer 4 and Layer 7 health checks. You must click **Advanced Settings** to show advanced options. We recommend that you do not modify the advanced options.

    |Type|Parameter|Description|
    |----|---------|-----------|
    |**Layer 4 Health Check**|**Port**|The port that the health check feature uses to communicate with the backend server. Valid values: 1 to 65535. By default, the backend port that is configured for a listener is used. **Note:** The Layer 4 health check is suitable for TCP and UDP forwarding rules. |
    |**Layer 7 Health Check**|**Domain** and **Path**|During a Layer 7 health check, Anti-DDoS Pro or Anti-DDoS Premium sends an HTTP HEAD request to the default homepage of the origin server. **Note:** The Layer 7 health check is suitable only for TCP forwarding rules.

If you do not want to use the default homepage of the origin server for health checks, you must specify a domain name and a path of the page that you want to check.

If you have limited the host field for the HTTP HEAD request, you need only to specify a URI for health checks. The Domain parameter is optional. The default value is the IP address of the backend server. |
    |**Port**|The port that the health check feature uses to communicate with the backend server. Valid values: 1 to 65535. By default, the backend port that is configured for a listener is used.|
    |**Advanced Settings**|**Response Timeout Period**|The timeout period of a health check. Valid values: 1 to 30. Unit: seconds. If the backend server does not respond within the specified timeout period, the backend server is unhealthy.|
    |**Check Interval**|The interval between two consecutive health checks. Valid values: 1 to 30. Unit: seconds. **Note:** Each scrubbing node in the Anti-DDoS Pro or Anti-DDoS Premium cluster performs health checks on backend servers at the specified interval independently and concurrently. The scrubbing nodes may perform health checks on the same backend server at different points in time. Therefore, the health check records on the backend server do not indicate the time interval specified for the health check. |
    |**Unhealthy Threshold**|The number of consecutive failed health checks performed on a backend server by the same scrubbing node before the backend server is declared as unhealthy. Valid values: 1 to 10.|
    |**Healthy Threshold**|The number of consecutive successful health checks performed on a backend server by the same scrubbing node before the backend server is declared as healthy. Valid values: 1 to 10.|

    After the health check feature is enabled, **Enabled** appears in the **Health Check** column for the forwarding rule.

    ![Enabled](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6567989061/p190039.png)


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

        For more information, see [Enable the health check feature](#section_awz_6jp_tn2).

    -   Forwarding ports must be the ports that are specified in forwarding rules.
    -   If a forwarding rule uses UDP, we recommend that you configure a UDP health check. If a forwarding rule uses TCP, we recommend that you configure a TCP health check \(Layer 4 health check\) or HTTP health check \(Layer 7 health check\).
    -   If you configure an HTTP health check, the Path parameter is required, but the Domain parameter is optional.

