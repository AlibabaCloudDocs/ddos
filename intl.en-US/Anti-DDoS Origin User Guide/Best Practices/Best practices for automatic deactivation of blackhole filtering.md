# Best practices for automatic deactivation of blackhole filtering

If your service IP address encounters volumetric DDoS attacks after your service IP address is added to Anti-DDoS Origin Enterprise, blackhole filtering may still be triggered. To avoid extended periods of service disruption, you must deactivate blackhole filtering at the earliest opportunity. Anti-DDoS Origin Enterprise provides a solution to configure alerts and automatically deactivate blackhole filtering.

This solution requires you to call an API operation of Anti-DDoS Origin Enterprise. Therefore, this solution is available only for Anti-DDoS Origin Enterprise instances. Before you use this solution, make sure that your service IP address is added to an Anti-DDoS Origin Enterprise instance. For more information, see [Add a cloud service to Anti-DDoS Origin Enterprise for protection](/intl.en-US/Anti-DDoS Origin User Guide/Instances/Add a cloud service to Anti-DDoS Origin Enterprise for protection.md).

You can manually deactivate blackhole filtering for Anti-DDoS Origin Enterprise instances in the Anti-DDoS Basic console. For more information, see [Deactivate blackhole filtering](/intl.en-US/Anti-DDoS Origin User Guide/Black hole policies/Deactivate blackhole filtering.md). However, manual deactivation may result in delays and unexpected errors. If your service requires a high level of stability and continuity, use the following method to configure alerts and automatically deactivate blackhole filtering:

1.  Create an alert rule in the Cloud Monitor console to monitor blackhole filtering that is triggered on an Anti-DDoS Origin Enterprise instance.

    **Note:** If blackhole filtering is triggered and detected on the IP addresses that are added to Anti-DDoS Origin Enterprise, Cloud Monitor sends messages about blackhole filtering. In other scenarios, no messages about blackhole filtering are sent.

2.  Create an alert rule to automatically deactivate blackhole filtering on Anti-DDoS Origin Enterprise by calling the DeleteBlackhole operation. For more information, see [DeleteBlackhole](/intl.en-US/API reference/Anti-DDoS Origin/API reference (2018-07-20)/Protection/DeleteBlackhole.md).

Similarly, you can create rules to automatically call an API operation of Alibaba Cloud DNS. The operation resolves your domain name to the IP address of an Anti-DDoS Pro or Anti-DDoS Premium instance during DDoS attacks.

1.  Log on to the [Cloud Monitor console](https://cloudmonitor.console.aliyun.com/).

2.  In the left-side navigation pane, choose **Alerts** \> **Alert Rules**.

3.  On the Alert Rules page, click the **Event Alert** tab.

4.  Click **Create Event Alert** to create a rule for blackhole filtering.

    -   In the panel that appears, set **Product Type** to **Anti-DDoS Advanced**.
    -   In the **Event Name** drop-down list, select **ddosbgp\_event\_blackhole**.
    ![Event alerts](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/5478248951/p53155.png)

5.  Select the channel to push alert notifications based your service requirements and click **OK**.

    Cloud Monitor supports the following channels:

    -   **MNS queue**
    -   **Function service**
    -   **URL callback**
    -   **Log Service**
    ![Alert types](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/5478248951/p53156.png)

    The event alert is created. When Cloud Monitor detects that blackhole filtering is triggered on an IP address that is added to Anti-DDoS Origin Enterprise, Cloud Monitor generates an alert and pushes the following message through the specified channel.

    Sample alert message:

    ```
    {    
        "action": "add", //The event status. The value add indicates that the event begins, and the value del indicates that the event ends.    
        "bps": 0, //The throughput when the event is triggered. Unit: Mbit/s.    
        "pps": 0, //The packet rate when the event is triggered. Unit: packets per second (PPS).    
        "instanceId": "ddosbgp-cn-78v17******", //The ID of the Anti-DDoS Origin Enterprise instance.    
        "ip": "47. *. *. *", //The IP address on which the event is triggered.    
        "regionId": "cn-hangzhou", //The ID of the region where the Anti-DDoS Origin Enterprise instance resides.    
        "time": 1564104493000, //The time when the event begins. The value is a timestamp. Unit: milliseconds.    
        "type": "blackhole"  //The event type. The value defense indicates a traffic scrubbing event and the value blackhole indicates a blackhole filtering event.
    }
    ```

6.  Specify an alert action that calls the DeleteBlackhole operation to automatically deactivate blackhole filtering. For more information, see [DeleteBlackhole](/intl.en-US/API reference/Anti-DDoS Origin/API reference (2018-07-20)/Protection/DeleteBlackhole.md).


