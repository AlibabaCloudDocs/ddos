# DescribeResourcePackStatistics {#doc_api_ddosbgp_DescribeResourcePackStatistics .reference}

调用DescribeResourcePackStatistics接口查询抗D流量包的统计信息。

**说明：** DDoS防护包的API接口目前仅对企业版DDoS防护包用户开放。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=ddosbgp&api=DescribeResourcePackStatistics&type=RPC&version=2018-07-20)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeResourcePackStatistics|要执行的操作，取值：**DescribeResourcePackStatistics**。

 |
|DdosRegionId|String|否|cn-hangzhou|实例所在地区ID。

 |
|InstanceId|String|否|ddosbgp-cn-x1|要查询的防护包实例ID。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|AvailablePackNum|Integer|8|可用流量包数量。

 |
|RequestId|String|A2D6D5FB-FA07-41A8-B093-A2B7B26E72F2|本次请求的ID。

 |
|TotalCurrCapacity|Long|20831250000000|总可用防护流量，单位为Byte。

 |
|TotalInitCapacity|Long|427000000000000|总初始防护流量，单位为Byte。

 |
|TotalUsedCapacity|Long|5285439000000|总消耗防护流量，单位为Byte。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeResourcePackStatistics
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeResourcePackStatisticsResponse>
     <TotalInitCapacity>427000000000000</TotalInitCapacity>
     <TotalUsedCapacity>5285439000000</TotalUsedCapacity>
     <TotalCurrCapacity>20831250000000</TotalCurrCapacity>
     <RequestId>A2D6D5FB-FA07-41A8-B093-A2B7B26E72F2</RequestId>
     <AvailablePackNum>8</AvailablePackNum>
</DescribeResourcePackStatisticsResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"TotalInitCapacity":427000000000000,
	"TotalUsedCapacity":5285439000000,
	"RequestId":"A2D6D5FB-FA07-41A8-B093-A2B7B26E72F2",
	"TotalCurrCapacity":20831250000000,
	"AvailablePackNum":8
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/ddosbgp)查看更多错误码。

