# DescribeDomainViewTopUrl

调用DescribeDomainViewTopUrl查询指定时间段内网站业务访问量最大的前N个URL。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=ddoscoo&api=DescribeDomainViewTopUrl&type=RPC&version=2020-01-01)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeDomainViewTopUrl|要执行的操作。取值：**DescribeDomainViewTopUrl**。 |
|EndTime|Long|是|1583683200|查询结束时间。时间戳格式，单位：秒。

 **说明：** 必须为整点分钟。 |
|StartTime|Long|是|1582992000|查询开始时间。时间戳格式，单位：秒。

 **说明：** 必须为整点分钟。 |
|Top|Integer|是|5|返回URL的数量。取值范围：**1**~**100**。 |
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
|UrlList|Array of Url| |网站业务的访问量TOP URL列表。 |
|Count|Long|3390671|请求数量。 |
|Domain|String|www.aliyun.com|网站域名。 |
|Url|String|Lw==|URL。使用BASE64加密表示。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=DescribeDomainViewTopUrl
&EndTime=1583683200
&StartTime=1582992000
&Top=5
&<公共请求参数>
```

正常返回示例

`XML` 格式

```
<DescribeDomainViewTopUrlResponse>
	  <RequestId>C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E</RequestId>
	  <UrlList>
		    <Count>3390671</Count>
		    <Domain>www.aliyun.com</Domain>
		    <Url>Lw==</Url>
	  </UrlList>
</DescribeDomainViewTopUrlResponse>
```

`JSON` 格式

```
{
    "RequestId": "C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E",
    "UrlList": [
        {
            "Count": 3390671,
            "Domain": "www.aliyun.com",
            "Url": "Lw=="
        }
    ]
}
```

## 错误码

访问[错误中心](https://error-center.alibabacloud.com/status/product/ddoscoo)查看更多错误码。

