# DescribeDDosEventMax

调用DescribeDDosEventMax查询指定时间范围内的流量型攻击峰值（bps）、连接型攻击峰值（cps）、Web资源耗尽型攻击峰值（qps）。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=ddoscoo&api=DescribeDDosEventMax&type=RPC&version=2020-01-01)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeDDosEventMax|要执行的操作。取值：**DescribeDDosEventMax**。 |
|EndTime|Long|是|1604073600|查询开始时间戳，单位：秒。 |
|StartTime|Long|是|1598889600|查询结束时间戳，单位：秒。 |

调用API时，除了本文中该API的请求参数，还需加入阿里云API公共请求参数。公共请求参数的详细介绍，请参见[公共参数](~~157269~~)。

调用API的请求格式，请参见本文**示例**中的请求示例。

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|Cps|Long|1302|连接型攻击峰值，单位：cps。 |
|Mbps|Long|6809|流量型攻击峰值，单位：Mbps。 |
|Qps|Long|26314|Web资源耗尽型攻击峰值，单位：qps。 |
|RequestId|String|5AE2FC86-C840-41AE-9F1A-3A2747C7C1DF|本次请求的ID。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=DescribeDDosEventMax
&EndTime=1604073600
&StartTime=1598889600
&<公共请求参数>
```

正常返回示例

`XML` 格式

```
<DescribeDDosEventMaxResponse>
	  <RequestId>5AE2FC86-C840-41AE-9F1A-3A2747C7C1DF</RequestId>
	  <Qps>26314</Qps>
	  <Cps>1302</Cps>
	  <Mbps>6809</Mbps>
 </DescribeDDosEventMaxResponse>
```

`JSON` 格式

```
{
	"RequestId": "5AE2FC86-C840-41AE-9F1A-3A2747C7C1DF",
	"Qps": 26314,
	"Cps": 1302,
	"Mbps": 6809
}
```

## 错误码

访问[错误中心](https://error-center.aliyun.com/status/product/ddoscoo)查看更多错误码。

