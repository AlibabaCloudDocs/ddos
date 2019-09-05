# ConfigLayer7BlackWhiteList {#doc_api_ddoscoo_ConfigLayer7BlackWhiteList .reference}

调用ConfigLayer7BlackWhiteList为指定域名设置7层防护黑白名单。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=ddoscoo&api=ConfigLayer7BlackWhiteList&type=RPC&version=2017-12-28)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|ConfigLayer7BlackWhiteList|系统规定参数。取值：**ConfigLayer7BlackWhiteList**。

 |
|Domain|String|是|www.aliyun.com|要配置的域名。

 |
|BlackList.N|RepeatList|否|1.1.1.1|黑名单列表。若有多个加黑地址，依次传入BlackList.1, BlackList.2, BlackList.3, ...

 |
|ResourceGroupId|String|否|test|资源组ID。

 |
|WhiteList.N|RepeatList|否|1.1.1.1|白名单列表。若有多个加白地址，依次传入WhiteList.1, WhiteList.2, WhiteList.3, ...

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|CF33B4C3-196E-4015-AADD-5CAD00057B80|本次请求的ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=ConfigLayer7BlackWhiteList
&Domain=www.aliyun.com
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<ConfigLayer7BlackWhiteListResponse>
     <RequestId>0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc</RequestId>
</ConfigLayer7BlackWhiteListResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/ddoscoo)查看更多错误码。

