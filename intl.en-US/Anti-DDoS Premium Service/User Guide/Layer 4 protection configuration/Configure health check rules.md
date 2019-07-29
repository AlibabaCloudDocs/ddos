# Configure health check rules {#concept_59593_zh .concept}

Anti-DDoS Premium provides health checks for protected non-website businesses.

Anti-DDoS Premium provides health checks for protected non-website business based on the settings of IP addresses and ports.

You can set health check rules for a specified port of a specified IP address.

## Procedure {#section_nxf_k6m_igf .section}

1.  Log on to the [Anti-DDoS Premium console](https://yundun.console.aliyun.com/?p=ddosdip).
2.  In the left-side navigation pane, choose **Provisioning** \> **Non-Website**.
3.  Select an Anti-DDoS Premium instance.
4.  Click **Edit** in the Health Check column corresponding to an existing forwarding rule.

    **Note:** The health check feature is disabled by default. When the protocol specified in the forwarding rule is TCP, you can choose either Layer 4 or Layer 7 health check.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/586603/156436781549648_en-US.png)


## Configuration items {#section_ew8_mfc_m2x .section}

**Note:** We recommend that you use default values when configuring advanced settings for health check rules.

|Health check setting|Description|
|--------------------|-----------|
|Port|The port that the health check service uses to communicate with the back-end server. The back-end port configured for the listener is used by default.|
|**Advanced setting**|
|Response Timeout|The maximum timeout period for each health check response. If the back-end server does not respond within the timeout period, the health check fails.|
|Check Interval|The interval between two consecutive health checks. All scrubbing nodes in the Anti-DDoS Premium cluster perform health checks on back-end servers at the specified interval independently and concurrently. Scrubbing nodes may perform health checks on the same back-end server at different points in time. This is the reason why the health check records on the back-end server do not indicate a check interval.|
|Unhealthy Threshold|The number of consecutive failed health checks performed by the same scrubbing node server that must occur before declaring a back-end server unhealthy.|
|Healthy Threshold|The number of consecutive successful health checks performed by the same scrubbing node that must occur before declaring a back-end server healthy.|

|Health check setting|Description|
|--------------------|-----------|
|Domain Name and Health Check URI \(HTTP only\)|During a Layer 7 health check, the Anti-DDoS Premium forwarding system sends an HTTP HEAD request to the default homepage of the back-end server. -   If the page for health checks is not the default homepage of the back-end server, you must specify the domain name and URI for health checks.
-   If you have limited the host header field to specific values, you only need to specify the URI for health checks. The domain parameter is optional and set to the IP address of the back-end server by default.

 |
|Port|The port that the health check service uses to communicate with the back-end server. The back-end port configured for the listener is used by default.|
|**Advanced setting**|
|Response Timeout|The maximum timeout period for each health check response. If the back-end server does not respond within the timeout period, the health check fails.|
|Check Interval|The interval between two consecutive health checks. All scrubbing nodes in the Anti-DDoS Premium cluster perform health checks on back-end servers at the specified interval independently and concurrently. Scrubbing nodes may perform health checks on the same back-end server at different points in time. This is the reason why the health check records on the back-end server do not indicate a check interval.|
|Unhealthy Threshold|The number of consecutive failed health checks performed by the same scrubbing node that must occur before declaring a back-end server unhealthy.|
|Healthy Threshold|The number of consecutive successful health checks performed by the same scrubbing node that must occur before declaring a back-end server healthy.|

