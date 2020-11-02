# View mitigation reports

After you enable the mitigation analysis feature, you can view mitigation reports on the DDoS BGP Mitigation Report and DDoS BGP Events Report tabs.

The mitigation analysis feature is enabled. For more information, see [Enable mitigation analysis](/intl.en-US/Anti-DDoS Origin User Guide/Mitigation analysis (public preview)/Enable mitigation analysis.md).

## Procedure

1.  Log on to the [Anti-DDoS console](https://yundun.console.aliyun.com/?p=ddos).

2.  In the upper-left corner of the top navigation bar, select a region.

3.  In the left-side navigation pane, choose **Anti-DDoS Origin** \> **Mitigation Analysis \(Beta\)**.

4.  On the **Mitigation Analysis \(Beta\)** page, select an Anti-DDoS Origin Enterprise instance and click **Mitigation Reports**.

    **Note:** To view the mitigation reports, you must turn on **Status** for the mitigation analysis feature. For more information about how to enable the feature, see [Enable mitigation analysis](/intl.en-US/Anti-DDoS Origin User Guide/Mitigation analysis (public preview)/Enable mitigation analysis.md).

    ![Mitigation Reports](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/3378034061/p170885.png)

5.  Click the tab for a report that you want to view. The tabs include:

    -   **DDoS BGP Mitigation Report**: records Inbound Traffic Monitor, Inbound Traffic Monitor \(sort by scrubbing centers\), Inbound Traffic Monitor \(sort by flow types\), PktChk, syn cookie, SrcChk, FDR, DipRate, SrcRate, L7 Filter, L4 Filter, DFPDR, DnsChk, IpDR, AntiTcp, AntiUdp, and AntiOtherTcp.
    -   **DDoS BGP Events Report**: records statistics on DDoS events.
6.  In the upper-right corner of the page, click **Please Select** and set a time range for query.

    You can specify a relative time range, time frame, or custom time range.

    **Note:** The query results contain reports that are generated 1 minute earlier or later than the specified time range.

7.  View the mitigation reports.


