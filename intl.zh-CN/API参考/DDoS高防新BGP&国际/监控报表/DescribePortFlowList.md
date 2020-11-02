# DescribePortFlowList

调用DescribePortFlowList查询DDoS高防实例的流量数据列表。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=ddoscoo&api=DescribePortFlowList&type=RPC&version=2020-01-01)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribePortFlowList|要执行的操作。取值：**DescribePortFlowList**。 |
|EndTime|Long|是|1583683200|查询结束时间。时间戳格式，单位：秒。

 **说明：** 必须为整点分钟。 |
|InstanceIds.N|RepeatList|是|ddoscoo-cn-mp91j1ao\*\*\*\*|DDoS高防实例的ID。

 **说明：** 您可以调用[DescribeInstanceIds](~~157459~~)查询所有DDoS高防实例的ID信息。 |
|Interval|Integer|是|1000|返回数据的步长，单位为秒，即每隔多少秒返回一个结果。 |
|StartTime|Long|是|1582992000|查询开始时间。时间戳格式，单位：秒。

 **说明：** 必须为整点分钟。 |
|ResourceGroupId|String|否|default|DDoS高防实例在资源管理产品中所属的资源组ID。默认为空，即属于默认资源组。 |
|RegionId|String|否|cn-hangzhou|DDoS高防服务的地域ID。取值：

 -   **cn-hangzhou**：表示DDoS高防（新BGP）服务。
-   **ap-southeast-1**：表示DDoS高防（国际）服务。 |

调用API时，除了本文中该API的请求参数，还需加入阿里云API公共请求参数。公共请求参数的详细介绍，请参见[公共参数](~~157269~~)。

调用API的请求格式，请参见本文**示例**中的请求示例。

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|PortFlowList|Array of PortFlow| |流量数据。 |
|AttackBps|Long|0|攻击带宽，单位：bps。 |
|AttackPps|Long|0|攻击包转发率，单位：pps。 |
|InBps|Long|2176000|入方向带宽，单位：bps。 |
|InPps|Long|2934|入方向包转发率，单位：pps。 |
|Index|Long|0|返回数据的索引号。 |
|OutBps|Long|4389|出方向带宽，单位：bps。 |
|OutPps|Long|5|出方向包转发率，单位：pps。 |
|Region|String|cn|访问流量来源地区。取值：

 -   **cn**：中国内地。
-   **alb-ap-northeast-1-gf-x**：日本。
-   **alb-ap-southeast-gf-x**：新加坡。
-   **alb-cn-hongkong-gf-x**：中国香港。
-   **alb-eu-central-1-gf-x**：德国。
-   **alb-us-west-1-gf-x**：美国西部。

 **说明：** **cn**以外的取值只有在DDoS高防（国际）服务（**RegionId**为**ap-southeast-1**）中提供。 |
|Time|Long|1582992000|统计时间。时间戳格式，单位：秒。 |
|RequestId|String|FFC77501-BDF8-4BC8-9BF5-B295FBC3189B|本次请求的ID。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=DescribePortFlowList
&EndTime=1583683200
&InstanceIds.1=ddoscoo-cn-mp91j1ao****
&Interval=1000
&StartTime=1582992000
&<公共请求参数>
```

正常返回示例

`XML` 格式

```
<DescribePortFlowListResponse>
	  <RequestId>FFC77501-BDF8-4BC8-9BF5-B295FBC3189B</RequestId>
	  <PortFlowList>
		    <OutPps>5</OutPps>
		    <OutBps>4389</OutBps>
		    <InBps>2176000</InBps>
		    <InPps>2934</InPps>
		    <Region>cn</Region>
		    <Index>0</Index>
		    <AttackBps>0</AttackBps>
		    <AttackPps>0</AttackPps>
            <Time>1582992000</Time>
	  </PortFlowList>
	  <PortFlowList>
		    <OutPps>5</OutPps>
		    <OutBps>4155</OutBps>
		    <InBps>4648000</InBps>
		    <InPps>6268</InPps>
		    <Region>cn</Region>
		    <Index>1</Index>
		    <AttackBps>0</AttackBps>
		    <AttackPps>0</AttackPps>
            <Time>1582993000</Time>
	  </PortFlowList>
</DescribePortFlowListResponse>
```

`JSON` 格式

```
{
	"RequestId": "FFC77501-BDF8-4BC8-9BF5-B295FBC3189B",
	"PortFlowList": [
		{
			"OutPps": 5,
			"OutBps": 4389,
			"InBps": 2176000,
			"InPps": 2934,
			"Region": "cn",
			"Index": 0,
			"AttackBps": 0,
			"AttackPps": 0,
            "Time": 1582992000
		},
		{
			"OutPps": 5,
			"OutBps": 4155,
			"InBps": 4648000,
			"InPps": 6268,
			"Region": "cn",
			"Index": 1,
			"AttackBps": 0,
			"AttackPps": 0,
            "Time": 1582993000
		}
	]
}
```

## 错误码

访问[错误中心](https://error-center.alibabacloud.com/status/product/ddoscoo)查看更多错误码。

