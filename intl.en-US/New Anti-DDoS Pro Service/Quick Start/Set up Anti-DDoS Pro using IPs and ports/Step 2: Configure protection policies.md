# Step 2: Configure protection policies {#task_226581 .task}

After a port forwarding rule is added, you can configure the following protection policies based on your needs: session persistence, health check, and anti-DDoS protection.

You have added port forwarding rules. For more information, see [Step 1: Create a port forwarding rule](reseller.en-US/New Anti-DDoS Pro Service/Quick Start/Set up Anti-DDoS Pro using IPs and ports/Step 1: Create a port forwarding rule.md#).

You can configure protection policies based on different business scenarios. For example,

-   you can configure a session persistence policy based on IP address to forward requests from the same IP address to the same origin server.
-   You can configure a health check policy to check the availability of the origin server. The purpose of a health check is to ensure that requests from the client are not forwarded to servers where exceptions have occurred.
-   Anti-DDoS protection policies are based on IPs and ports. To mitigate DDoS attacks, you can configure policies to set limits on parameters, such as the request rate or packet length.

1.   Log on to the [Anti-DDoS Pro console](https://partners-yundunnext.console.aliyun.com/?p=ddoscoo#/domain). 
2.   In the left-side navigation pane, choose **Management** \> **Port Settings**. 
3.   On the Port Settings page, select an Anti-DDoS Pro instance.![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/190015/156153962546906_en-US.png)

  
4.   Select a port forwarding rule and configure the session persistence, health check, and anti-DDoS protection policies based on your needs. 
    -    **Session persistence** 

        1.  Click **Change** in the **Session Persistence** column.
        2.  In the Session Persistence dialog box, enable or disable session persistence based on your needs.
            -   To enable session persistence, specify the **Timeout Period** and click **Complete**.
            -   To disable session persistence, click **Disable Session Persistence**.
        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/190015/156153962546907_en-US.png)

    -    **Health check** 
        1.  Click **Change** in the **Health Check** column.
        2.  In the Health Check dialog box, complete the configuration. The configuration details are as follows. You can click **Advanced Settings** to show or hide advanced settings.

            |Type|Item|Description|
            |----|----|-----------|
            |Layer 4 and layer 7| **Port** |The port that the health check service uses to communicate with the origin server. Default is the port of the origin server. Valid values: 1 to 65535.|
            |Layer 7| **Domain**, **Path** |This setting is only applicable to TCP rules. During a layer 7 health check, the Anti-DDoS Pro forwarding system sends an HTTP header request to the default homepage on the origin server.             -   If you do not want to use the default homepage for health checks, you must enter a domain and path of another page.
            -   If you have limited the host header field to specific values, you only need to specify the URI for health checks. The domain parameter is optional and set to the IP address of the origin server by default.
 |
            |Advanced setting| **Response Timeout Period** |The timeout period during a health check. Valid values: 1 to 30 seconds. If the origin server does not respond within the timeout period, it indicates that the health check failed.|
            |Advanced setting| **Check Interval** |The time interval between two health checks. Valid values: 1 to 30 seconds. All scrubbing nodes in the Anti-DDoS Pro cluster perform health checks on origin servers at the specified interval independently and concurrently. Scrubbing nodes may perform health checks on the same origin server at different times. This is the reason that the health check records on the origin server do not indicate a check interval.|
            |Advanced setting| **Unhealthy Threshold** |The number of consecutive failed health checks performed by the same scrubbing node that must occur before declaring an origin server unhealthy. Valid values: 1 to 10.|
            |Advanced setting| **Healthy Threshold** |The number of consecutive successful health checks performed by the same scrubbing node that must occur before declaring an origin server healthy. Valid values: 1 to 10.|

            ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/190015/156153962546908_en-US.png)

            ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/190015/156153962546909_en-US.png)

        3.  Click **Complete** to enable health check policies. To disable health check policies, click **Change** in the Health Check column. In the Health Check dialog box that appears, click **Disable Health Check**.
    -    **Anti-DDoS protection policies** 
        1.  Click **Change** in the **Anti-DDoS Protection Policy** column.
        2.  In the Anti-DDoS Protection Policy dialog box, complete the configuration. The configuration details are as follows:

            |Item|Description|
            |----|-----------|
            | **False Source** |Detects and blocks false source IPs. This setting is only applicable to TCP rules.|
            | **Empty Connection** |Detects and blocks null session connections. This setting is only applicable to TCP rules. **Note:** To enable Empty Connections, you must enable False Source first.

 |
            | **Source New Connection Rate Limit** |The maximum number of new connections per second from a single source IP. All new connections exceeding the limit are discarded. The actual limit on the new connection rate may be slightly different because the scrubbing nodes are deployed in clusters. The rate limit can be set to **Automatic** or **Manual**. Valid values: 1 to 50,000.|
            | **Source Concurrent Connection Rate Limit** |The maximum number of concurrent connections from a single source IP. All connections exceeding the limit are discarded. When enabled, you must specify a rate limit. Valid values: 1 to 50,000.|
            | **Destination New Connection Rate Limit** |The maximum number of new connections per second to a single destination IP and port. All new connections exceeding the limit are discarded. The actual limit on the new connection rate may be slightly different because the scrubbing nodes are deployed in clusters. When enabled, you must specify a rate limit. Valid values: 100 to 100,000.|
            | **Destination Concurrent Connection Rate Limit** |The maximum number of concurrent connections to a single destination IP and port. All connections exceeding the limit are discarded. When enabled, you must specify a rate limit. Valid values: 1,000 to 1,000,000.|
            | **Packet Length Limit** |The limit on packet payload length. Unit: byte. All packets exceeding the limit are discarded. Valid values: 0 to 6,000.|

            ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/190015/156153962546910_en-US.png)

        3.  Click **OK**.

