# DescribeOpEntities {#doc_api_ddosbgp_DescribeOpEntities .reference}

调用DescribeOpEntities接口查询用户的操作日志。

**说明：** DDoS防护包的API接口目前仅对企业版DDoS防护包用户开放。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=ddosbgp&api=DescribeOpEntities&type=RPC&version=2018-07-20)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeOpEntities|要执行的操作，取值：**DescribeOpEntities**。

 |
|CurrentPage|Integer|是|1|列表的页码，默认值为**1**。

 |
|EndTime|Long|是|1557906714012|查询结束时间，秒级时间戳。

 |
|PageSize|Integer|是|10|分页查询时每页的行数，最大值为**50**，默认值为**10**。

 |
|StartTime|Long|是|1555314714011|查询开始时间，秒级时间戳。

 |
|InstanceId|String|否|ddosbgp-cn-x1|要查询的防护包实例ID。

 |
|OrderBy|String|否|opdate|排序字段，取值：**opdate**（操作时间）。

 |
|OrderDir|String|否|ASC|排序方向，取值：

 -   **ASC**：正序
-   **DESC**：倒序

 |
|ResourceGroupId|String|否|test|资源组ID。

 |
|ResourceRegionId|String|否|cn-hangzhou|资源组地区ID。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|OpEntities| | |操作日志信息。

 |
|EntityObject|String|ddosbgp-cn-o4013qftb006|操作对象，即防护包实例。

 |
|EntityType|Integer|1|操作对象类型，取值：**1**（实例）。

 |
|GmtCreate|Long|1557821673000|日志创建时间。

 |
|OpAccount|String|system|操作账号，取值：**system**（系统）。

 |
|OpAction|Integer|8|操作类型，取值：

 -   **3**：添加IP
-   **4**：解绑IP
-   **5**：实例降级
-   **6**：解除黑洞
-   **7**：重置解除黑洞次数
-   **8**：恢复弹性

 |
|OpDesc|String|\{\\"entity\\":\{\\"baseBandwidth\\":20,\\"elasticBandwidth\\":101\}\}|操作说明。

 |
|RequestId|String|52C8ECB0-0B1A-4E66-A31C-B6A855120E82|本次请求的ID。

 |
|TotalCount|Integer|1|返回结果的数量。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeOpEntities
&CurrentPage=1
&EndTime=1557906714012
&PageSize=10
&StartTime=1555314714011
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeOpEntitiesResponse>
     <TotalCount>1</TotalCount>
     <OpEntities>
           <OpEntity>
                 <OpAccount>system</OpAccount>
                 <OpDesc>{"entity":{"baseBandwidth":20,"elasticBandwidth":101}}</OpDesc>
                 <EntityObject>ddosbgp-cn-o4013qftb006</EntityObject>
                 <EntityType>1</EntityType>
                 <GmtCreate>1557821673000</GmtCreate>
                 <OpAction>8</OpAction>
           </OpEntity>
     </OpEntities>
     <RequestId>52C8ECB0-0B1A-4E66-A31C-B6A855120E82</RequestId>
</DescribeOpEntitiesResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"TotalCount":1,
	"OpEntities":[
		{
			"OpAccount":"system",
			"OpDesc":"{\"entity\":{\"baseBandwidth\":20,\"elasticBandwidth\":101}}",
			"EntityObject":"ddosbgp-cn-o4013qftb006",
			"EntityType":1,
			"GmtCreate":1557821673000,
			"OpAction":8
		}
	],
	"RequestId":"52C8ECB0-0B1A-4E66-A31C-B6A855120E82"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/ddosbgp)查看更多错误码。

