# Step 5: View security reports and log data {#task_222311 .task}

After you set up an Anti-DDoS Pro instance to protect your service, you can view security reports and log data in the Anti-DDoS Pro console.

-   You have added your website in the Anti-DDoS Pro console. For more information, see [Step 1: Add a website](reseller.en-US/New Anti-DDoS Pro Service/Quick Start/Set up Anti-DDoS Pro using domains/Step 1: Add a website.md#).
-   You have changed DNS records to forward traffic to Anti-DDoS Pro. For more information, see [Step 2: Change DNS records](reseller.en-US/New Anti-DDoS Pro Service/Quick Start/Set up Anti-DDoS Pro using domains/Step 2: Change DNS records.md#).

1.   Log on to the [Anti-DDoS Pro console](https://partners-yundunnext.console.aliyun.com/?p=ddoscoo#/domain). 
2.   Perform the following steps based on your needs: 
    -   View security reports

        In the left-side navigation pane, choose **Statistics** \> **Security Reports**. On the Reports page, select one of the following to view the corresponding reports: Service, Anti-DDoS Protection, and HTTP Flood Protection.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/189924/156154079646059_en-US.png)

        You can add multiple filter conditions to customize the reports. For example, time range, Anti-DDoS Pro instance, instance IP, and port number. The differences between these reports are as follows:

        |Report|Content|Filter condition|
        |------|-------|----------------|
        |Service|         -   Changes of inbound and outbound bandwidth
        -   Changes of concurrent connections and new connections
 |         -   Time range
        -   Anti-DDoS Pro instance
        -   Anti-DDoS Pro instance IP
        -   Forwarding port
 |
        |Anti-DDoS Protection|         -   Changes of back-to-origin traffic and scrubbed traffic
        -   Records of DDoS attacks
 |         -   Time range
        -   Anti-DDoS Pro instance
        -   Anti-DDoS Pro instance IP
 |
        |HTTP Flood Protection|         -   Changes of malicious requests and total requests
        -   Records of HTTP flood attacks
 |         -   Time range
        -   Protected domain
 |

        For more information, see [View security reports](reseller.en-US/New Anti-DDoS Pro Service/User Guide/View security reports.md#).

    -   Query and analyze log data

        In the left-side navigation pane, choose **System** \> **Logs**. On the Logs page, select the type of log data that you want to query: Operation Logs, Protection Logs. The differences between these types of log data are as follows:

        -   Operation logs record important operations of the last 30 days. For example, operations performed on IP addresses of protected assets, Anti-DDoS packages, and ECS instances. You can filter log records by time.
        -   Protection logs record the attacks that are experienced by Anti-DDoS Pro instances. You can filter log records by time.
        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/189924/156154079746060_en-US.png)

        If you need to analyze log data in real time and display results with graphs, we recommend that you activate Anti-DDoS Pro Full Log Service. After Anti-DDoS Pro Full Log Service is activated, access logs on your site are collected and maintained by [Alibaba Cloud Log Service](../../../../reseller.en-US/Product Introduction/What is Log Service.md#). You can search and analyze log data in real time, and view search results through dashboards.

        Anti-DDoS Pro Full Log Service is a value-added service. To use the service, you must activate and enable it. To use Anti-DDoS Pro Full Log Service, perform the following steps:

        1.  Activate Anti-DDoS Pro Full Log Service. For more information, see [Activate the full log service](reseller.en-US/New Anti-DDoS Pro Service/User Guide/Log queries/Full log.md#section_tsj_h3f_g30).
        2.  Enable Anti-DDoS Pro Full Log Service. For more information, see [Enable the full log service](reseller.en-US/New Anti-DDoS Pro Service/User Guide/Log queries/Full log.md#section_brn_bn3_kgb).
        After Anti-DDoS Pro Full Log Service is enabled, you can choose **Statistics** \> **Full Log** to search and analyze log data in real time. You can also view and edit dashboards, and set monitoring alerts on this page.

        **Note:** For more information about the fields that are displayed in a log record, see [Fields](reseller.en-US/New Anti-DDoS Pro Service/User Guide/Log queries/Fields.md#).

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/189924/156154079746061_en-US.png)


