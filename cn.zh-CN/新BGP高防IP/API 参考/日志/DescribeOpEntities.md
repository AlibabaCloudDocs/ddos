# DescribeOpEntities {#doc_api_ddoscoo_DescribeOpEntities .reference}

调用DescribeOpEntities查询操作日志。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=ddoscoo&api=DescribeOpEntities&type=RPC&version=2017-12-28)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeOpEntities|系统规定参数。取值：**DescribeOpEntities**。

 |
|EndTime|Long|是|1536715558000|结束时间时间戳，单位：毫秒。

 |
|PageNo|Integer|是|1|页号，即从第几页开始显示。

 |
|PageSize|Integer|是|10|分页大小，即每页显示多少条结果。最大值50。

 |
|StartTime|Long|是|1534123558000|开始时间时间戳，单位：毫秒。

 |
|ResourceGroupId|String|否|test|资源组ID。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|OpEntities| | |操作日志。

 |
|EntityObject|String|2.2.2.2|操作对象的值，即操作的IP地址。

 |
|EntityType|Integer|1|操作对象类型。取值：**1**（IP类型）。

 |
|GmtCreate|Long|1536715558000|创建日志的时间戳，单位：毫秒。

 |
|OpAccount|String|123|操作人。

 |
|OpAction|Integer|1|操作类型。取值：**1**（修改弹性带宽）。

 |
|OpDesc|String|\{"newEntity":\{"elasticBandwidth":30\},"oldEntity":\{"elasticBandwidth":200\}\}|操作详情。OpDesc的JSON字符串，具体结构描述如下：

 -   **oldValue**，Struct类型，旧值，具体结构描述如下：
    -   **elasticBandwidth**，Integer类型，弹性带宽值。
-   **newValue**，Struct类型，新值，具体结构描述如下：
    -   **elasticBandwidth**，Integer类型，弹性带宽值。

 |
|RequestId|String|CF33B4C3-196E-4015-AADD-5CAD00057B80|本次请求的ID。

 |
|Total|Long|10|记录总数。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeOpEntities
&EndTime=1536715558000
&PageNo=1
&PageSize=10
&StartTime=1534123558000
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeOpEntitiesResponse>
     <OpEntities>
          <element>
               <entityObject>1.1.1.1</entityObject>
               <gmtCreate>1120384</gmtCreate>
               <opAction>2</opAction>
               <opDesc>
                    <newValue>
                         <elasticBandwidth>30</elasticBandwidth>
                    </newValue>
                    <oldValue>
                         <elasticBandwidth>10</elasticBandwidth>
                    </oldValue>
               </opDesc>
               <opResult>1</opResult>
          </element>
     </OpEntities>
     <Total>10</Total>
</DescribeOpEntitiesResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"OpEntities":[
		{
			"gmtCreate":1120384,
			"entityObject":"1.1.1.1",
			"opResult":1,
			"opDesc":{
				"newValue":{
					"elasticBandwidth":30
				},
				"oldValue":{
					"elasticBandwidth":10
				}
			},
			"opAction":2
		}
	],
	"Total":10
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/ddoscoo)查看更多错误码。

