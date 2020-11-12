# DescribeSceneDefenseObjects

调用DescribeSceneDefenseObjects查询定制场景策略的防护对象。

关于定制场景策略的介绍，请参见[定制场景策略](~~148079~~)。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=ddoscoo&api=DescribeSceneDefenseObjects&type=RPC&version=2020-01-01)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeSceneDefenseObjects|要执行的操作。取值：**DescribeSceneDefenseObjects**。 |
|PolicyId|String|是|47e07ebd-0ba5-4afc-957b-59d15b90\*\*\*\*|要查询的策略ID。

 **说明：** 您可以调用[DescribeSceneDefensePolicies](~~159382~~)查询所有策略ID。 |
|RegionId|String|否|cn-hangzhou|DDoS高防服务地域ID。取值：

 -   **cn-hangzhou**：表示DDoS高防（新BGP）服务。
-   **ap-southeast-1**：表示DDoS高防（国际）服务。 |
|ResourceGroupId|String|否|rg-acfm2pz25js\*\*\*\*|DDoS高防实例在资源管理产品中所属的资源组ID。默认为空，即属于默认资源组。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|Objects|Array of Object| |定制场景策略的防护对象信息。 |
|Domain|String|\*\*\*.aliyun.com|该策略防护的域名。 |
|PolicyId|String|47e07ebd-0ba5-4afc-957b-59d15b90\*\*\*\*|定制场景策略的ID。 |
|Vip|String|203.\*\*\*.\*\*\*.119|该策略防护的高防实例IP。 |
|RequestId|String|FE07E73F-F19E-4A51-B62F-AC59E3B962D8|本次请求的ID。 |
|Success|Boolean|true|是否成功调用。取值：

 -   **true**：是
-   **false**：否 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=DescribeSceneDefenseObjects
&PolicyId=47e07ebd-0ba5-4afc-957b-59d15b90****
&<公共请求参数>
```

正常返回示例

`XML` 格式

```
<DescribeSceneDefenseObjectsResponse>
	  <RequestId>FE07E73F-F19E-4A51-B62F-AC59E3B962D8</RequestId>
	  <Objects>
		    <Domain>***.aliyun.com</Domain>
		    <PolicyId>47e07ebd-0ba5-4afc-957b-59d15b90****</PolicyId>
	  </Objects>
	  <Objects>
		    <Vip>203.***.***.119</Vip>
		    <PolicyId>47e07ebd-0ba5-4afc-957b-59d15b90****</PolicyId>
	  </Objects>
	  <Success>true</Success>
</DescribeSceneDefenseObjectsResponse>
```

`JSON` 格式

```
{
	"RequestId": "FE07E73F-F19E-4A51-B62F-AC59E3B962D8",
	"Objects": [
		{
			"Domain": "***.aliyun.com",
			"PolicyId": "47e07ebd-0ba5-4afc-957b-59d15b90****"
		},
		{
			"Vip": "203.***.***.119",
			"PolicyId": "47e07ebd-0ba5-4afc-957b-59d15b90****"
		}
	],
	"Success": true
}
```

## 错误码

访问[错误中心](https://error-center.aliyun.com/status/product/ddoscoo)查看更多错误码。

