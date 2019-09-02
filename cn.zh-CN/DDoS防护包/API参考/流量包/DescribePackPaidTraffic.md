# DescribePackPaidTraffic {#doc_api_ddosbgp_DescribePackPaidTraffic .reference}

调用DescribePackPaidTraffic接口查询付费流量明细。

**说明：** DDoS防护包的API接口目前仅对企业版DDoS防护包用户开放。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=ddosbgp&api=DescribePackPaidTraffic&type=RPC&version=2018-07-20)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribePackPaidTraffic|要执行的操作，取值：**DescribePackPaidTraffic**。

 |
|CurrentPage|Integer|是|1|列表的页码，默认值为**1**。

 |
|EndTime|Long|是|1557908337870|查询结束时间，秒级时间戳。所设置的查询时间区间不能超过30天。

 |
|PageSize|Integer|是|10|分页查询时每页的行数，最大值为**50**，默认值为**10**。

 |
|StartTime|Long|是|1557303537870|查询开始时间，秒级时间戳。所设置的查询时间区间不能超过30天。

 |
|InstanceId|String|否|ddosbgp-cn-x1|要查询的防护包实例ID。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|PackPaidTraffics| | |付费流量明细。

 |
|BaseBandwidth|Integer|20|基础防护带宽，单位为Gb。

 |
|ElasticBandwidth|Integer|100|弹性防护带宽，单位为Gb。

 |
|InstanceId|String|ddosbgp-cn-x1|防护包实例ID。

 |
|MaxAttack|Float|49.998|攻击流量峰值，单位为Gbps。

 |
|PaidCapacity|Float|615.166|付费流量大小，单位为Gb。

 |
|StartTime|Long|1557809400000|统计时间。

 |
|TotalCapacity|Float|1302.666|总防护流量，单位为Gb。

 |
|RequestId|String|070363B7-BB66-43B8-9A2C-9E4B83284FC5|本次请求的ID。

 |
|TotalCount|Integer|1|返回结果的数量。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribePackPaidTraffic
&CurrentPage=1
&EndTime=1557908337870
&PageSize=10
&StartTime=1557303537870
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribePackPaidTrafficResponse>
     <TotalCount>1</TotalCount>
     <RequestId>070363B7-BB66-43B8-9A2C-9E4B83284FC5</RequestId>
     <PackPaidTraffics>
           <PackPaidTraffic>
                 <PaidCapacity>615.166</PaidCapacity>
                 <MaxAttack>49.998</MaxAttack>
                 <InstanceId>ddosbgp-cn-x1</InstanceId>
                 <TotalCapacity>1302.666</TotalCapacity>
                 <ElasticBandwidth>100</ElasticBandwidth>
                 <BaseBandwidth>20</BaseBandwidth>
                 <StartTime>1557809400000</StartTime>
           </PackPaidTraffic>
     </PackPaidTraffics>
</DescribePackPaidTrafficResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"TotalCount":1,
	"RequestId":"070363B7-BB66-43B8-9A2C-9E4B83284FC5",
	"PackPaidTraffics":[
		{
			"PaidCapacity":615.166,
			"InstanceId":"ddosbgp-cn-x1",
			"MaxAttack":49.998,
			"TotalCapacity":1302.666,
			"ElasticBandwidth":100,
			"StartTime":1557809400000,
			"BaseBandwidth":20
		}
	]
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/ddosbgp)查看更多错误码。

