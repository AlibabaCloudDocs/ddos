# DescribeDomainQPSList

调用DescribeDomainQPSList查询网站业务的QPS统计信息。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=ddoscoo&api=DescribeDomainQPSList&type=RPC&version=2020-01-01)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeDomainQPSList|要执行的操作。取值：**DescribeDomainQPSList**。 |
|EndTime|Long|是|1583683200|查询结束时间。时间戳格式，单位：秒。

 **说明：** 必须为整点分钟。 |
|Interval|Long|是|1000|返回数据的步长，单位为秒，即每隔多少秒返回一个结果。 |
|StartTime|Long|是|1582992000|查询开始时间。时间戳格式，单位：秒。

 **说明：** 必须为整点分钟。 |
|ResourceGroupId|String|否|default|DDoS高防实例在资源管理产品中所属的资源组ID。默认为空，即属于默认资源组。 |
|RegionId|String|否|cn-hangzhou|DDoS高防服务的地域ID。取值：

 -   **cn-hangzhou**：表示DDoS高防（新BGP）服务。
-   **ap-southeast-1**：表示DDoS高防（国际）服务。 |
|Domain|String|否|www.aliyun.com|网站业务的域名。不传入表示查询所有域名的QPS统计信息。

 **说明：** 域名必须已配置网站业务转发规则。您可以调用[DescribeDomains](~~91724~~)查询所有域名。 |

调用API时，除了本文中该API的请求参数，还需加入阿里云API公共请求参数。公共请求参数的详细介绍，请参见[公共参数](~~157269~~)。

调用API的请求格式，请参见本文**示例**中的请求示例。

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|DomainQPSList|Array of DomainQPS| |网站业务QPS统计信息。 |
|AttackQps|Long|1|攻击QPS。 |
|CacheHits|Long|0|缓存命中数。 |
|Index|Long|0|返回数据的索引号。 |
|MaxAttackQps|Long|37|攻击QPS峰值。 |
|MaxNormalQps|Long|93|正常QPS峰值。 |
|MaxQps|Long|130|总QPS峰值。 |
|Time|Long|1582992000|统计时间。时间戳格式，单位：秒。 |
|TotalCount|Long|20008|总访问次数。 |
|TotalQps|Long|1|总QPS。 |
|RequestId|String|327F2ABB-104D-437A-AAB5-D633E29A8C51|本次请求的ID。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=DescribeDomainQPSList
&Interval=1000
&<公共请求参数>
```

正常返回示例

`XML` 格式

```
<DescribeDomainQPSListResponse>
	  <DomainQPSList>
		    <MaxAttackQps>37</MaxAttackQps>
		    <TotalQps>1</TotalQps>
		    <TotalCount>20008</TotalCount>
		    <MaxQps>130</MaxQps>
		    <MaxNormalQps>93</MaxNormalQps>
		    <AttackQps>1</AttackQps>
		    <Index>0</Index>
		    <Time>1582992000</Time>
		    <CacheHits>0</CacheHits>
	  </DomainQPSList>
	  <RequestId>327F2ABB-104D-437A-AAB5-D633E29A8C51</RequestId>
</DescribeDomainQPSListResponse>
```

`JSON` 格式

```
{
	"DomainQPSList": [
		{
			"MaxAttackQps": 37,
			"TotalQps": 1,
			"TotalCount": 20008,
			"MaxQps": 130,
			"MaxNormalQps": 93,
			"AttackQps": 1,
			"Index": 0,
			"Time": 1582992000,
			"CacheHits": 0
		}
	],
	"RequestId": "327F2ABB-104D-437A-AAB5-D633E29A8C51"
}
```

## 错误码

访问[错误中心](https://error-center.alibabacloud.com/status/product/ddoscoo)查看更多错误码。

