# 自定义TLS安全策略

DDoS高防支持TLS安全策略自定义功能，您可以根据实际业务需要选择合适的TLS协议版本和加密算法套件。

-   已添加网站配置，且网站配置关联了增强功能套餐的DDoS高防实例。更多信息，请参见[添加网站](/cn.zh-CN/DDoS高防（新BGP&国际）用户指南/接入DDoS高防/域名接入/添加网站.md)。
-   网站配置的**协议类型**包含**HTTPS**，且已上传对应的HTTPS证书。更多信息，请参见[上传HTTPS证书](/cn.zh-CN/DDoS高防（新BGP&国际）用户指南/接入DDoS高防/域名接入/上传HTTPS证书.md)。

如果您的业务需要通过PCI DSS 3.2认证，希望禁用TLS 1.0协议。同时，您的另一个业务的访问终端仅支持TLS 1.0协议，需要兼容TLS 1.0协议。这种情况下，您可以通过TLS安全策略自定义功能为不同业务灵活配置所需的TLS安全策略。

## 操作步骤

1.  登录[DDoS高防控制台](https://yundun.console.aliyun.com/?p=ddoscoo)。

2.  在顶部菜单栏左上角处，选择服务所在地域：

    -   **中国内地**：选择该地域将跳转到**DDoS高防（新BGP）**控制台。
    -   **非中国内地**：选择该地域将跳转到**DDoS高防（国际）**控制台。
    您可以通过切换地域分别管理和配置DDoS高防（新BGP）和DDoS高防（国际）实例。在使用DDoS高防服务时，请确认您已选择正确的地域。

3.  在左侧导航栏，选择**接入管理** \> **域名接入**。

4.  定位到要操作的域名，单击**证书状态**列中的**TLS安全策略**。

    ![TLS安全策略](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/5641919951/p50664.png)

5.  在**TLS安全策略配置**对话框，配置**TLS版本**和**加密套件**。

    ![TLS安全策略配置](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/6827501161/p50665.png)

    |参数|说明|
    |--|--|
    |**TLS版本**|选择HTTPS支持的TLS协议版本。可选项：    -   **支持TLS1.0及以上版本，兼容性最好，安全性较低**（默认）：支持TLS 1.0、TLS 1.1和TLS 1.2。
    -   **支持TLS1.1及以上版本，兼容性较好，安全性较好**：支持TLS 1.1和TLS 1.2。
    -   **支持TLS1.2及以上版本，兼容性较好，安全性很高**：支持TLS 1.2。
您也可以根据需要选择**开启支持TLS1.3**。 |
    |**加密套件**|选择HTTPS支持的加密套件。可选项：**说明：** 您可以将光标放置在某个加密套件选项上的![问号](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/6827501161/p226604.png)图标，查看该选项包含的加密套件。

    -   **全部加密套件，安全性较低，兼容性较高**（默认）

该选项包含以下加密套件：

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
    -   **强加密套件，安全性较高，兼容性较低**：只有在**TLS版本**为**支持TLS1.2及以上版本，兼容性较好，安全性很高**时，支持该选项。

该选项包含以下加密套件：

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
    -   **自定义加密套件**：选择该选项后，您需要从全部加密套件中选择一个或多个加密套件。 |

6.  单击**确定**。


