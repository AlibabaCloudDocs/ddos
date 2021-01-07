# Upload an HTTPS certificate

To use Anti-DDoS Pro or Anti-DDoS Premium to scrub HTTPS traffic, you must select HTTPS and upload an HTTPS certificate when you add the domain name of a website. If the uploaded HTTPS certificate changes, you must update the certificate in the Anti-DDoS Pro or Anti-DDoS Premium console.

-   A website that supports HTTPS is added to Anti-DDoS Pro or Anti-DDoS Premium. For more information, see [Add a website](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Use domains/Add a website.md).
-   The certificate file of the website is prepared.

    If you have uploaded the certificate file to the [SSL Certificates Service console](https://yundunnext.console.aliyun.com/?p=casnext), you can select the certificate. Otherwise, you must upload your own certificate and private key files. The following files are required:

    -   The public key file in the CRT format or the certificate file in the PEM format
    -   The private key file in the KEY format

## Scenarios

You must upload the HTTPS certificate in the following scenarios:

-   You select HTTPS when you add a domain name to Anti-DDoS Pro or Anti-DDoS Premium.
-   You select HTTPS when you add a domain name to Anti-DDoS Pro or Anti-DDoS Premium and upload a certificate. You need to replace the uploaded certificate or update the certificate when it expires.

## Procedure

1.  Log on to the [Anti-DDoS Pro console](https://yundun.console.aliyun.com/?p=ddoscoo).

2.  In the top navigation bar, select the region where your instance resides.

    -   **Mainland China**: If you select this region, the **Anti-DDoS Pro console** appears.
    -   **Outside Mainland China**: If you select this region, the **Anti-DDoS Premium console** appears.
    You can switch the region to configure and manage Anti-DDoS Pro or Anti-DDoS Premium instances. Make sure that you select the required region when you use Anti-DDoS Pro or Anti-DDoS Premium.

3.  In the left-side navigation pane, choose **Provisioning** \> **Website Config**.

4.  On the Website Config page, find the domain name for which you want to upload a certificate, and click the upload icon in the **Certificate Status** column.

    ![Certificate status](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/2097449951/p45762.png)

5.  In the Upload SSL Certificate and Private Key dialog box, set **Upload Method** and configure other parameters.

    You can use one of the following methods to upload your certificate:

    -   **Select Existing Certificates** \(recommended\)

        If you have uploaded the certificate to SSL Certificates Service, you can select the certificate and upload it to Anti-DDoS Pro or Anti-DDoS Premium.

        ![Select Existing Certificates](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/2097449951/p45763.png)

        If you have not uploaded the certificate to SSL Certificates Service, you can click **Go to the SSL Certificates console** to upload your certificate. For more information about how to upload certificates to SSL Certificates Service, see [Upload certificates](/intl.en-US/Manage the certificates/Upload certificates.md).

    -   **Manual Upload**

        Specify **Certificate Name**, copy and paste the content of the certificate file to the **Certificate File** field, and then copy and paste the content of the private key file to the **Private Key** field.

        ![Manual Upload](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/2097449951/p45764.png)

        **Note:**

        -   If the certificate file is in the PEM, CER, or CRT format, you can use a text editor to open the certificate file and copy the file content. If the certificate file is in other formats, such as PFX and P7B, you must convert the file into the PEM format and use a text editor to open the file and copy the file content. For information about how to convert the format of a certificate file, see [How do I convert an HTTPS certificate to the PEM format?]().
        -   If the certificate file has multiple certificates, such as a certificate chain, you must concatenate the content of these certificates and copy the concatenated content to the **Certificate File** field.
        Certificate file example

        ```
        -----BEGIN CERTIFICATE----- 
        xxxxxxxxxxxxvs6MTXcJSfN9Z7rZ9fmxWr2BFN2XbahgnsSXM48ixZJ4krc+1M+j2kcubVpsE2cgHdj4v8H6jUz9Ji4mr7vMNS6dXv8PUkl/qoDeNGCNdyTS5NIL5ir+g92cL8IGOkjgvhlqt9vc65Cgb4mL+n5+DV9uOyTZTW/MojmlgfUekC2xiXa54nxJf17Y1TADGSbyJbsC0Q9nIrHsPl8YKkvRWvIAqYxXZ7wRwWWmv4TMxFhWRiNY7yZIo2ZUhl02SIDNggIEeg==
        -----END CERTIFICATE-----
        ```

        Private key file example

        ```
        -----BEGIN RSA PRIVATE KEY-----
        xxxxxxxxxxxxtZ3UKHJTRgNQmioPQn2bqdKHop+B/dn/4VZL7Jt8zSDGM9sTMThLyvsmLQKBgQCr+ujntC1kN6pGBj2Fw2l/EA/W3rYEce2tyhjgmG7rZ+A/jVE9fld5sQra6ZdwBcQJaiygoIYoaMF2EjRwc0qwHaluq0C15f6ujSoHh2e+D5zdmkTg/3NKNjqNv6xA2gYpinVDzFdZ9Zujxvuh9o4Vqf0YF8bv5UK5G04RtKadOw==
        -----END RSA PRIVATE KEY-----
        ```

6.  Click **OK**.

    After the certificate is uploaded, the **Certificate Status** becomes **Normal**.

    ![Modify a certificate](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9890000161/p190386.png)

    If the certificate is updated, you must upload the updated certificate. To upload the certificate, log on to the [Anti-DDoS Pro](https://yundun.console.aliyun.com/?p=ddoscoo) console, click **Website Config**, and then click the ![Edit icon](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9890000161/p190391.png) icon next to the certificate to upload the updated certificate.

    **Warning:** If the certificate is updated but is not uploaded in the Anti-DDoS Pro or Anti-DDoS Premium console, HTTPS traffic cannot be forwarded to the origin server.


## FAQ

[How do I handle the error "The specified parameter is invalid" reported when I upload an HTTPS certificate?]()

