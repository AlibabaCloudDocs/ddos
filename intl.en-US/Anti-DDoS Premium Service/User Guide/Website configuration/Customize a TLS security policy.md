# Customize a TLS security policy {#task_960830 .task}

Anti-DDoS Premium allows you to customize TLS security policies. You can select an appropriate TLS protocol as needed.

-   Your website has been associated with an Anti-DDoS Premium instance of the enhanced function plan.
-   You have added and configured a website that supports HTTPS. For more information about how to add and configure a website, see [Associate a website business with Anti-DDoS Premium for protection](reseller.en-US/Anti-DDoS Premium Service/Quick Start/Associate a website business with Anti-DDoS Premium for protection.md#).
-   You have uploaded the corresponding SSL certificate. For more information about how to upload an SSL certificate, see [Upload an SSL certificate](reseller.en-US/Anti-DDoS Premium Service/User Guide/Website configuration/Upload an SSL certificate.md#).

If your business needs to comply with PCI DSS 3.2, you must disable the TLS 1.0 protocol. However, the Web server of another business only supports the TLS 1.0 protocol, the TLS 1.0 must be enabled for this business. In this case, you can customize the TLS security policies for different businesses as needed.

1.  Log on to the [Anti-DDoS Premium console](https://yundun.console.aliyun.com/?p=ddosdip).
2.  In the left-side navigation pane, choose **Provisioning** \> **Website**.
3.  Click **TLS Security Policy** in the Certificate Status column corresponding to the added website.
4.  In the **TLS Security Settings** dialog box that appears, set **TLS Versions** and **Cipher Suites**. 

    -   **TLS Versions:** The default value is **TLS 1.0 and later versions. This setting provides the best compatibility but a low security level**. You can select V1.1 or V1.2 and later as needed.
    -   **Cipher Suites:** 
        -   **Strong cipher suites. This setting provides a high security level but a low compatibility.** 

            Only the following strong cipher suites are supported:

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

            In addition to the preceding strong cipher suites, the following four weak cipher suites are also supported:

            -   RSA-AES256-CBC-SHA
            -   RSA-AES128-CBC-SHA
            -   ECDHE-RSA-3DES-EDE-CBC-SHA
            -   RSA-3DES-EDE-CBC-SHA
    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/776342/156436735750665_en-US.png)


