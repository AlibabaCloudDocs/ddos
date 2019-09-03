# Configure health check rules {#concept_59593_zh .concept}

Anti-DDoS Pro provides the health check feature.

Anti-DDoS Pro provides protection against DDoS attacks based on source IPs and ports when no domain name is provided. The health check feature is available to all source IPs and ports that are associated with Anti-DDoS Pro instances.

You can configure health check rules for specific IPs and ports.

## Procedure {#section_nxf_k6m_igf .section}

1.  Log on to the [new Anti-DDoS Pro console](https://partners-yundunnext.console.aliyun.com/?p=ddoscoo#/report).
2.  In the left-side navigation pane, choose **Management** \> **Port Settings**.
3.  Select an Anti-DDoS Pro instance.
4.  Select a forwarding rule and click **Change** under the Health Check column.

    **Note:** The health check feature is disabled by default. If the selected forwarding rule is based on the TCP protocol, you can configure layer 4 or layer 7 health check settings.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/586603/156747905649648_en-US.png)


## Configuration items {#section_ew8_mfc_m2x .section}

**Note:** We recommend that you use the default values for advanced settings.

|Parameter|Description|
|---------|-----------|
|Port|The port that the health check service uses to communicate with the origin server. Default is the port of the origin server.|
|**Advanced settings**|
|Response Timeout Period|The timeout period during a health check. If the origin server does not respond within the timeout period, it indicates that the health check failed.|
|Check Interval|The time interval between two consecutive health checks. All scrubbing nodes in the Anti-DDoS Pro cluster perform health checks on origin servers at the specified interval independently and concurrently. Scrubbing nodes may perform health checks on the same origin server at different times. This is the reason that the health check records on the origin server do not indicate a check interval.|
|Unhealthy Threshold|The number of consecutive failed health checks performed by the same scrubbing node that must occur before declaring an origin server unhealthy.|
|Healthy Threshold|The number of consecutive successful health checks performed by the same scrubbing node that must occur before declaring an origin server healthy.|

|Parameter|Description|
|---------|-----------|
|Domain and path \(HTTP only\)|During a layer 7 health check, the Anti-DDoS Pro forwarding system sends an HTTP HEAD request to the default homepage on the origin server. -   If you do not want to use the default homepage for health checks, you must enter a domain and path of another page.
-   If you have limited the host header field to specific values, you only need to specify the URI for health checks. The domain parameter is optional and set to the IP address of the origin server by default.

 |
|Port|The port that the health check service uses to communicate with the origin server. Default is the port of the origin server.|
|**Advanced settings**|
|Response Timeout Period|The timeout period during a health check. If the origin server does not respond within the timeout period, it indicates that the health check failed.|
|Check Interval|The time interval between two consecutive health checks. All scrubbing nodes in the Anti-DDoS Pro cluster perform health checks on origin servers at the specified interval independently and concurrently. Scrubbing nodes may perform health checks on the same origin server at different times. This is the reason that the health check records on the origin server do not indicate a check interval.|
|Unhealthy Threshold|The number of consecutive failed health checks performed by the same scrubbing node that must occur before declaring an origin server unhealthy.|
|Healthy Threshold|The number of consecutive successful health checks performed by the same scrubbing node that must occur before declaring an origin server healthy.|

