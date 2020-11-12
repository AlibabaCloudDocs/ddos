# DescribeDDosAllEventList

调用DescribeDDosAllEventList查询攻击事件列表。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=ddoscoo&api=DescribeDDosAllEventList&type=RPC&version=2020-01-01)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeDDosAllEventList|要执行的操作。取值：**DescribeDDosAllEventList**。 |
|EndTime|Long|是|1604073600|查询结束时间戳，单位：秒。 |
|PageNumber|Integer|是|1|分页查询请求时返回的页码。例如，查询第一页的返回结果，则填写**1**。 |
|PageSize|Integer|是|10|页面显示的记录数量。 |
|StartTime|Long|是|1598889600|查询开始时间戳，单位：秒。 |
|EventType|String|否|defense|要查询的事件类型。取值：

 **说明：** 默认取值为空，表示查询所有类型。

 -   **web-cc**：Web资源耗尽型攻击。
-   **cc**：连接型攻击。
-   **defense**：流量型攻击清洗事件。
-   **blackhole**：流量型攻击黑洞事件。

 如果要查询多个事件类型，传入多个值并用英文逗号（,）分隔即可。 |

调用API时，除了本文中该API的请求参数，还需加入阿里云API公共请求参数。公共请求参数的详细介绍，请参见[公共参数](~~157269~~)。

调用API的请求格式，请参见本文**示例**中的请求示例。

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|AttackEvents|Array of AttackEvent| |攻击事件信息。 |
|EndTime|Long|1600953999|事件结束时间戳，单位：秒。 |
|EventType|String|defense|事件类型。取值：

 -   **web-cc**：Web资源耗尽型攻击。
-   **cc**：连接型攻击。
-   **defense**：流量型攻击清洗事件。
-   **blackhole**：流量型攻击黑洞事件。 |
|Ip|String|203.\*\*\*.\*\*\*.52|受攻击对象。不同事件类型返回的受攻击对象格式不同，具体如下：

 -   Web资源耗尽型攻击：返回受攻击的网站域名。
-   连接型攻击：返回受攻击的高防IP。
-   流量型攻击（清洗事件、黑洞事件）：返回受攻击的高防IP。 |
|Mbps|Long|2415|攻击带宽，单位：Mbps。 |
|Port|String|80|受攻击的端口号。

 **说明：** 只有连接型攻击会返回该参数，Web资源耗尽型和流量型攻击（清洗事件、黑洞事件）不返回该参数。 |
|Pps|Long|204800|攻击的包转发率，单位：pps。 |
|StartTime|Long|1600951380|事件开始时间戳，单位：秒。 |
|RequestId|String|0AA2B635-69BD-499D-9587-5782663DC0F6|本次请求的ID。 |
|Total|Long|2|攻击事件的数量。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=DescribeDDosAllEventList
&EndTime=1604073600
&PageNumber=1
&PageSize=10
&StartTime=1598889600
&<公共请求参数>
```

正常返回示例

`XML` 格式

```
<DescribeDDosAllEventListResponse>
	  <RequestId>0AA2B635-69BD-499D-9587-5782663DC0F6</RequestId>
	  <Total>2</Total>
	  <AttackEvents>
		    <Pps>2870</Pps>
		    <EndTime>1600951860</EndTime>
		    <EventType>web-cc</EventType>
		    <Ip>***.example.com</Ip>
		    <StartTime>1600951470</StartTime>
		    <Mbps>0</Mbps>
	  </AttackEvents>
	  <AttackEvents>
		    <Pps>204800</Pps>
		    <EndTime>1600953999</EndTime>
		    <EventType>defense</EventType>
		    <Port></Port>
		    <Ip>203.***.***.52</Ip>
		    <StartTime>1600951380</StartTime>
		    <Mbps>2415</Mbps>
	  </AttackEvents>
</DescribeDDosAllEventListResponse>
```

`JSON` 格式

```
{
	"RequestId": "0AA2B635-69BD-499D-9587-5782663DC0F6",
	"Total": 2,
	"AttackEvents": [
		{
			"Pps": 2870,
			"EndTime": 1600951860,
			"EventType": "web-cc",
			"Ip": "***.example.com",
			"StartTime": 1600951470,
			"Mbps": 0
		},
		{
			"Pps": 204800,
			"EndTime": 1600953999,
			"EventType": "defense",
			"Port": "",
			"Ip": "203.***.***.52",
			"StartTime": 1600951380,
			"Mbps": 2415
		}
	]
}
```

## 错误码

访问[错误中心](https://error-center.aliyun.com/status/product/ddoscoo)查看更多错误码。

