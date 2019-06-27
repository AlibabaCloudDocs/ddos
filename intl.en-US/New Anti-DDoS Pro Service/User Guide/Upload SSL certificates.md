# Upload SSL certificates {#task_221116 .task}

To use Anti-DDoS Pro to filter HTTPS traffic, you must select HTTPS in the domain settings and upload the SSL certificate. When your SSL certificate expires, you must update the certificate in the Anti-DDoS Pro console in a timely manner.

-   You have added your domain in the Anti-DDoS Pro console and your site supports HTTPS. For more information about adding domains, see [Step 1: Add a website](reseller.en-US/New Anti-DDoS Pro Service/Quick Start/Set up Anti-DDoS Pro using domains/Step 1: Add a website.md#).
-   You have prepared the certificate files.

    If you have uploaded your certificate files to [Alibaba Cloud SSL Certificates Service](https://partners-yundunnext.console.aliyun.com/?p=casnext), you can select the certificate directly. Otherwise, you need to prepare the certificate files for upload. Generally, the following files are required:

    -   The public key file in CRT format or the certificate file in PEM format.
    -   The private key file in KEY format.

1.   Log on to the [Anti-DDoS Pro console](https://partners-yundunnext.console.aliyun.com/?p=ddoscoo). 
2.   In the left-side navigation pane, choose **Management** \> **Websites**. 
3.   In the Websites list, select your domain and click the upload icon in the **Certificate Status** column.![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/188520/156160009645762_en-US.png)

  
4.   In the Upload SSL Certificate and Private Key dialog box, select an **Upload Method** and specify the parameters. You can select from one of the following methods to upload your certificate. 
    -    **Select Existing Certificates** \(Recommended\)

        If you have uploaded your SSL certificate to Alibaba Cloud SSL Certificates Service, you can directly select an existing certificate for upload.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/188520/156160009745763_en-US.png)

        If your certificate is not hosted on SSL Certificates Service, you can click **Go to the SSL Certificates console** to upload your certificate first. For more information about uploading certificates to SSL Certificates Service, see [Upload certificates](../../../../reseller.en-US/User Guide/Upload certificates.md#).

    -    **Manual Upload** 

        Enter a **Certificate Name**, and copy the contents of the certificate file and private key file to the **Certificate File** field and **Private Key** field respectively.

        **Note:** 

        -   For certificate files in common formats, such as PEM, CER, and CRT, you can use a text editor to open the file and copy its contents. For certificate files in other formats, such as PFX and P7B, you need to convert the file into PEM format first.
        -   If your SSL certificate includes multiple certificate files, such as a certificate chain, you need to combine the contents of multiple certificate files and paste them into the **Certificate File** field.
        Certificate file example

        ``` {#codeblock_7kx_qhu_25z}
        -----BEGIN CERTIFICATE----- 
        xxxxxxxxxxxxvs6MTXcJSfN9Z7rZ9fmxWr2BFN2XbahgnsSXM48ixZJ4krc+1M+j2kcubVpsE2cgHdj4v8H6jUz9Ji4mr7vMNS6dXv8PUkl/qoDeNGCNdyTS5NIL5ir+g92cL8IGOkjgvhlqt9vc65Cgb4mL+n5+DV9uOyTZTW/MojmlgfUekC2xiXa54nxJf17Y1TADGSbyJbsC0Q9nIrHsPl8YKkvRWvIAqYxXZ7wRwWWmv4TMxFhWRiNY7yZIo2ZUhl02SIDNggIEeg==
        -----END CERTIFICATE-----
        ```

        Private key file example

        ``` {#codeblock_5qj_l6u_jhb}
        -----BEGIN RSA PRIVATE KEY-----
        xxxxxxxxxxxxtZ3UKHJTRgNQmioPQn2bqdKHop+B/dn/4VZL7Jt8zSDGM9sTMThLyvsmLQKBgQCr+ujntC1kN6pGBj2Fw2l/EA/W3rYEce2tyhjgmG7rZ+A/jVE9fld5sQra6ZdwBcQJaiygoIYoaMF2EjRwc0qwHaluq0C15f6ujSoHh2e+D5zdmkTg/3NKNjqNv6xA2gYpinVDzFdZ9Zujxvuh9o4Vqf0YF8bv5UK5G04RtKadOw==
        -----END RSA PRIVATE KEY-----
        ```

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/188520/156160009745764_en-US.png)

5.   Click **OK**. 

After the upload is complete, the certificate status is updated.

