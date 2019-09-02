# CheckGrant {#doc_api_ddosbgp_CheckGrant .reference}

调用CheckGrant接口检查防护包服务的授权状态，即是否授权防护包查询您的ECS服务器信息。

**说明：** DDoS防护包的API接口目前仅对企业版DDoS防护包用户开放。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=ddosbgp&api=CheckGrant&type=RPC&version=2018-07-20)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|CheckGrant|要执行的操作，取值：**CheckGrant**。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|E76E316C-697F-42D8-883A-D99864D2E77F|本次请求的ID。

 |
|Status|Integer|1|授权状态，取值：

 -   **1**：已授权DDoS防护包查询您的ECS服务器信息
-   **0**：未授权DDoS防护包查询您的ECS服务器信息

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=CheckGrant
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<CheckGrantResponse>
      <RequestId>E76E316C-697F-42D8-883A-D99864D2E77F</RequestId>
      <Status>1</Status>
</CheckGrantResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Status":1,
	"RequestId":"E76E316C-697F-42D8-883A-D99864D2E77F"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/ddosbgp)查看更多错误码。

