# Create a custom TLS policy

Anti-DDoS Pro and Anti-DDoS Premium allow you to create custom Transport Layer Security \(TLS\) policies. You can choose TLS protocol versions and cipher suites based on your business requirements.

-   A website is added to an Anti-DDoS Pro or Anti-DDoS Premium instance that uses the Enhanced function plan. For more information, see [Add a website](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Use domains/Add a website.md).
-   The website supports HTTPS, and the required HTTPS certificate is uploaded. For more information, see [Upload an HTTPS certificate](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Use domains/Upload an HTTPS certificate.md).

If one of your services needs to comply with PCI DSS 3.2, you must disable TLS 1.0 for the service. However, terminals that access other services support only TLS 1.0. In this case, you can customize TLS policies for different services.

## Procedure

1.  Log on to the [Anti-DDoS Pro console](https://yundun.console.aliyun.com/?p=ddoscoo).

2.  In the top navigation bar, select the region where your instance resides.

    -   **Mainland China**: If you select this region, the **Anti-DDoS Pro console** appears.
    -   **Outside Mainland China**: If you select this region, the **Anti-DDoS Premium console** appears.
    You can switch the region to configure and manage Anti-DDoS Pro or Anti-DDoS Premium instances. Make sure that you select the required region when you use Anti-DDoS Pro or Anti-DDoS Premium.

3.  In the left-side navigation pane, choose **Provisioning** \> **Website Config**.

4.  Find the domain name that you want to configure and click **TLS Security Settings** in the **Certificate Status** column.

    ![TLS Security Settings](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/3097449951/p50664.png)

5.  In the **TLS Security Settings** dialog box, configure **TLS Versions** and **Cipher Suites**.

    ![TLS Security Settings](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6958121161/p50665.png)

    |Parameter|Description|
    |---------|-----------|
    |**TLS Versions**|Select TLS protocol versions that HTTPS supports. Valid values:    -   **TLS1.0 and later versions. This setting provides the best compatibility but a low security level.**: TLS 1.0, TLS 1.1, and TLS 1.2. This is the default value.
    -   **TLS1.1 and later versions. This setting provides a good compatibility and a medium security level.**: TLS 1.1 and TLS 1.2.
    -   **TLS1.2 and later versions. This setting provides a good compatibility and a high security level.**: TLS 1.2.
You can also click **Enable TLS 1.3** based on your business requirements. |
    |**Cipher Suites**|Select cipher suites that HTTPS supports. Valid values:**Note:** You can move your pointer over the ![Question mark icon](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/5613712161/p226604.png) icon of a cipher suite option to view the cipher suites contained in this option.

    -   **All cipher suites. This setting provides a low security level but a high compatibility.**

This option contains the following cipher suites:

        -   ECDHE-ECDSA-AES128-GCM-SHA256
        -   ECDHE-ECDSA-AES256-GCM-SHA384
        -   ECDHE-ECDSA-AES128-SHA256
        -   ECDHE-ECDSA-AES256-SHA384
        -   ECDHE-RSA-AES128-GCM-SHA256
        -   ECDHE-RSA-AES256-GCM-SHA384
        -   ECDHE-RSA-AES128-SHA256
        -   ECDHE-RSA-AES256-SHA384
        -   AES128-GCM-SHA256
        -   AES256-GCM-SHA384
        -   AES128-SHA256 AES256-SHA256
        -   ECDHE-ECDSA-AES128-SHA
        -   ECDHE-ECDSA-AES256-SHA
        -   ECDHE-RSA-AES128-SHA
        -   ECDHE-RSA-AES256-SHA
        -   AES128-SHA AES256-SHA
        -   DES-CBC3-SHA
    -   **Strong cipher suites. This setting provides a high security level but a low compatibility.**: This option is available only when the **TLS Versions** is set to **TLS1.2 and later versions. This setting provides a good compatibility and a high security level.**

This option contains the following cipher suites:

        -   ECDHE-ECDSA-AES128-GCM-SHA256
        -   ECDHE-ECDSA-AES256-GCM-SHA384
        -   ECDHE-ECDSA-AES128-SHA256
        -   ECDHE-ECDSA-AES256-SHA384
        -   ECDHE-RSA-AES128-GCM-SHA256
        -   ECDHE-RSA-AES256-GCM-SHA384
        -   ECDHE-RSA-AES128-SHA256
        -   ECDHE-RSA-AES256-SHA384
        -   ECDHE-ECDSA-AES128-SHA
        -   ECDHE-ECDSA-AES256-SHA
    -   **Selecting Your Cipher Suites**: If you select this option, you must select one or more cipher suites from all cipher suites. |

6.  Click **OK**.


