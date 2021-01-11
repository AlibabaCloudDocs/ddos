# Enable traffic rerouting to an on-demand instance

If you purchase an on-demand Anti-DDoS Origin instance and DDoS attacks are detected on your server in a data center, you can manually enable traffic rerouting to the instance. After the attacks stop, you can disable traffic rerouting to the instance.

## Prerequisites

An on-demand Anti-DDoS Origin instance is purchased.

**Note:** On-demand instances protect servers in on-premises data centers outside mainland China and cloud assets based on Classless Inter-Domain Routing \(CIDR\) blocks. You must contact sales personnel to purchase on-demand instances.

## Procedure

1.  Log on to the [Anti-DDoS console](https://yundun.console.aliyun.com/?p=ddos).

2.  In the upper-left corner of the top navigation bar, select a region.

3.  On the **Assets** page, click the **Others** tab.

    The **Others** tab lists the IP addresses of the on-demand Anti-DDoS Origin instances that you have purchased in the current region. If you have purchased on-demand instances in other regions or have not purchased any on-demand instances, no data is displayed on the **Others** tab.

4.  Find the on-demand instance for which you want to enable traffic rerouting and click **Start Redirection** in the Operation column. In the message that appears, click **OK**.

    After you enable traffic rerouting to the on-demand instance, the instance enters the **Redirecting** state. This indicates that the system is rerouting the traffic destined for protected assets to mitigate DDoS attacks.

    If you want to stop traffic rerouting to the on-demand instance, click **Pause Redirection** in the Operation column.

    **Note:** After you click Pause Redirection, the system no longer reroutes the traffic destined for protected assets to your on-demand instance and does not mitigate DDoS attacks for your assets.


## References

You can also enable the Automatic \(NetFlow\) mode to automatically reroute traffic to an on-demand instance. You can enable or disable traffic rerouting to an on-demand instance based on the NetFlow information of your servers in data centers and rules that you specified. For more information about how to enable the Automatic \(NetFlow\) mode, see [Enable the Automatic \(NetFlow\) mode](/intl.en-US/Anti-DDoS Origin User Guide/On-demand protection/Enable the Automatic (NetFlow) mode.md).

## Related API operations

-   [ModifyOnDemaondDefenseStatus](/intl.en-US/API reference/Anti-DDoS Origin/API reference (2017-11-20)/On-demand instances/ModifyOnDemaondDefenseStatus.md)

