# Check the security overview

After you switch traffic of your service to an Anti-DDoS Pro or Anti-DDoS Premium instance, you can view the metrics and DDoS attack events in real time on the Security Overview page in the Anti-DDoS Pro or Anti-DDoS Premium console.

## Prerequisites

An Anti-DDoS Pro or Anti-DDoS Premium instance is purchased, and your service is protected by the instance. For more information, see the following topics:

-   [Purchase mitigation plans for Anti-DDoS Pro and Anti-DDoS Premium](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Purchase mitigation plans for Anti-DDoS Pro and Anti-DDoS Premium.md)
-   [Add a website](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Use domains/Add a website.md) for website services
-   [Create forwarding rules](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Use ports/Create forwarding rules.md) for non-website services

## Background information

The Security Overview page provides an overview of the following metrics and DDoS attack events:

-   Service metrics: clean bandwidth, queries per second \(QPS\), connections per second \(CPS\), protected domain names, and protected ports
-   Attack events: volumetric DDoS attacks, connection flood attacks, and resource exhaustion attacks

## Procedure

1.  Log on to the [Anti-DDoS Pro console](https://yundun.console.aliyun.com/?p=ddoscoo).

2.  In the top navigation bar, select the region where your instance resides.

    -   **Mainland China**: If you select this region, the **Anti-DDoS Pro console** appears.
    -   **Outside Mainland China**: If you select this region, the **Anti-DDoS Premium console** appears.
    You can switch the region to configure and manage Anti-DDoS Pro or Anti-DDoS Premium instances. Make sure that you select the required region when you use Anti-DDoS Pro or Anti-DDoS Premium.

3.  In the left-side navigation pane, click **Security Overview**.

4.  Turn on **Traffic Flow Diagram** to view the background information and concepts.

    **Traffic Flow Diagram** shows the relationship between origin servers and Anti-DDoS Pro or Anti-DDoS Premium instances, terms, and commonly used units.

    ![Security Overview](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/4987449951/p54011.png)

5.  Click the Instances tab, select one or more instances, and then specify a time range to view the relevant metrics.

    ![Instances tab](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/4987449951/p54020.png)

    You can view the following instance information:

    -   **Peak Attack Bandwidth** \(unit: bit/s\) and **Peak Attack Packet Rate** \(unit: pps\)
    -   Traffic trends
        -   Anti-DDoS Pro provides the **Bandwidth** trend chart to show traffic information by **bps** or **pps**. You can view the trends of inbound, outbound, and attack traffic of an instance for a specific time range.

            ![Bandwidth trends](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/4987449951/p84211.png)

        -   Anti-DDoS Premium provides the **Overview** tab to show bandwidth trends and the **Inbound Distribution** tab to show the distribution of inbound traffic. Anti-DDoS Premium also provides the **Outbound Distribution** tab to show the distribution of outbound traffic.

            ![Trend of inbound traffic](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/5987449951/p84212.png)

    -   **Attack Events** of the Blackhole and Mitigation types

        You can move the pointer over an IP address or a port to view the details of an attack, such as Attack Target, Attack Type, Peak Attack Traffic, and Protection Effect.

        ![Network attack event](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/4558121161/p212118.png)

    -   **Connections** on a port

        -   **Concurrent Connections**: the total number of concurrent TCP connections established between clients and the instance
        -   **New Connections**: the number of new TCP connections established between clients and the instance per second
        -   **Active**: the number of TCP connections in the **Established** state
        -   **Inactive**: the number of TCP connections in all states except the **Established** state
        **Note:** If you select an instance, the Connections trend chart shows the numbers of connections on different ports. If you select more than one instance, the Connections trend chart shows the total number of connections on all ports.

        ![Connections](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/5987449951/p54023.png)

    -   **Source Locations** and **Source Service Providers**

        -   **Source Locations**: the distribution of source locations from which normal traffic is sent. Source locations are classified by **Global** and **Mainland China**.
        -   **Source Service Providers**: the distribution of Internet service providers \(ISPs\) from which normal traffic is sent.
        ![Source Locations](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/2395078061/p188828.png)

6.  Click the Domains tab, select one or more domains, and then specify a time range to view the relevant metrics.

    ![Number of requests](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/5987449951/p54012.png)

    You can view the following domain information:

    -   **Peak HTTP Mitigation Traffic** \(unit: QPS\) and **Peak HTTPS Mitigation Traffic** \(unit: QPS\)
    -   **Requests** trend chart

        The trend of requests is displayed based on the peak values in a specific time range. The displayed time granularity is based on the specific time range:

        -   If the time range is less than 1 hour, the granularity is 1 minute.
        -   If the time range is from 1 to less than 6 hours, the granularity is 10 minutes.
        -   If the time range is from 6 to less than 24 hours, the granularity is 30 minutes.
        -   If the time range is from 1 to less than 7 days, the granularity is 1 hour.
        -   If the time range is from 7 to less than 15 days, the granularity is 4 hours.
        -   For larger time ranges, the granularity is 12 hours.
    -   **Mitigation Events**

        You can move the pointer over a domain to view the details of an attack, such as Domains, Peak Attack Traffic, and Attack Type.

        ![Mitigation Events](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/5987449951/p54015.png)

    -   **Response Codes** trend chart

        The trend chart of response codes shows the accumulated numbers of response codes within a specific time range. The time range and time granularity in this trend chart have definitions similar to the definitions in the **Requests** trend chart. Description of response codes:

        -   2xx: The request is successfully received, understood, and accepted by the server.

            **Note:** Statistics on 2xx response codes include the statistics on the 200 response code.

        -   200: The request succeeded.
        -   3xx: The client must perform further operations to complete the request. In most cases, a 3xx response code indicates redirection.
        -   4xx: The client may be faulty, which interrupts server processing.
        -   5xx: An error or an exception occurred when the server processed the request.
        -   502: Anti-DDoS Pro or Anti-DDoS Premium attempts to process the request as a proxy server, but it receives invalid responses from the upstream server.
        -   503: The server may be overloaded or in temporary maintenance and cannot process the request.
        -   504: Anti-DDoS Pro or Anti-DDoS Premium attempts to process the request as a proxy server, but it does not receive responses from the upstream server in a timely manner.
        ![Response codes](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/2395078061/p54017.png)

    -   **Source Locations**: the distribution of source locations from which requests are sent. Source locations are classified by **Global** and **Mainland China**.

        ![Source Locations](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/2395078061/p188920.png)

    -   **Most Requested URIs** and **Slow Loading URIs**

        -   **Most Requested URIs**: the top five most requested URIs. The URIs are displayed in descending order. You can click **More** to view the total number of requests for each URI.
        -   **Slow Loading URIs**: the top five URIs based on the response time, in seconds. The URIs are displayed in descending order. You can click **More** to view the response time of each URI.
        ![Most Requested URIs](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/2395078061/p189037.png)

    -   **Cache Hit Rate** trend chart

        You can view the trend chart of cache hit rates only after you enable the static page caching feature. For more information, see [Configure static page caching](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Protection settings/Configure static page caching.md).

        ![Cache Hit Ratio](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/2395078061/p189220.png)


