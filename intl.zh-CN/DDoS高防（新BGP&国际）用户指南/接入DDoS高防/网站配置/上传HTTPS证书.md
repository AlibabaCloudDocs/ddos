# 上传HTTPS证书

要使DDoS高防帮助您清洗HTTPS业务流量，您必须在网站配置中选择HTTPS协议并上传HTTPS证书。已上传证书发生变化时，您也要在DDoS高防控制台及时更新证书。

-   已添加网站配置且网站支持HTTPS协议。更多信息，请参见[添加网站](/intl.zh-CN/DDoS高防（新BGP&国际）用户指南/接入DDoS高防/网站配置/添加网站.md)。
-   已准备好证书文件内容。

    如果您已将证书文件上传到[SSL证书服务控制台](https://yundunnext.console.aliyun.com/?p=casnext)进行统一管理，那么在上传证书时您可以直接选择已有证书，否则您需要准备好网站的证书和私钥文件。您需要准备的证书相关内容包括：

    -   公钥文件（CRT格式）或者证书文件（PEM格式）
    -   私钥文件（KEY格式）

## 应用场景

您需要在以下场景中上传HTTPS证书：

-   接入域名时，域名的协议是HTTPS协议。
-   接入HTTPS协议的域名后，已上传的证书需要更换或因为证书过期需要更新。

## 操作步骤

1.  登录[DDoS高防控制台](https://yundun.console.aliyun.com/?p=ddoscoo)。

2.  在顶部菜单栏左上角处，选择服务所在地域：

    -   **中国内地**：选择该地域将跳转到**DDoS高防（新BGP）**控制台。
    -   **非中国内地**：选择该地域将跳转到**DDoS高防（国际）**控制台。
    您可以通过切换地域分别管理和配置DDoS高防（新BGP）和DDoS高防（国际）实例。在使用DDoS高防服务时，请确认您已选择正确的地域。

3.  在左侧导航栏，选择**接入管理** \> **域名接入**。

4.  在域名接入页面，定位到要操作的域名，单击**证书状态**列下的上传图标。

    ![证书状态](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/4641919951/p45762.png)

5.  在上传证书和私钥对话框，选择一种**上传方式**，并完成上传配置。

    可选择的上传方式包括：

    -   （推荐）**选择已有证书**

        如果您的网站证书已经上传并托管在SSL证书服务中，您可以直接从已有证书中选择证书并上传。

        ![选择已有证书](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/4641919951/p45763.png)

        即使您的证书未托管在SSL证书服务，您也可以单击**前往SSL证书控制台管理**，上传并管理您的证书，然后再选择已有证书。关于如何在SSL证书服务控制台上传证书，请参见[上传证书](/intl.zh-CN/证书管理/上传证书.md)。

    -   **手动上传**

        填写**证书名称**，并将证书文件和私钥文件中的文本内容分别复制粘贴到**证书文件**和**私钥文件**框中。

        ![手动上传](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/4641919951/p45764.png)

        **说明：**

        -   对于PEM、CER、CRT格式的证书，您可以使用文本编辑器直接打开证书文件，复制其中的文本内容。对于其他格式（例如，PFX、P7B等）的证书，您需要将证书文件转换成PEM格式后，才能用文本编辑器打开并复制其中的文本内容。关于证书格式的转换方式，请参见[HTTPS证书转换成PEM格式]()。
        -   如果该HTTPS证书有多个证书文件（例如，证书链），您需要将证书文件中的文本内容拼接合并后粘贴至**证书文件**中。
        证书文件文本内容样例：

        ```
        -----BEGIN CERTIFICATE----- 
        xxxxxxxxxxxxvs6MTXcJSfN9Z7rZ9fmxWr2BFN2XbahgnsSXM48ixZJ4krc+1M+j2kcubVpsE2cgHdj4v8H6jUz9Ji4mr7vMNS6dXv8PUkl/qoDeNGCNdyTS5NIL5ir+g92cL8IGOkjgvhlqt9vc65Cgb4mL+n5+DV9uOyTZTW/MojmlgfUekC2xiXa54nxJf17Y1TADGSbyJbsC0Q9nIrHsPl8YKkvRWvIAqYxXZ7wRwWWmv4TMxFhWRiNY7yZIo2ZUhl02SIDNggIEeg==
        -----END CERTIFICATE-----
        ```

        私钥文件文本内容样例：

        ```
        -----BEGIN RSA PRIVATE KEY-----
        xxxxxxxxxxxxtZ3UKHJTRgNQmioPQn2bqdKHop+B/dn/4VZL7Jt8zSDGM9sTMThLyvsmLQKBgQCr+ujntC1kN6pGBj2Fw2l/EA/W3rYEce2tyhjgmG7rZ+A/jVE9fld5sQra6ZdwBcQJaiygoIYoaMF2EjRwc0qwHaluq0C15f6ujSoHh2e+D5zdmkTg/3NKNjqNv6xA2gYpinVDzFdZ9Zujxvuh9o4Vqf0YF8bv5UK5G04RtKadOw==
        -----END RSA PRIVATE KEY-----
        ```

6.  单击**确定**。

    成功上传证书后，**证书状态**会变更为**正常**。

    ![修改证书](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/5928947061/p190386.png)

    如果证书发生更新，您必须及时在[DDoS高防控制台](https://yundun.console.aliyun.com/?p=ddoscoo)的**域名接入**页面修改证书（单击证书后的![修改](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/5928947061/p190391.png)图标），上传更新后的证书。

    **警告：** 如果证书已经更新，却没有在DDoS高防控制台修改证书，将会导致HTTPS业务解析异常。


## 相关FAQ

[上传HTTPS证书提示“参数错误”]()

