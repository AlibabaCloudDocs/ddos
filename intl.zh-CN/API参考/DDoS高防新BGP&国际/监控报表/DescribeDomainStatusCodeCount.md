# DescribeDomainStatusCodeCount

调用DescribeDomainStatusCodeCount查询指定时间段内网站业务的各类响应状态码的统计信息。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=ddoscoo&api=DescribeDomainStatusCodeCount&type=RPC&version=2020-01-01)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeDomainStatusCodeCount|要执行的操作。取值：**DescribeDomainStatusCodeCount**。 |
|EndTime|Long|是|1583683200|查询结束时间。时间戳格式，单位：秒。

 **说明：** 必须为整点分钟。 |
|StartTime|Long|是|1582992000|查询开始时间。时间戳格式，单位：秒。

 **说明：** 必须为整点分钟。 |
|ResourceGroupId|String|否|default|DDoS高防实例在资源管理产品中所属的资源组ID。默认为空，即属于默认资源组。 |
|RegionId|String|否|cn-hangzhou|DDoS高防服务的地域ID。取值：

 -   **cn-hangzhou**：表示DDoS高防（新BGP）服务。
-   **ap-southeast-1**：表示DDoS高防（国际）服务。 |
|Domain|String|否|www.aliyun.com|网站业务的域名。

 **说明：** 域名必须已配置网站业务转发规则。您可以调用[DescribeDomains](~~91724~~)查询所有域名。 |

调用API时，除了本文中该API的请求参数，还需加入阿里云API公共请求参数。公共请求参数的详细介绍，请参见[公共参数](~~157269~~)。

调用API的请求格式，请参见本文**示例**中的请求示例。

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E|本次请求的ID。 |
|Status200|Long|951159|查询时间段内200状态码的数量。 |
|Status2XX|Long|951472|查询时间段内2XX类状态码的数量。 |
|Status3XX|Long|133209|查询时间段内3XX状态码的数量。 |
|Status403|Long|0|查询时间段内403状态码的数量。 |
|Status404|Long|897|查询时间段内404状态码的数量。 |
|Status405|Long|0|查询时间段内405状态码的数量。 |
|Status4XX|Long|5653|查询时间段内4XX状态码的数量。 |
|Status501|Long|0|查询时间段内501状态码的数量。 |
|Status502|Long|0|查询时间段内502状态码的数量。 |
|Status503|Long|0|查询时间段内503状态码的数量。 |
|Status504|Long|0|查询时间段内504状态码的数量。 |
|Status5XX|Long|14|查询时间段内5XX状态码的数量。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=DescribeDomainStatusCodeCount
&EndTime=1583683200
&StartTime=1582992000
&<公共请求参数>
```

正常返回示例

`XML` 格式

```
<DescribeDomainStatusCodeCountResponse>
	  <RequestId>C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E</RequestId>
	  <Status2XX>951472</Status2XX>
	  <Status200>951159</Status200>
	  <Status3XX>133209</Status3XX>
	  <Status4XX>5653</Status4XX>
	  <Status403>0</Status403>
	  <Status404>897</Status404>
	  <Status405>0</Status405>
	  <Status5XX>14</Status5XX>
	  <Status501>0</Status501>
	  <Status502>0</Status502>
	  <Status503>0</Status503>
	  <Status504>0</Status504>
</DescribeDomainStatusCodeCountResponse>
```

`JSON` 格式

```
{
    "RequestId": "C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E",
    "Status2XX": 951472,
    "Status200": 951159,
    "Status3XX": 133209,
    "Status4XX": 5653,
    "Status403": 0,
    "Status404": 897,
    "Status405": 0,
    "Status5XX": 14,
    "Status501": 0,
    "Status502": 0,
    "Status503": 0,
    "Status504": 0
}
```

## 错误码

访问[错误中心](https://error-center.alibabacloud.com/status/product/ddoscoo)查看更多错误码。

