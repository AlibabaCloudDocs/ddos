# Configure cross-border traffic blocking

After you add the IP address of your cloud asset to Anti-DDoS Origin Enterprise, you can enable the cross-border traffic blocking feature to block cross-border traffic. This improves DDoS mitigation effects. This feature is applicable to scenarios where your service does not involve cross-border traffic.

-   An Anti-DDoS Origin Enterprise instance is purchased.

    For more information, see [Purchase an Anti-DDoS Origin Enterprise instance](/intl.en-US/Anti-DDoS Origin User Guide/Purchase an Anti-DDoS Origin Enterprise instance.md).

    **Note:** The mitigation settings feature is now public preview. If you have purchased an Anti-DDoS Origin Enterprise instance, you can submit a [ticket](https://workorder-intl.console.aliyun.com/?#/ticket/add/?productId=80) to enable this feature.

-   The IP address of your cloud asset is added to Anti-DDoS Origin Enterprise.

    For more information, see [Add a cloud service to Anti-DDoS Origin Enterprise for protection](/intl.en-US/Anti-DDoS Origin User Guide/Instances/Add a cloud service to Anti-DDoS Origin Enterprise for protection.md).


The cross-border traffic blocking feature blocks cross-border traffic within a specific blocking period

-   Cross-border traffic:
    -   If your cloud asset resides in mainland China, the feature blocks traffic that originates from outside mainland China.
    -   If your cloud asset resides outside mainland China, this feature blocks traffic that originates from mainland China.
-   Blocking period: 30 minutes to 1 day.
-   Limits: By default, you can enable this feature 10 times per month for each Anti-DDoS Origin Enterprise instance.

    If your quota is exhausted, you can submit a [ticket](https://workorder-intl.console.aliyun.com/?#/ticket/add/?productId=80) to request technical support.


You can manually disable this feature at any time during the blocking period.

## Enable cross-border traffic blocking

1.  Log on to the [Anti-DDoS console](https://yundun.console.aliyun.com/?p=ddos).

2.  In the left-side navigation pane, choose **Anti-DDoS Origin** \> **Mitigation Settings**.

3.  On the **Cross-Border Traffic Blocking** tab, select the region where the Anti-DDoS Origin Enterprise instance resides and the instance that you want to manage.

4.  In the protected asset list, find the IP address that you want to manage and enable the feature.

    You can use one of the following methods to enable the feature:

    -   For an IP address: Find the IP address and turn on **Region Blocking**.
    -   For multiple IP addresses: Select the IP addresses and click **Batch Enable**.
5.  In the **Configure Blocking Period** dialog box, select a duration and click **OK**.

    Valid values: 30 minutes to 1 day.

    **Note:** The blocking period cannot be modified after it is applied. If you need to modify the blocking period, you must disable the cross-border traffic blocking feature and configure the blocking period again.

    After the preceding settings are completed, **Region Blocking** for the IP address is turned on, and the feature takes effect immediately. In the protected asset list, you can view the **Start Time** and **End Time** of the blocking period.

    After the blocking period ends, the feature no longer blocks cross-border traffic, and **Region Blocking** for the IP address is turned off.


## Manually disable cross-border traffic blocking

You can manually disable the cross-border traffic blocking feature during the blocking period.

**Note:** If this feature is enabled for an IP address, you cannot remove the IP address from the Anti-DDoS Origin Enterprise instance during the blocking period. To remove the IP address, you must disable the feature.

1.  Log on to the [Anti-DDoS console](https://yundun.console.aliyun.com/?p=ddos).

2.  In the left-side navigation pane, choose **Anti-DDoS Origin** \> **Mitigation Settings**.

3.  On the **Cross-Border Traffic Blocking** tab, select the region where the Anti-DDoS Origin Enterprise instance resides and the instance that you want to manage.

4.  In the protected asset list, find the IP address that you want to manage and disable the feature.

    You can use one of the following methods to disable the feature:

    -   For an IP address: Find the IP address and turn off **Region Blocking**.
    -   For multiple IP addresses: Select the IP addresses and click **Batch Disable**.
5.  In the dialog box that appears, click **OK**.

    After the preceding settings are completed, **Region Blocking** for the IP address is turned off, and the feature no longer blocks cross-border traffic.


