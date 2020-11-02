# DescribePortConnsList

调用DescribePortConnsList查询DDoS高防实例的端口连接数列表。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=ddoscoo&api=DescribePortConnsList&type=RPC&version=2020-01-01)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribePortConnsList|要执行的操作。取值：**DescribePortConnsList**。 |
|EndTime|Long|是|1583683200|查询结束时间。时间戳格式，单位：秒。

 **说明：** 必须为整点分钟。 |
|InstanceIds.N|RepeatList|是|ddoscoo-cn-mp91j1ao\*\*\*\*|DDoS高防实例的ID。

 **说明：** 您可以调用[DescribeInstanceIds](~~157459~~)查询所有DDoS高防实例的ID信息。 |
|Interval|Integer|是|1000|返回数据的步长，单位为秒，即每隔多少秒返回一个结果。 |
|StartTime|Long|是|1582992000|查询开始时间。时间戳格式，单位：秒。

 **说明：** 必须为整点分钟。 |
|RegionId|String|否|cn-hangzhou|DDoS高防服务的地域ID。取值：

 -   **cn-hangzhou**：表示DDoS高防（新BGP）服务。
-   **ap-southeast-1**：表示DDoS高防（国际）服务。 |
|ResourceGroupId|String|否|default|DDoS高防实例在资源管理产品中所属的资源组ID。默认为空，即属于默认资源组。 |
|Port|String|否|null|要查询的端口号。不传入表示查询所有端口。 |

调用API时，除了本文中该API的请求参数，还需加入阿里云API公共请求参数。公共请求参数的详细介绍，请参见[公共参数](~~157269~~)。

调用API的请求格式，请参见本文**示例**中的请求示例。

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|ConnsList|Array of Conn| |端口连接数据列表。 |
|ActConns|Long|2|活跃连接数。 |
|Conns|Long|20|并发连接数。 |
|Cps|Long|0|新建连接数。 |
|InActConns|Long|4|不活跃连接数。 |
|Index|Long|0|返回数据的索引。 |
|Time|Long|1582992000|统计时间。时间戳格式，单位：秒。 |
|RequestId|String|7E6BF16F-27A9-49BC-AD18-F79B409DE753|本次请求的ID。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=DescribePortConnsList
&EndTime=1583683200
&InstanceIds.1=ddoscoo-cn-mp91j1ao****
&Interval=1000
&StartTime=1582992000
&<公共请求参数>
```

正常返回示例

`XML` 格式

```
<DescribePortConnsListResponse>
	  <ConnsList>
		    <Conns>20</Conns>
		    <Cps>0</Cps>
		    <Index>0</Index>
		    <ActConns>2</ActConns>
		    <InActConns>4</InActConns>
            <Time>1582992000</Time>
	  </ConnsList>
	  <ConnsList>
		    <Conns>24</Conns>
		    <Cps>0</Cps>
		    <Index>1</Index>
		    <ActConns>2</ActConns>
		    <InActConns>5</InActConns>
            <Time>1582993000</Time>
	  </ConnsList>
	  <RequestId>7E6BF16F-27A9-49BC-AD18-F79B409DE753</RequestId>
</DescribePortConnsListResponse>
```

`JSON` 格式

```
{
	"ConnsList": [
		{
			"Conns": 20,
			"Cps": 0,
			"Index": 0,
			"ActConns": 2,
			"InActConns": 4,
            "Time": 1582992000
		},
		{
			"Conns": 24,
			"Cps": 0,
			"Index": 1,
			"ActConns": 2,
			"InActConns": 5,
            "Time": 1582993000
		}
	],
	"RequestId": "7E6BF16F-27A9-49BC-AD18-F79B409DE753"
}
```

## 错误码

访问[错误中心](https://error-center.alibabacloud.com/status/product/ddoscoo)查看更多错误码。

