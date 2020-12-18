# Enable traffic rerouting to an on-demand instance

This topic describes how to enable traffic rerouting to an on-demand Anti-DDoS Origin instance in the Anti-DDoS console.

An on-demand Anti-DDoS Origin instance is purchased.

**Note:** On-demand instances protect servers in on-premises data centers outside China and cloud assets based on CIDR blocks. You must contact sales personnel to purchase on-demand instances.

1.  Log on to the [Anti-DDoS console](https://yundun.console.aliyun.com/?p=ddosnext).

2.  In the top navigation bar, select the region where your on-demand Anti-DDoS Origin instance resides.

3.  On the Assets page, click the **Others** tab.

    **Note:** The **Others** tab shows the IP addresses of all your on-demand Anti-DDoS Origin instances. If you have not purchased on-demand instances, the **Others** tab contains no IP addresses.

4.  Find the IP address of your on-demand instance and click **Start Redirection** in the Operation column. In the message that appears, click OK.

    ![Start Redirection](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/7218858951/p130268.png)


If traffic rerouting is enabled, the IP address of your on-demand instance is in the **Redirecting** state. This indicates that the system is rerouting the traffic of protected assets to mitigate DDoS attacks. If you want to stop rerouting the traffic, click **Pause Redirection** in the Operation column.

**Note:** After you click Pause Redirection, the system no longer reroutes the traffic of protected assets to your on-demand instance and does not mitigate DDoS attacks for your assets.

![Pause Redirection](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/7218858951/p130266.png)

