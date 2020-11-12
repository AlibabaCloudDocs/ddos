# DescribeDDosEventSrcIp

调用DescribeDDosEventSrcIp查询某次流量型攻击的攻击来源IP详情。

**说明：** 目前该接口仅适用于查询流量型攻击的数据，不适用于查询Web资源消耗型和连接型攻击的数据。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=ddoscoo&api=DescribeDDosEventSrcIp&type=RPC&version=2020-01-01)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeDDosEventSrcIp|要执行的操作。取值：**DescribeDDosEventSrcIp**。 |
|EventType|String|是|defense|要查询的攻击事件的类型。取值：

 -   **defense**：表示流量型攻击清洗事件。
-   **blackhole**：表示流量型攻击黑洞事件。 |
|Ip|String|是|203.\*\*\*.\*\*\*.199|受攻击的高防IP。 |
|Range|Long|是|2|要返回的攻击来源IP的个数。按照攻击流量由大到小排序，默认返回前**5**个IP。 |
|StartTime|Long|是|1598948471|要查询事件的开始时间戳，单位：秒。

 **说明：** 您可以调用[DescribeDDosAllEventList](~~188604~~)查询所有事件的开始时间信息。 |

调用API时，除了本文中该API的请求参数，还需加入阿里云API公共请求参数。公共请求参数的详细介绍，请参见[公共参数](~~157269~~)。

调用API的请求格式，请参见本文**示例**中的请求示例。

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|Ips|Array of EventSrcIp| |攻击来源IP信息。 |
|AreaId|String|110000|攻击来源地域的代码。更多信息，请参见[地域代码](~~167926~~)。例如，**110000**表示中国北京市、**us**表示美国。 |
|Isp|String|100026|攻击来源网络运营商。取值：

 -   **100017**：电信
-   **100026**：联通
-   **100025**：移动
-   **100027**：教育网
-   **100020**：铁通
-   **1000143**：鹏博士
-   **100080**：歌华
-   **1000139**：广电
-   **100023**：有线通
-   **100063**：方正宽带
-   **1000337**：皓宽网络
-   **100021**：世纪互联
-   **1000333**：华数传媒
-   **100093**：网宿
-   **1000401**：腾讯
-   **100099**：百度
-   **1000323**：阿里云
-   **100098**：阿里巴巴 |
|SrcIp|String|218.\*\*\*.\*\*\*.24|攻击来源IP。 |
|RequestId|String|38A0224E-FDBC-4733-A362-B391827FC1E9|本次请求的ID。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=DescribeDDosEventSrcIp
&EventType=defense
&Ip=203.***.***.199
&Range=2
&StartTime=1598948471
&<公共请求参数>
```

正常返回示例

`XML` 格式

```
<DescribeDDosEventSrcIpResponse>
	  <RequestId>38A0224E-FDBC-4733-A362-B391827FC1E9</RequestId>
	  <Ips>
		    <Isp>100026</Isp>
		    <AreaId>110000</AreaId>
		    <SrcIp>218.***.***.24</SrcIp>
	  </Ips>
	  <Ips>
		    <Isp></Isp>
		    <AreaId>us</AreaId>
		    <SrcIp>193.***.***.174</SrcIp>
	  </Ips>
</DescribeDDosEventSrcIpResponse>
```

`JSON` 格式

```
{
	"RequestId": "38A0224E-FDBC-4733-A362-B391827FC1E9",
	"Ips": [
		{
			"Isp": "100026",
			"AreaId": "110000",
			"SrcIp": "218.***.***.24"
		},
		{
			"Isp": "",
			"AreaId": "us",
			"SrcIp": "193.***.***.174"
		}
	]
}
```

## 错误码

访问[错误中心](https://error-center.aliyun.com/status/product/ddoscoo)查看更多错误码。

