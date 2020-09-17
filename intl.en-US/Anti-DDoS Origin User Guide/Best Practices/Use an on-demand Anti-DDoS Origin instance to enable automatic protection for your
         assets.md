# Use an on-demand Anti-DDoS Origin instance to enable automatic protection for your assets

This topic describes the best practices to use an on-demand Anti-DDoS Origin instance to automatically protect your assets against heavy DDoS attacks. If an attack occurs, you can call API operations to enable automatic protection.

-   An Anti-DDoS Origin Enterprise instance is purchased. For more information, see [Purchase an Anti-DDoS Origin Enterprise instance](/intl.en-US/Anti-DDoS Origin User Guide/Purchase an Anti-DDoS Origin Enterprise instance.md).
-   An on-demand Anti-DDoS Origin instance is enabled. To do so, you must contact the sales personnel.
-   Alert contacts and alert groups are created in Cloud Monitor. For more information, see [Create an alert contact or alert group](/intl.en-US/Alarm service/Alert contacts/Create an alert contact or alert group.md).

An on-demand Anti-DDoS Origin instance can provide protection against DDoS attacks for on-premises data centers, small carriers, customers outside mainland China, and customers who have their own BGP networks. You do not need to change your service IP addresses or network architecture. The following figure shows the protection mechanism of the on-demand Anti-DDoS Origin instance.

![Protection mechanism](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/1302130061/p130642.png)

Description:

-   The service traffic is normal, or a small-scale attack occurs: The traffic is forwarded to the local scrubbing center of Anti-DDoS Origin. The service latency does not increase.
-   A DDoS attack occurs: The scrubbing centers distributed across the world declare routes to forward and scrub the traffic. The service latency slightly increases, but the protection capability can reach a Tbit/s level.

You can configure alert rules in Cloud Monitor to monitor DDoS attacks in the local scrubbing center of Anti-DDoS Origin. If an attack occurs, you can call API operations to enable traffic redirection of the on-demand Anti-DDoS Origin instance and disable traffic redirection after the attack stops.

**Note:** In this topic, API request parameters are described in the `<Parameter description>` format. For example, specify the ID of the on-demand Anti-DDoS Origin instance in `instanceId=<yourOnDemandInstanceId>`.

You must replace `<Parameter description>` with the actual parameter value. For example, contact the sales personnel to obtain the ID of your on-demand Anti-DDoS Origin instance and replace `<yourOnDemandInstanceId>` with the ID.

1.  Configure an alert rule in Cloud Monitor to monitor blackhole filtering and traffic scrubbing events in the local scrubbing center of Anti-DDoS Origin.

    1.  Log on to the [Cloud Monitor console](https://cloudmonitor.console.aliyun.com/#/home/ecs).

    2.  In the left-side navigation pane, choose **Alarms** \> **Alarm Rules**.

    3.  Click the **Event Alarm** tab.

    4.  On the Event Alarm tab, click **Create Event Alert**.

    5.  In the **Create / Modify Event Alert** pane, configure the following alert parameters.

        ![Create / Modify Event Alert](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/1302130061/p130616.png)

        |Parameter|Description|
        |---------|-----------|
        |**Alarm Rule Name**|Enter the name of the alert rule. For example, enter Alert for DDoS attacks of Anti-DDoS Origin.|
        |**Event Type**|Select **System Event**.|
        |**Product Type**|Select **Anti-DDoS Advanced**.|
        |**Event Level**|Select **All Levels**.|
        |**Event Name**|Select **ddosbgp\_event\_blackhole** and **ddosbgp\_event\_clean**.|
        |**Resource Range**|Select **All Resources**.|
        |**Alarm Notification**|Select **Alarm Notification**. Then, specify **Contact Group** and **Notification Method**.|

    6.  Click **OK**.

    The created alert rule automatically takes effect. If the Anti-DDoS Origin instance detects a DDoS attack, contacts in the alert group receive a notification. You can view and manage **event alert rules** in the list. For more information, see [Create an event-triggered alert rule](/intl.en-US/Alarm service/Alarm rules/Create an event-triggered alert rule.md).

    ![Event alert rules](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/1302130061/p130622.png)

2.  If a DDoS attack occurs, the contacts receive a notification of the blackhole filtering or traffic scrubbing event. In this case, call the [ModifyOnDemaondDefenseStatus](/intl.en-US/API reference/Anti-DDoS Origin/API reference (2017-11-20)/On-demand instances/ModifyOnDemaondDefenseStatus.md) API operation to redirect traffic to the global anycast scrubbing centers of Alibaba Cloud.

    You must specify the following request parameters:

    ```
    ? Action=ModifyOnDemaondDefenseStatus
    &DdosRegionId=<yourInstanceRegionId>
    &DefenseStatus=Defense
    &InstanceId=<yourOnDemandInstanceId>
    ```

3.  Disable blackhole filtering in the on-demand Anti-DDoS Origin instance.

    -   If blackhole filtering is not triggered, skip this step.
    -   If blackhole filtering is triggered, call the [DeleteBlackhole](/intl.en-US/API reference/Anti-DDoS Origin/API reference (2018-07-20)/Protection/DeleteBlackhole.md) API operation to disable it 10 seconds after you enable traffic redirection.

        You must specify the following request parameters:

        ```
        ? Action=DeleteBlackhole
        &InstanceId=<yourOnDemandInstanceId>
        &Ip=<yourOnDemandInstanceIp>
        ```

4.  Call the [DescribeTopTraffic](/intl.en-US/API reference/Anti-DDoS Origin/API reference (2017-11-20)/On-demand instances/DescribeTopTraffic.md) API operation to check whether the DDoS attack stops.

    You must specify the following request parameters:

    ```
    ? Action=DescribeTopTraffic
    &Ipnet=<onDemandInstanceIpnetToQuery>
    &InstanceId=<yourOnDemandInstanceId>
    &StartTime=<startTimeToQuery>
    &EndTime=<endTimeToQuery>             
    ```

    If the value of the AttackBps parameter returned by the API operation is smaller than 300000 for more than 30 minutes, the DDoS attack stops. This parameter indicates the volume of attack traffic, in Kbit/s.

5.  After the DDoS attack stops, call the [ModifyOnDemaondDefenseStatus](/intl.en-US/API reference/Anti-DDoS Origin/API reference (2017-11-20)/On-demand instances/ModifyOnDemaondDefenseStatus.md) API operation during off-peak hours to stop traffic redirection in the on-demand Anti-DDoS Origin instance.

    **Note:** We recommend that you call this API operation during off-peak hours to minimize service impact caused by traffic switching.

    You must specify the following request parameters:

    ```
    ? Action=ModifyOnDemaondDefenseStatus
    &DdosRegionId=<yourDdosRegionId>
    &DefenseStatus=UnDefense
    &InstanceId=<yourOnDemandInstanceId>
    ```


