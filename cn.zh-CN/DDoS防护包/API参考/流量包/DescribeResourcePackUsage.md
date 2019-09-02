# DescribeResourcePackUsage {#doc_api_ddosbgp_DescribeResourcePackUsage .reference}

调用DescribeResourcePackUsage接口查询抗D流量包的使用明细。

**说明：** DDoS防护包的API接口目前仅对企业版DDoS防护包用户开放。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=ddosbgp&api=DescribeResourcePackUsage&type=RPC&version=2018-07-20)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeResourcePackUsage|要执行的操作，取值：**DescribeResourcePackUsage**。

 |
|EndTime|Long|是|1557909844|查询结束时间，秒级时间戳。所设置的查询时间区间不能超过30天。

 |
|StartTime|Long|是|1557305044|查询开始时间，秒级时间戳。所设置的查询时间区间不能超过30天。

 |
|InstanceId|String|否|ddosbgp-cn-x1|要查询的防护包实例ID。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|EndTime|Long|1557910800|统计结束时间，秒级时间戳。

 |
|Interval|Long|3600|统计时间间隔，单位为秒。

 |
|PackUsages| | |已用防护流量明细。

 |
|Time|Long|1557471600|时间。

 |
|Traffic|Float|153.064|流量，单位为Gb。

 |
|RequestId|String|38F3D5EF-42BA-4533-81EB-AEAD068B5E02|本次请求的ID。

 |
|StartTime|Long|1557302400|统计起始时间，秒级时间戳。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeResourcePackUsage
&EndTime=1557909844
&StartTime=1557305044
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeResourcePackUsageResponse>
     <Interval>3600</Interval>
     <PackUsages>
           <PackUsage>
                 <Time>1557471600</Time>
                 <Traffic>153.064</Traffic>
           </PackUsage>
     </PackUsages>
     <RequestId>38F3D5EF-42BA-4533-81EB-AEAD068B5E02</RequestId>
     <EndTime>1557910800</EndTime>
     <StartTime>1557302400</StartTime>
</DescribeResourcePackUsageResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Interval":3600,
	"PackUsages":[
		{
			"Time":1557471600,
			"Traffic":153.064
		}
	],
	"RequestId":"38F3D5EF-42BA-4533-81EB-AEAD068B5E02",
	"EndTime":1557910800,
	"StartTime":1557302400
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/ddosbgp)查看更多错误码。

