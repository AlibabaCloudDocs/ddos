# DescribeTraffic {#doc_api_ddosbgp_DescribeTraffic .reference}

调用DescribeTraffic接口查看指定防护包上的流量情况。

**说明：** DDoS防护包的API接口目前仅对企业版DDoS防护包用户开放。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=ddosbgp&api=DescribeTraffic&type=RPC&version=2018-07-20)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeTraffic|要执行的操作，取值：**DescribeTraffic**。

 |
|EndTime|Integer|是|1563445054|查询结束时间，秒级时间戳。

 |
|Interval|Integer|是|1000|流量统计的时间间隔区间（单位：秒）。

 |
|StartTime|Integer|是|1560853054|查询开始时间，秒级时间戳。

 |
|InstanceId|String|否|ddosbgp-cn-\*\*\*\*\*|要查询的防护包实例ID。

 |
|Ip|String|否|1.1.1.1|要查询的防护对象IP。

 |
|ResourceGroupId|String|否|test|资源组ID。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|FlowList| | |流量信息。

 |
|FlowType|String|max|显示流量类型：

 -   **avg**：区间平均值
-   **max**：区间峰值

 |
|Kbps|Integer|8|流量大小（单位：Kbps）。

 |
|Name|String|73765106-54e7-11e9-aab0-d89d67182200|流量信息记录ID。

 |
|Pps|Integer|9|数据包数（单位：pps）。

 |
|Time|Integer|1560857000|流量信息时间戳。

 |
|RequestId|String|6A507DC8-F657-4C13-84E2-D1D1B9400753|本次请求的ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeTraffic
&EndTime=1563445054
&Interval=1000
&StartTime=1560853054
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeTraffic>
	  <RequestId>6A507DC8-F657-4C13-84E2-D1D1B9400753</RequestId>
	  <FlowList>
		    <Name>73765106-54e7-11e9-aab0-d89d67182200</Name>
		    <Pps>25</Pps>
		    <Time>1560855000</Time>
		    <FlowType>max</FlowType>
		    <Kbps>17</Kbps>
	  </FlowList>
	  <FlowList>
		    <Name>73765106-54e7-11e9-aab0-d89d67182200</Name>
		    <Pps>9</Pps>
		    <Time>1560857000</Time>
		    <FlowType>max</FlowType>
		    <Kbps>8</Kbps>
	  </FlowList>
</DescribeTraffic>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"FlowList":[
		{
			"Pps":25,
			"Name":"73765106-54e7-11e9-aab0-d89d67182200",
			"Time":1560855000,
			"FlowType":"max",
			"Kbps":17
		},
		{
			"Pps":9,
			"Name":"73765106-54e7-11e9-aab0-d89d67182200",
			"Time":1560857000,
			"FlowType":"max",
			"Kbps":8
		}
	],
	"RequestId":"6A507DC8-F657-4C13-84E2-D1D1B9400753"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/ddosbgp)查看更多错误码。

