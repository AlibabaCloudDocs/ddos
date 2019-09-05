# ConfigLayer7Cert {#doc_api_ddoscoo_ConfigLayer7Cert .reference}

调用ConfigLayer7Cert为指定域名配置7层证书。

设置证书。新BGP高防的证书上传功能已接入云盾证书服务，您可以直接调用该接口从证书服务拉取对应的证书上传到新BGP高防服务。当您选择重新上传一组证书和私钥时，我们会将您的这组证书和私钥重新上传到云盾证书服务，以便您可以重复使用这组证书。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=ddoscoo&api=ConfigLayer7Cert&type=RPC&version=2017-12-28)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|ConfigLayer7Cert|系统规定参数。取值：**ConfigLayer7Cert**。

 |
|Domain|String|是|www.aliyun.com|要操作的域名。

 |
|Cert|String|否|xx|证书公钥。

 **说明：** 若传入此参数，则必须同时传入**CertName**和**Key**。若传入**CertName**、**Cert**、**Key**组合，则无需传入**CertId**。

 |
|CertId|Integer|否|1234|证书ID。

 **说明：** 若传入此参数，则无需传入**CertName**、**Cert**、**Key**。

 |
|CertName|String|否|testCertName|证书名称。

 **说明：** 若传入此参数，则必须同时传入**Cert**和**Key**。若传入**CertName**、**Cert**、**Key**组合，则无需传入**CertId**。

 |
|Key|String|否|xx|证书私钥。

 **说明：** 若传入此参数，则必须同时传入**CertName**和**Cert**。若传入**CertName**、**Cert**、**Key**组合，则无需传入**CertId**。

 |
|ResourceGroupId|String|否|xx|资源组ID。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc|本次请求的ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=ConfigLayer7Cert
&Domain=www.aliyun.com
&CertId=1
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<ConfigLayer7CertResponse>
     <RequestId>0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc</RequestId>
</ConfigLayer7CertResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/ddoscoo)查看更多错误码。

