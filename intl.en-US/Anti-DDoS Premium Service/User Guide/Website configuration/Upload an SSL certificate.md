# Upload an SSL certificate {#task_221116 .task}

To use Anti-DDoS Premium to scrub HTTPS traffic, you must select HTTPS on the Website Configuration page, and upload the SSL certificate. When your SSL certificate changes, you must update the certificate in the Anti-DDoS Premium console in a timely manner.

-   You have added and configured a website that supports HTTPS. For more information about how to add and configure a website, see [Associate a website business with Anti-DDoS Premium for protection](reseller.en-US/Anti-DDoS Premium Service/Quick Start/Associate a website business with Anti-DDoS Premium for protection.md#).
-   You have prepared the certificate files.

    If you have uploaded your certificate files to [Alibaba Cloud SSL Certificates Service](https://partners-yundunnext.console.aliyun.com/?p=casnext), you can select the certificate directly. Otherwise, you need to prepare and upload the certificate files and private key files. The following files are required:

    -   The public key file in CRT format or the certificate file in PEM format
    -   The private key file in KEY format

1.  Log on to the [Anti-DDoS Premium console](https://yundun.console.aliyun.com/?p=ddosdip).
2.  In the left-side navigation pane, choose **Provisioning** \> **Website**.
3.  On the Website tab, click the upload icon in the **Certificate Status** column corresponding to the website to upload a certificate for. 

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/830179/156436708551000_en-US.png)

4.  In the Upload SSL Certificate and Private Key dialog box that appears, set **Upload Method** and the corresponding parameters. You can select either of the following methods to upload your certificate. 
    -   **Select Existing Certificates** \(Recommended\)

        If you have uploaded your certificate files to Alibaba Cloud SSL Certificates Service, you can directly select and upload an existing certificate.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/188520/156436708545763_en-US.png)

        If your certificate files have not been uploaded to SSL Certificates Service, you can click **Go to the SSL Certificates console** to upload your certificate first. For more information about how to upload certificates to SSL Certificates console, see [Upload certificates](../../../../../reseller.en-US/User Guide/Upload certificates.md#).

    -   **Manual Upload** 

        Set **Certificate Name**, and copy the content of the certificate file to the **Certificate File** field and the content of the private key file to the **Private Key** field.

        **Note:** 

        -   If the certificate file is in PEM, CER, or CRT formats, you can use a text editor to open the file and copy its content. If the certificate file is in another format such as PFX and P7B, you need to convert the file format into PEM before you can use a text editor to open it and copy its content.
        -   If your SSL certificate has multiple certificate files, such as a certificate chain, you need to combine the content of multiple certificate files and paste the content to the **Certificate File** field.
        Example of a certificate file:

        ``` {#codeblock_7kx_qhu_25z}
        -----BEGIN CERTIFICATE----- 
        xxxxxxxxxxxxvs6MTXcJSfN9Z7rZ9fmxWr2BFN2XbahgnsSXM48ixZJ4krc+1M+j2kcubVpsE2cgHdj4v8H6jUz9Ji4mr7vMNS6dXv8PUkl/qoDeNGCNdyTS5NIL5ir+g92cL8IGOkjgvhlqt9vc65Cgb4mL+n5+DV9uOyTZTW/MojmlgfUekC2xiXa54nxJf17Y1TADGSbyJbsC0Q9nIrHsPl8YKkvRWvIAqYxXZ7wRwWWmv4TMxFhWRiNY7yZIo2ZUhl02SIDNggIEeg==
        -----END CERTIFICATE-----
        ```

        Example of a private key file:

        ``` {#codeblock_5qj_l6u_jhb}
        -----BEGIN RSA PRIVATE KEY-----
        xxxxxxxxxxxxtZ3UKHJTRgNQmioPQn2bqdKHop+B/dn/4VZL7Jt8zSDGM9sTMThLyvsmLQKBgQCr+ujntC1kN6pGBj2Fw2l/EA/W3rYEce2tyhjgmG7rZ+A/jVE9fld5sQra6ZdwBcQJaiygoIYoaMF2EjRwc0qwHaluq0C15f6ujSoHh2e+D5zdmkTg/3NKNjqNv6xA2gYpinVDzFdZ9Zujxvuh9o4Vqf0YF8bv5UK5G04RtKadOw==
        -----END RSA PRIVATE KEY-----
        ```

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/188520/156436708545764_en-US.png)

5.  Click **OK**.

After the upload is complete, the certificate status is updated.

