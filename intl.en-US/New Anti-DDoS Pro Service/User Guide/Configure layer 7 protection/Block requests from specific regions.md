# Block requests from specific regions {#task_183076 .task}

Geo-blocking allows you to block access from specific regions based on IP address. For example, you can choose to block requests from 34 Chinese provincial regions and 7 international regions. Currently, this feature is only available to specific domains.

Before you enable Geo-blocking, make sure that your domain is associated with an Anti-DDoS Pro instance of the enhanced package.

Assume that all normal requests to website example.aliyundemo.com are from 34 Chinese provincial regions. You can use Geo-blocking to block requests from international regions.

**Notes** 

-   To enable Geo-blocking for multiple domains, you must modify Geo-blocking status for each domain respectively.
-   When Geo-blocking is enabled, Anti-DDoS Pro identifies and filters traffic based on the region where the traffic originates. This feature does not reduce the volume of traffic that enters Anti-DDoS Pro scrubbing centers.

1.  Log on to the [new Anti-DDoS Pro console](https://partners-yundun.console.aliyun.com/?p=ddoscoo&__consolePageCode=ddoscoo).
2.  In the left-side navigation pane, choose **Protection** \> **Protection Settings** \> **HTTP Flood Protection Policies**.
3.  Select a domain, for example, example.aliyundemo.com. In the Geo-blocking section, click the Status toggle to enable Geo-blocking for the selected domain.![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/156896/156747922344273_en-US.png)


4.  Click **Change Settings**. Select the regions that you want to block in the dialog box that appears. You can select regions as follows to block traffic from international regions.![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/156896/156747922344274_en-US.png)


5.  Click **OK** and the configuration takes effect immediately.

