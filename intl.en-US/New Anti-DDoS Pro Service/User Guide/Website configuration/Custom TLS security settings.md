# Custom TLS security settings {#task_960830 .task}

The new Anti-DDoS Pro supports custom TLS security settings and allows you to choose TLS protocols based on your business needs.

-   Your website has been associated with an Anti-DDoS Pro instance of the enhanced package.
-   You have added your domain in the Anti-DDoS Pro console and your website supports HTTPS. For more information about adding domains, see [Step 1: Add a website](reseller.en-US/New Anti-DDoS Pro Service/Quick Start/Set up Anti-DDoS Pro using domains/Step 1: Add a website.md#).
-   You have uploaded the corresponding SSL certificates in the console. For more information, see [Upload SSL certificates](reseller.en-US/New Anti-DDoS Pro Service/User Guide/Website configuration/Upload SSL certificates.md#).

If one of your service needs to implement an authentication mechanism that is compliant with PCI DSS 3.2, TLS 1.0 must be disabled. However, if your clients only support TLS 1.0, your service must also support TLS 1.0. Anti-DDoS Pro allows you to configure different TLS security settings for different services.

1.  Log on to the [new Anti-DDoS Pro console](https://partners-yundunnext.console.aliyun.com/?p=ddoscoo).
2.  In the left-side navigation pane, choose **Management** \> **Websites**.
3.  Select a domain and click **TLS Security Settings** under the Certificate Status column. 

    ![](images/50664_en-US.png)

4.  In the **TLS Security Settings** dialog box, select **TLS Versions** and **Cipher Suites** based on your needs. 

    -   **TLS Versions**: Default is **TLS 1.0 and later versions. This setting provides the best compatibility but a low security level.** You can choose to support TLS 1.1 or TLS 1.2 and later versions based on your needs.
    -   **Cipher Suites**:
        -   **Strong cipher suites. This setting provides a high security level but a low compatibility.** 

            Supported strong cipher suites are as follows:

            -   ECDHE-ECDSA-AES256-GCM-SHA384
            -   ECDHE-RSA-AES256-GCM-SHA384
            -   ECDHE-ECDSA-AES128-GCM-SHA256
            -   ECDHE-RSA-AES128-GCM-SHA256
            -   ECDHE-ECDSA-WITH-CHACHA20-POLY1305
            -   ECDHE-RSA-WITH-CHACHA20-POLY1305
            -   ECDHE-RSA-AES256-CBC-SHA
            -   ECDHE-RSA-AES128-CBC-SHA
            -   ECDHE-ECDSA-AES256-CBC-SHA
            -   ECDHE-ECDSA-AES128-CBC-SHA
        -   **All cipher suites. This setting provides a low security level but a high compatibility.** 

            The following weak cipher suites are also supported in addition to above strong cipher suites.

            -   RSA-AES256-CBC-SHA
            -   RSA-AES128-CBC-SHA
            -   ECDHE-RSA-3DES-EDE-CBC-SHA
            -   RSA-3DES-EDE-CBC-SHA
    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/776342/156747945650665_en-US.png)


