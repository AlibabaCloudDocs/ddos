# Configure session persistence rules {#task228 .task}

Anti-DDoS Pro provides the session persistence feature, which supports forwarding requests from the same IP address to the same back-end server within a specific timeout period.

Anti-DDoS Pro provides protection against DDoS attacks based on source IPs and ports when no domain name is provided. The session persistence feature is available to all source IPs and ports that are associated with Anti-DDoS Pro instances.

1.  Log on to the [new Anti-DDoS Pro console](https://partners-yundunnext.console.aliyun.com/?p=ddoscoo#/report).
2.  In the left-side navigation pane, choose **Management** \> **Port Settings**.
3.  Select an Anti-DDoS Pro instance and its IP address.
4.  Select a forwarding rule and click **Change** under the Session Persistence column. 

    **Note:** The session persistence setting takes effect for individual ports.

5.  In the **Session Persistence** dialog box, specify a **Timeout Threshold** and click **Comfirm**. 

    **Note:** You can also click **Disable Session Persistence** to disable this feature.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/586604/156747907349646_en-US.png)


