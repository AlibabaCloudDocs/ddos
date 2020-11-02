# DescribeDomainStatusCodeList

调用DescribeDomainStatusCodeList查询网站业务的响应状态码统计信息。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=ddoscoo&api=DescribeDomainStatusCodeList&type=RPC&version=2020-01-01)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeDomainStatusCodeList|要执行的操作。取值：**DescribeDomainStatusCodeList**。 |
|Interval|Long|是|1000|返回数据的步长，单位为秒，即每隔多少秒返回一个结果。 |
|QueryType|String|是|gf|查询数据的来源。取值：

 -   **gf**：高防响应。
-   **upstrem**：源站响应。 |
|StartTime|Long|是|1582992000|查询开始时间。时间戳格式，单位：秒。

 **说明：** 必须为整点分钟。 |
|ResourceGroupId|String|否|default|DDoS高防实例在资源管理产品中所属的资源组ID。默认为空，即属于默认资源组。 |
|RegionId|String|否|cn-hangzhou|DDoS高防服务的地域ID。取值：

 -   **cn-hangzhou**：表示DDoS高防（新BGP）服务。
-   **ap-southeast-1**：表示DDoS高防（国际）服务。 |
|EndTime|Long|否|1583683200|查询结束时间。时间戳格式，单位：秒。

 **说明：** 必须为整点分钟。 |
|Domain|String|否|www.aliyun.com|网站业务的域名。不传入表示查询所有域名的响应状态码统计信息。

 **说明：** 域名必须已配置网站业务转发规则。您可以调用[DescribeDomains](~~91724~~)查询所有域名。 |

调用API时，除了本文中该API的请求参数，还需加入阿里云API公共请求参数。公共请求参数的详细介绍，请参见[公共参数](~~157269~~)。

调用API的请求格式，请参见本文**示例**中的请求示例。

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|3B63C0DD-8AC5-44B2-95D6-064CA9296B9C|本次请求的ID。 |
|StatusCodeList|Array of StatusCode| |响应状态码的统计信息。 |
|Index|Integer|0|返回数据的索引号。 |
|Status200|Long|15520|200状态码的统计值。 |
|Status2XX|Long|15520|2XX类状态码的统计值。 |
|Status3XX|Long|0|3XX类状态码的统计值。 |
|Status403|Long|0|403状态码的统计值。 |
|Status404|Long|0|404状态码的统计值。 |
|Status405|Long|0|405状态码的统计值。 |
|Status4XX|Long|4486|4XX类状态码的统计值。 |
|Status501|Long|0|501状态码的统计值。 |
|Status502|Long|0|502状态码的统计值。 |
|Status503|Long|0|503状态码的统计值。 |
|Status504|Long|0|504状态码的统计值。 |
|Status5XX|Long|0|5XX类状态码的统计值。 |
|Time|Long|1582992000|统计时间。时间戳格式，单位：秒。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=DescribeDomainStatusCodeList
&QueryType=gf
&<公共请求参数>
```

正常返回示例

`XML` 格式

```
<DescribeDomainStatusCodeListResponse>
	  <RequestId>3B63C0DD-8AC5-44B2-95D6-064CA9296B9C</RequestId>
	  <StatusCodeList>
		    <Status501>0</Status501>
		    <Status502>0</Status502>
		    <Status403>0</Status403>
		    <Index>0</Index>
		    <Time>1582992000</Time>
		    <Status503>0</Status503>
		    <Status404>0</Status404>
		    <Status504>0</Status504>
		    <Status405>0</Status405>
		    <Status2XX>15520</Status2XX>
		    <Status200>15520</Status200>
		    <Status3XX>0</Status3XX>
		    <Status4XX>4486</Status4XX>
		    <Status5XX>0</Status5XX>
	  </StatusCodeList>
</DescribeDomainStatusCodeListResponse>
```

`JSON` 格式

```
{
	"RequestId": "3B63C0DD-8AC5-44B2-95D6-064CA9296B9C",
	"StatusCodeList": [
		{
			"Status501": 0,
			"Status502": 0,
			"Status403": 0,
			"Index": 0,
			"Time": 1582992000,
			"Status503": 0,
			"Status404": 0,
			"Status504": 0,
			"Status405": 0,
			"Status2XX": 15520,
			"Status200": 15520,
			"Status3XX": 0,
			"Status4XX": 4486,
			"Status5XX": 0
		}
	]
}
```

## 错误码

访问[错误中心](https://error-center.alibabacloud.com/status/product/ddoscoo)查看更多错误码。

