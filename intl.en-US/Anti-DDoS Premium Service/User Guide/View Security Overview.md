# View Security Overview {#task_1461397 .task}

After you migrate your workloads to Anti-DDoS Premium and switch workload traffic to the Anti-DDoS Premium instance, you can go to the Security Overview page in the console. On this page, you can view the metrics and attack events in real time.

The Security Overview page provides an overview of the following metrics and DDoS attack events:

-   Workload metrics: service bandwidth, request rate \(QPS\), connection rate \(CPS\), protected domains, and protected ports.
-   Attack events: volumetric attacks, connection attacks, and application layer attacks.

1.  Log on to the [Anti-DDoS Premium console](https://yundun.console.aliyun.com/?p=ddosdip).
2.  On the **Security Overview** page, you can learn more about the background information and related concepts. 

    In the top section of the **Security Overview** page, you can learn about traffic flow information, commonly used terms, and units of measurement.

    ![Security overview](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1161782/156817493754011_en-US.png)

3.  Click the Instances tab, select one or more instances, and specify a time range to view the corresponding metrics.![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1592069/156817493758763_en-US.png)

![Connections](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1161782/156817493754021_en-US.png)

 

    You can view the following information about the selected instances:

    -   The **Peak Attack Bandwidth** and the **Peak Attack Packet Rate**
    -   The **Bandwidth** traffic, including inbound traffic, outbound traffic, and attack flow
    -   Attack **Events** 

        Move the pointer over an IP address to view the attack details, such as the attack type, peak attack traffic, and protection effect.

        ![Events](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1161782/156817493754022_en-US.png)

    -   Port **Connections** 

        -   **Concurrent Connections**: The total number of concurrent TCP connections established between clients and the Anti-DDoS Premium instance.
        -   **New Connections**: The total number of new TCP connections established between clients and the Anti-DDoS Premium instance per second.
        **Note:** When only one instance is selected, the chart displays the numbers of different port connections to the instance. When two or more instances are selected, the chart displays the total number of port connections.

        ![Connections](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1161782/156817493854023_en-US.png)

    -   The distribution of traffic for **Source Locations** and **ISPs**
4.  Click the Domains tab, select one or more domains, and specify a time range to view the corresponding metrics.![Requests](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1161782/156817493854012_en-US.png)

![Response codes](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1161782/156817493854018_en-US.png)

 You can view the following information about the selected domains:
    -   The **Peak HTTP Attack Traffic** and the **Peak HTTPS Attack Traffic**
    -   The **Requests** trend chart

        The trend of requests is displayed based on the peak values in the queried time range. The displayed time granularity is based on the size of the queried time range:

        -   If the time range is less than an hour, the granularity is one minute.
        -   If the time range is between 1 to 6 hours, the granularity is 10 minutes.
        -   If the time range is between 6 to 24 hours, the granularity is 30 minutes.
        -   If the time range is between 1 to 7 days, the granularity is one hour.
        -   If the time range is between 7 to 15 days, the granularity is 4 hours.
        -   For other time ranges, the granularity is 12 hours.
    -   **Application Layer Attack Events** 

        Move the pointer over a domain to view attack details, such as the attack type and peak attack traffic.

        ![Application Layer Attack Events](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1161782/156817493854015_en-US.png)

    -   **Response Codes** information

        The trend of response codes displays the accumulated numbers of response codes within the queried time range. This range is the same as the time range used in the **Requests** trend chart. You can move the pointer over the question mark icon to find the explanation for the response codes.

        ![Response Codes](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1161782/156817493854017_en-US.png)

    -   The traffic **Source Locations**
    -   **Most Requested URIs** and **Slow Loading URIs**
    -   The trend chart for the **Cache Hit Rate** 

        **Note:** You must enable the Static Page Caching feature before you can view the trend for the cache hit rate. For more information, see [Accelerate access to a static page](intl.en-US/Anti-DDoS Premium Service/User Guide/Layer 7 protection configuration/Accelerate access to a static page.md#).


