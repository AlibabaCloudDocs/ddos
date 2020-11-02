# DescribePortViewSourceIsps

调用DescribePortViewSourceIsps查询指定时间段内DDoS高防实例的请求来源运营商分布。

**说明：** 由于DDoS高防的四层传输层身份统计算法更新，目前该接口返回数据不能反应真实流量的大小，仅可用于计算不同运营商请求数量的比例（即请求的来源运营商分布情况）。如果您想获取请求流量数据，推荐您调用[DescribePortFlowList](~~157460~~)。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=ddoscoo&api=DescribePortViewSourceIsps&type=RPC&version=2020-01-01)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribePortViewSourceIsps|要执行的操作。取值：**DescribePortViewSourceIsps**。 |
|EndTime|Long|是|1583683200|查询结束时间。时间戳格式，单位：秒。不传入表示使用当前时间作为结束时间。

 **说明：** 必须为整点分钟。 |
|InstanceIds.N|RepeatList|是|ddoscoo-cn-mp91j1ao\*\*\*\*|DDoS高防实例的ID。

 **说明：** 您可以调用[DescribeInstanceIds](~~157459~~)查询所有DDoS高防实例的ID信息。 |
|StartTime|Long|是|1582992000|查询开始时间。时间戳格式，单位：秒。

 **说明：** 必须为整点分钟。 |
|RegionId|String|否|cn-hangzhou|DDoS高防服务的地域ID。取值：

 -   **cn-hangzhou**：表示DDoS高防（新BGP）服务。
-   **ap-southeast-1**：表示DDoS高防（国际）服务。 |
|ResourceGroupId|String|否|default|DDoS高防实例在资源管理产品中所属的资源组ID。默认为空，即属于默认资源组。 |

调用API时，除了本文中该API的请求参数，还需加入阿里云API公共请求参数。公共请求参数的详细介绍，请参见[公共参数](~~157269~~)。

调用API的请求格式，请参见本文**示例**中的请求示例。

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|Isps|Array of Isp| |DDoS高防实例的请求来源运营商信息。 |
|Count|Long|3390671|相对请求数量。

 **说明：** 该数据不表示真实请求数量的大小，目前您可以使用该数据来计算不同运营商请求数量的比例。 |
|IspId|String|100017|运营商ID。详见返回参数表下的运营商代码说明，运营商ID对应表中的代码。 |
|RequestId|String|C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E|本次请求的ID。 |

**运营商代码**

|代码

|运营商 |
|----|-----|
|100017

|电信 |
|100026

|联通 |
|100025

|移动 |
|100027

|教育网 |
|100020

|铁通 |
|1000143

|鹏博士 |
|100080

|歌华 |
|1000139

|广电 |
|100023

|有线通 |
|100063

|方正宽带 |
|1000337

|皓宽网络 |
|100021

|世纪互联 |
|1000333

|华数传媒 |
|100093

|网宿 |
|1000401

|腾讯 |
|100099

|百度 |
|1000323

|阿里云 |
|100098

|阿里巴巴 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=DescribePortViewSourceIsps
&EndTime=1583683200
&InstanceIds.1=ddoscoo-cn-mp91j1ao****
&StartTime=1582992000
&<公共请求参数>
```

正常返回示例

`XML` 格式

```
<DescribePortViewSourceIspsResponse>
	  <RequestId>C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E</RequestId>
	  <Isps>
		    <Count>3390671</Count>
		    <IspId>100017</IspId>
	  </Isps>
</DescribePortViewSourceIspsResponse>
```

`JSON` 格式

```
{
    "RequestId": "C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E",
    "Isps": [
        {
            "Count": 3390671,
            "IspId": "100017"
        }
    ]
}
```

## 错误码

访问[错误中心](https://error-center.alibabacloud.com/status/product/ddoscoo)查看更多错误码。

