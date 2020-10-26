# Deactivate blackhole filtering

This topic describes how to deactivate blackhole filtering that has been triggered for an IP address that is protected by Anti-DDoS Origin Enterprise.

After you purchase an Anti-DDoS Origin Enterprise instance, you can deactivate blackhole filtering 100 times per month free of charge. In the validity period of your Anti-DDoS Origin Enterprise instance, the number of times to deactivate blackhole filtering is automatically reset to 100 at the beginning of each month.

**Note:** If the number of times in a month is not used up, the system clears it by the end of the month and does not add it to the number in the next month.

Before you manually deactivate blackhole filtering, check the time of automatic deactivation in the Anti-DDoS Origin console. If the time is acceptable, we recommend that you wait for blackhole filtering to be automatically deactivated. For more information, see [View the duration of a black hole](/intl.en-US/Anti-DDoS Origin User Guide/Black hole policies/View the duration of a black hole.md).

1.  Log on to the [Anti-DDoS console](https://yundun.console.aliyun.com/?p=ddos).

2.  In the upper-left corner of the top navigation bar, select a region.

3.  In the left-side navigation pane, choose **Anti-DDoS Origin** \> **Manage Instances**.

4.  On the Manage Instances page, find the required instance and click **Deactivate Black Hole** in the Actions column.

    **Note:** You can **deactivate blackhole filtering** only when blackhole filtering is triggered for **IP addresses** protected by the instance. If blackhole filtering is not triggered, the **Deactivate Black Hole** operation is not available in the console.

5.  On the **Protection Target** tab, find a protected IP address that is in the **Blackholing** state and click **Deactivate Black Hole** in the Actions column.

6.  In the **Deactivate Black Hole** dialog box, view the remaining times that you can deactivate blackhole filtering and click **OK**.

    **Note:** Blackhole filtering is a risk management policy used by the backend servers of Alibaba Cloud. If your request to deactivate blackhole filtering fails, your deactivation times for the day are not deducted.


If an error message appears, the deactivation fails. You can wait and try again later. If no error message appears, blackhole filtering is deactivated.

**Related topics**  


[DeleteBlackhole](/intl.en-US/API reference/Anti-DDoS Origin/API reference (2018-07-20)/Protection/DeleteBlackhole.md)

