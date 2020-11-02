# DescribePortViewSourceProvinces

调用DescribePortViewSourceProvinces查询指定时间段内DDoS高防实例的请求来源（中国）省份分布。

**说明：** 由于DDoS高防的四层传输层身份统计算法更新，目前该接口返回数据不能反应真实流量的大小，仅可用于计算不同省份请求数量的比例（即请求的来源省份分布情况）。如果您想获取请求流量数据，推荐您调用[DescribePortFlowList](~~157460~~)。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=ddoscoo&api=DescribePortViewSourceProvinces&type=RPC&version=2020-01-01)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribePortViewSourceProvinces|要执行的操作。取值：**DescribePortViewSourceProvinces**。 |
|InstanceIds.N|RepeatList|是|ddoscoo-cn-mp91j1ao\*\*\*\*|DDoS高防实例的ID。

 **说明：** 您可以调用[DescribeInstanceIds](~~157459~~)查询所有DDoS高防实例的ID信息。 |
|StartTime|Long|是|1582992000|查询开始时间。时间戳格式，单位：秒。

 **说明：** 必须为整点分钟。 |
|RegionId|String|否|cn-hangzhou|DDoS高防服务地域ID。取值：

 -   **cn-hangzhou**：表示DDoS高防（新BGP）服务。
-   **ap-southeast-1**：表示DDoS高防（国际）服务。 |
|ResourceGroupId|String|否|default|DDoS高防实例在资源管理产品中所属的资源组ID。默认为空，即属于默认资源组。 |
|EndTime|Long|否|1583683200|查询结束时间。时间戳格式，单位：秒。不传入表示使用当前时间作为结束时间。

 **说明：** 必须为整点分钟。 |

调用API时，除了本文中该API的请求参数，还需加入阿里云API公共请求参数。公共请求参数的详细介绍，请参见[公共参数](~~157269~~)。

调用API的请求格式，请参见本文**示例**中的请求示例。

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E|本次请求的ID。 |
|SourceProvinces|Array of Province| |DDoS高防实例的请求来源（中国）省份信息。 |
|Count|Long|3390671|相对请求数量。

 **说明：** 该数据不表示真实请求数量的大小，目前您可以使用该数据来计算不同省份请求数量的比例。 |
|ProvinceId|String|440000|省份ID，具体请参见[中国地区、国家和地域代码](~~167926~~)。例如，**110000**表示北京市，**120000**表示天津市。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=DescribePortViewSourceProvinces
&InstanceIds.1=ddoscoo-cn-mp91j1ao****
&StartTime=1582992000
&<公共请求参数>
```

正常返回示例

`XML` 格式

```
<DescribePortViewSourceProvincesResponse>
	  <RequestId>C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E</RequestId>
	  <SourceProvinces>
		    <Count>3390671</Count>
		    <ProvinceId>440000</ProvinceId>
	  </SourceProvinces>
</DescribePortViewSourceProvincesResponse>
```

`JSON` 格式

```
{
    "RequestId": "C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E",
    "SourceProvinces": [
        {
            "Count": 3390671,
            "ProvinceId": "440000"
        }
    ]
}
```

## 错误码

访问[错误中心](https://error-center.alibabacloud.com/status/product/ddoscoo)查看更多错误码。

