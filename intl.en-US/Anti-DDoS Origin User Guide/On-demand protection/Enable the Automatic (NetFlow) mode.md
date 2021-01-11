# Enable the Automatic \(NetFlow\) mode

After you purchase an on-demand Anti-DDoS Origin instance, you can configure the start mode for the instance. If you use the default start mode and DDoS attacks are detected on your server in a data center, you must manually enable traffic rerouting to the instance. You can also enable the Automatic \(NetFlow\) mode. If the inbound bandwidth or packets consecutively exceed a threshold for the specified number of times, the Automatic \(NetFlow\) mode allows the system to automatically reroute traffic to the instance.

-   An on-demand Anti-DDoS Origin instance is purchased.

    **Note:** On-demand instances protect servers in on-premises data centers outside mainland China and cloud assets based on Classless Inter-Domain Routing \(CIDR\) blocks. You must contact sales personnel to purchase on-demand instances.

-   To protect the assets that are not deployed on Alibaba Cloud, such as servers in data centers, you must provide the NetFlow information of these servers for Alibaba Cloud. For more information, submit a [ticket](https://workorder-intl.console.aliyun.com/?#/ticket/add/?productId=80) or use a DingTalk group to submit the application.

## Procedure

1.  Log on to the [Anti-DDoS console](https://yundun.console.aliyun.com/?p=ddos).

2.  In the upper-left corner of the top navigation bar, select a region.

3.  On the **Assets** page, click the **Others** tab.

    The **Others** tab lists the IP addresses of the on-demand Anti-DDoS Origin instances that you have purchased in the current region. If you have purchased on-demand instances in other regions or have not purchased any on-demand instances, no data is displayed on the **Others** tab.

4.  Find the on-demand instance for which you want to enable the Automatic \(NetFlow\) mode and choose **More** \> **Configure Start Mode** in the Operation column.

5.  In the **Configure Start Mode** panel, configure the parameters.

    ![Configure the start mode](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/7918230161/p187497.png)

    |Parameter|Description|
    |---------|-----------|
    |**Start Mode**|The mode used to enable traffic rerouting to the on-demand instance. Valid values:    -   **Manual**: If DDoS attacks are detected on your server in a data center, you must manually enable traffic rerouting to the on-demand instance. After the attacks stop, you must manually disable traffic rerouting to the on-demand instance. This is the default value.

If you select this option, you do not need to configure other parameters.

    -   **Automatic \(NetFlow\)**: If the inbound bandwidth or packets consecutively exceed the threshold for the specified number of times, the system automatically reroutes traffic to the on-demand instance.

If you select this option, you must configure other parameters, including Stop Mode.

**Note:** Before you enable the **Automatic \(NetFlow\)** mode, make sure that you have provided the NetFlow information of your server for Alibaba Cloud. |
    |**Traffic Rate**|The threshold of inbound bandwidth. Unit: Mbit/s. Minimum value: 100.|
    |**Packet Rate \(pps\)**|The threshold of inbound packets. Unit: Kpps. Minimum value: 10.|
    |**Threshold**|If the inbound bandwidth or packets consecutively exceed the threshold for the specified number of times, the system automatically reroutes traffic to the on-demand instance. The specified number of times is the value of this parameter.|
    |**Stop Mode**|The mode used to stop traffic rerouting to the on-demand instance. Valid values:    -   **Manual**: If the DDoS attacks stop, you must manually disable traffic rerouting to the on-demand instance. This is the default value.
    -   **Automatic**: If the DDoS attacks stop, the system no longer reroutes traffic to the on-demand instance from the time you specified.

If you select this option, you must configure the following parameters:

        -   **Time Zone**: the time zone of your server. The time zone must be in the `GMT-hh:mm` format. For example, the value `GMT-08:00` indicates that the time zone is UTC+8.
        -   **Stop Time**: the time from which the system no longer reroutes traffic to the on-demand instance. The time must be in the 24-hour clock and in the `hh:mm` format.

We recommend that you set this parameter to a value that is defined as off-peak hours. If the system detects that DDoS attacks stop, the system no longer reroutes traffic to the on-demand instance from the time you specified. |

6.  Click **OK**.

    After the Automatic \(NetFlow\) mode is enabled, if the inbound bandwidth or packets consecutively exceed the threshold for the specified number of times, the system automatically reroutes traffic to the on-demand instance. You can view the protection status of the on-demand instance on the **Others** tab of the **Assets** page. For more information, see [Enable traffic rerouting to an on-demand instance](/intl.en-US/Anti-DDoS Origin User Guide/On-demand protection/Enable traffic rerouting to an on-demand instance.md).


## References

-   [SetInstanceModeOnDemand](): specifies the scheduling mode for an on-demand instance.
-   [CreateSchedruleOnDemand](): creates a scheduling rule for an on-demand instance.
-   [QuerySchedruleOnDemand](): queries the scheduling rule of an on-demand instance.
-   [ConfigSchedruleOnDemand](): modifies the scheduling rule of an on-demand instance.
-   [DeleteSchedruleOnDemand](): deletes the scheduling rule of an on-demand instance.

