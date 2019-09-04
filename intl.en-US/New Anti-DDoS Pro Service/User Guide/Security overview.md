# Security overview {#task_1461397 .task}

After you associate your domain with an Anti-DDoS Pro instance and forward incoming traffic to the instance, you can view business metrics and DDoS events in real time on the Security Overview page in the console.

The Security Overview page provides an overview of the following business metrics and DDoS events:

-   Business metrics: service bandwidth, request rate \(QPS\), connection rate \(CPS\), protected domains, and protected ports.
-   DDoS events: volume based attacks, application layer attacks and protocol attacks.

1.  Log on to the [Anti-DDoS Pro console](https://partners-yundun.console.aliyun.com/?p=ddoscoo&__consolePageCode=ddoscoo).
2.  In the left-side navigation pane, select **Statistics** \> **Security Overview**. You can learn basic terms and concepts about Anti-DDoS Pro. 

    In the top section of the **Security Overview** page, you can learn how incoming traffic flows between Anti-DDoS Pro and backend servers, and commonly used terms and units.

    ![security overview](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1161782/156756513054011_en-US.png)

3.  Click the Instances tab, select one or multiple instances, and specify a time period to view the corresponding business metrics.![instances](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1161782/156756513054020_en-US.png)

![connections](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1161782/156756513054021_en-US.png)

 

    You can view the following information about selected instances:

    -   **Peak Attack Bandwidth** and **Peak Attack Packet**
    -   Trend of Traffic **Bandwidth**, including inbound traffic, outbound traffic, and attack traffic.
    -   Attack **Events** 

        Hover over an IP address to view attack details, such as the attack type, peak attack traffic, and protection effect.

        ![events](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1161782/156756513054022_en-US.png)

    -   Port **Connections** 

        -   **Concurrent Connections**: number of TCP connections established between the client and anti-DDoS pro at the same time.
        -   **New Connections**: number of TCP connections added by the client to communicate with anti-DDoS pro per second.
        **Note:** When only one instance is selected, the chart displays the numbers of different port connections to the instance. When two or more instances are selected, the chart displays the total number of port connections to the selected instances.

        ![connections](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1161782/156756513054023_en-US.png)

    -   Traffic **Source Locations** and **ISPs**
4.  Click the Domains tab, select one or multiple domains, and specify a time period to view the corresponding business metrics.![Number of requests](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1161782/156756513054012_en-US.png)

![Response code](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1161782/156756513054018_en-US.png)

 You can view the following information about selected domains:
    -   **Peak HTTP Attack Traffic** and **Peak HTTPS Attack Traffic**
    -   Trend of **Requests** 

        The trend of requests is displayed based on the peak values during specific time intervals. The time interval varies according to the search time period.

        -   If the search time period is less than an hour, the time interval is one minute.
        -   If the search time period is between 1 to 6 hours, the time interval is 10 minutes.
        -   If the search time period is between 6 to 24 hours, the time interval is 30 minutes.
        -   If the search time period is between 1 to 7 days, the time interval is one hour.
        -   If the search time period is between 7 to 15 days, the time interval is 4 hours.
        -   For other search time periods, the time interval is 12 hours.
    -   **Application Layer Attack Events** 

        Hover over a domain to view attack details, such as the attack type and peak attack traffic.

        ![Application Layer Attack Events](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1161782/156756513054015_en-US.png)

    -   **Response Codes** 

        The trend of response codes displays the accumulated numbers of response codes within the search time period, which is the same as the time period used in the trend of **requests**. You can hover over the question mark icon to find what the response codes mean.

        ![Response Code Help](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1161782/156756513054017_en-US.png)

    -   Traffic **Source Locations**
    -   The **Most Requested URIs** and **Slow Loading URIs**
    -   Trend of **Cache Hit Rate** 

        **Note:** To view the trend of cache hit rate, you must enable the static page caching feature first. For more information, see[Configure static page caching rules](reseller.en-US/New Anti-DDoS Pro Service/User Guide/Configure layer 7 protection/Configure static page caching rules.md#).


