# View the duration of blackhole filtering

If blackhole filtering is triggered on a server that encounters distributed denial of service \(DDoS\) attacks, access to the public IP address of the server is blocked for a specific duration and resumes after the duration expires. The default duration of blackhole filtering varies based on the region where an asset resides. The actual duration varies based on the severity of attacks that the asset encounters. You can view the actual duration for your asset in the Anti-DDoS console.

The default duration of blackhole filtering is 2.5 hours. The actual duration varies from 30 minutes to 24 hours based on the attack severity. The duration for blackhole filtering changes based on the following factors:

-   The duration of attacks. If an attack lasts for a long time, the duration of blackhole filtering is extended.
-   The frequency of attacks. The first time an asset encounters an attack, the duration of blackhole filtering is shortened. If the asset is frequently attacked, it may suffer from continuous attacks. In this case, the duration of blackhole filtering is extended.

The actual duration and blackhole triggering threshold in the Anti-DDoS console shall prevail. To view the information, perform the operations in this topic.

**Note:**

-   If an asset triggers blackhole filtering too frequently, Alibaba Cloud may further extend the duration of blackhole filtering and lower the threshold to trigger blackhole filtering for the asset.
-   Blackhole filtering is a service that Internet service providers \(ISPs\) provide for Alibaba Cloud. ISPs have strict limits on the time to deactivate blackhole filtering. In most cases, the duration of blackhole filtering is greater than or equal to 30 minutes. In addition, the duration is automatically adjusted as the security credit score of your account changes.

For more information about the blackhole filtering policy of Alibaba Cloud, see [Blackhole filtering policy of Alibaba Cloud](/intl.en-US/DDoS Protection Guide/Product Introduction/Blackhole filtering policy of Alibaba Cloud.md).

1.  Log on to the [Anti-DDoS console](https://yundun.console.aliyun.com/?p=ddos).

2.  In the upper-left corner of the top navigation bar, select a region.

3.  On the **Assets** page, view the protection descriptions in the **DDoS Attack Protection Information** section.

    The time that follows **Blackholing Disabled At** in the **DDoS Attack Protection Information** section indicates the duration of blackhole filtering for assets in the current region.

    ![Duration of blackhole filtering](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/1478248951/p34127.png)


