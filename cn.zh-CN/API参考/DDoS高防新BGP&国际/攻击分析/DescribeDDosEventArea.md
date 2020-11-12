# DescribeDDosEventArea

调用DescribeDDosEventArea查询某次流量型攻击的来源地域详情。

**说明：** 目前该接口仅适用于查询流量型攻击的数据，不适用于查询Web资源消耗型和连接型攻击的数据。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=ddoscoo&api=DescribeDDosEventArea&type=RPC&version=2020-01-01)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeDDosEventArea|要执行的操作。取值：**DescribeDDosEventArea**。 |
|EventType|String|是|defense|要查询的攻击事件类型。取值：

 -   **defense**：表示流量型攻击清洗事件。
-   **blackhole**：表示流量型攻击黑洞事件。 |
|Ip|String|是|203.\*\*\*.\*\*\*.199|受攻击的高防IP。 |
|StartTime|Long|是|1598948471|要查询事件的开始时间戳，单位：秒。

 **说明：** 您可以调用[DescribeDDosAllEventList](~~188604~~)查询所有事件的开始时间信息。 |

调用API时，除了本文中该API的请求参数，还需加入阿里云API公共请求参数。公共请求参数的详细介绍，请参见[公共参数](~~157269~~)。

调用API的请求格式，请参见本文**示例**中的请求示例。

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|Areas|Array of EventArea| |攻击来源地域信息。 |
|Area|String|110000|攻击来源地域的代码。更多信息，请参见[地域代码](~~167926~~)。例如，**110000**表示中国北京市、**us**表示美国。 |
|InPkts|Long|228|攻击来源地域的请求包数量。 |
|RequestId|String|11710C9F-BC5E-481A-BEC5-C6D8FBFCA827|本次请求的ID。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=DescribeDDosEventArea
&EventType=defense
&Ip=203.***.***.199
&StartTime=1598948471
&<公共请求参数>
```

正常返回示例

`XML` 格式

```
<DescribeDDosEventAreaResponse>
	  <RequestId>11710C9F-BC5E-481A-BEC5-C6D8FBFCA827</RequestId>
	  <Areas>
		    <Area>us</Area>
		    <InPkts>2</InPkts>
	  </Areas>
	  <Areas>
		    <Area>110000</Area>
		    <InPkts>228</InPkts>
	  </Areas>
  </DescribeDDosEventAreaResponse>
```

`JSON` 格式

```
{
    "RequestId": "11710C9F-BC5E-481A-BEC5-C6D8FBFCA827",
    "Areas": [
        {
            "Area": "us",
            "InPkts": 2
        },
        {
            "Area": "110000",
            "InPkts": 228
        }
    ]
}
```

## 错误码

访问[错误中心](https://error-center.aliyun.com/status/product/ddoscoo)查看更多错误码。

