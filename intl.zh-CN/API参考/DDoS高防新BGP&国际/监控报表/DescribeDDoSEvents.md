# DescribeDDoSEvents

调用DescribeDDoSEvents查询针对DDoS高防实例的攻击事件。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=ddoscoo&api=DescribeDDoSEvents&type=RPC&version=2020-01-01)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeDDoSEvents|要执行的操作。取值：**DescribeDDoSEvents**。 |
|InstanceIds.N|RepeatList|是|ddoscoo-cn-mp91j1ao\*\*\*\*|DDoS高防实例的ID。

 **说明：** 您可以调用[DescribeInstanceIds](~~157459~~)查询所有DDoS高防实例的ID信息。 |
|PageNumber|Integer|是|1|分页查询请求时返回的页码。例如，查询第一页的返回结果，则填写**1**。 |
|PageSize|Integer|是|10|页面显示的记录数量。 |
|StartTime|Long|是|1582992000|查询开始时间。时间戳格式，单位：秒。

 **说明：** 必须为整点分钟。 |
|RegionId|String|否|cn-hangzhou|DDoS高防服务的地域ID。取值：

 -   **cn-hangzhou**：表示DDoS高防（新BGP）服务。
-   **ap-southeast-1**：表示DDoS高防（国际）服务。 |
|ResourceGroupId|String|否|default|DDoS高防实例在资源管理产品中所属的资源组ID。默认为空，即属于默认资源组。 |
|EndTime|Long|否|1583683200|查询结束时间。时间戳格式，单位：秒。

 **说明：** 必须为整点分钟。 |

调用API时，除了本文中该API的请求参数，还需加入阿里云API公共请求参数。公共请求参数的详细介绍，请参见[公共参数](~~157269~~)。

调用API的请求格式，请参见本文**示例**中的请求示例。

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|DDoSEvents|Array of Data| |DDoS攻击事件列表。 |
|Bps|Long|0|攻击流量带宽大小。单位：bps。 |
|EndTime|Long|1583933330|攻击结束时间。时间戳格式，单位：秒。 |
|EventType|String|blackhole|攻击事件类型。取值：

 -   **defense**：清洗事件。
-   **blackhole**：黑洞事件。 |
|Ip|String|203.\*\*\*.\*\*\*.132|被攻击IP。 |
|Port|String|80|被攻击端口。 |
|Pps|Long|0|攻击流量包转发率。单位：pps。 |
|Region|String|cn|攻击来源地区。取值：

 -   **cn**：中国内地。
-   **alb-ap-northeast-1-gf-x**：日本。
-   **alb-ap-southeast-gf-x**：新加坡。
-   **alb-cn-hongkong-gf-x**：中国香港。
-   **alb-eu-central-1-gf-x**：德国。
-   **alb-us-west-1-gf-x**：美国西部。

 **说明：** **cn**以外的取值只有在DDoS高防（国际）服务（**RegionId**为**ap-southeast-1**）中提供。 |
|StartTime|Long|1583933277|攻击开始时间。时间戳格式，单位：秒。 |
|RequestId|String|0CA72AF5-1795-4350-8C77-50A448A2F334|本次请求的ID。 |
|Total|Long|1|攻击事件总数。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=DescribeDDoSEvents
&InstanceIds.1=ddoscoo-cn-mp91j1ao****
&PageNumber=1
&PageSize=10
&StartTime=1582992000
&<公共请求参数>
```

正常返回示例

`XML` 格式

```
<DescribeDDoSEventsResponse>
	  <RequestId>0CA72AF5-1795-4350-8C77-50A448A2F334</RequestId>
	  <Total>1</Total>
	  <DDoSEvents>
		    <Pps>0</Pps>
		    <Bps>0</Bps>
		    <EndTime>1583933330</EndTime>
		    <EventType>blackhole</EventType>
		    <Ip>203.***.***.132</Ip>
		    <Port></Port>
		    <StartTime>1583933277</StartTime>
	  </DDoSEvents>
</DescribeDDoSEventsResponse>
```

`JSON` 格式

```
{
	"RequestId": "0CA72AF5-1795-4350-8C77-50A448A2F334",
	"Total": 1,
	"DDoSEvents": [
		{
			"Pps": 0,
			"Bps": 0,
			"EndTime": 1583933330,
			"EventType": "blackhole",
			"Ip": "203.***.***.132",
			"Port": "",
			"StartTime": 1583933277
		}
	]
}
```

## 错误码

访问[错误中心](https://error-center.alibabacloud.com/status/product/ddoscoo)查看更多错误码。

