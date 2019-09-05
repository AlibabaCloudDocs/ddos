# ConfigDomainAccessMode {#doc_api_ddoscoo_ConfigDomainAccessMode .reference}

调用ConfigDomainAccessMode设置域名接入模式。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=ddoscoo&api=ConfigDomainAccessMode&type=RPC&version=2017-12-28)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|AccessMode|Integer|是|2|接入模式，取值：

 -   **0**：A记录
-   **1**：高防
-   **2**：回源

 |
|Action|String|是|ConfigDomainAccessMode|系统规定参数。取值：**ConfigDomainAccessMode**。

 |
|Domain|String|是|www.aliyun.com|要操作的域名。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|CF33B4C3-196E-4015-AADD-5CAD00057B80|本次请求的ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=ConfigDomainAccessMode
&AccessMode=2
&Domain=www.aliyun.com
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<ConfigDomainAccessModeResponse>
     <RequestId>0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc</RequestId>
</ConfigDomainAccessModeResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/ddoscoo)查看更多错误码。

