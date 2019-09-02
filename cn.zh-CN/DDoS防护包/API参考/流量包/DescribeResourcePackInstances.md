# DescribeResourcePackInstances {#doc_api_ddosbgp_DescribeResourcePackInstances .reference}

调用DescribeResourcePackInstances接口查询抗D流量包信息。

**说明：** DDoS防护包的API接口目前仅对企业版DDoS防护包用户开放。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=ddosbgp&api=DescribeResourcePackInstances&type=RPC&version=2018-07-20)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeResourcePackInstances|要执行的操作，取值：**DescribeResourcePackInstances**。

 |
|CurrentPage|Integer|是|1|列表的页码，默认值为**1**。

 |
|PageSize|Integer|是|10|分页查询时每页显示的行数，最大值为**50**，默认值为**10**。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|40B322C3-464E-477F-B137-46E64349F0E9|本次请求的ID。

 |
|ResourcePacks| | |抗D流量包信息。

 |
|CurrCapacity|Long|0|可用防护流量，单位为Byte。

 |
|EndTime|Long|1649433600000|失效时间。

 |
|InitCapacity|Long|100000000000000|初始防护流量，单位为Byte。

 |
|ResourcePackId|String|DDOSFLOWBAG-cn-o4012thfl000b5|抗D流量包ID。

 |
|StartTime|Long|1554708226000|生效时间。

 |
|Status|String|valid|流量包的状态，取值：

 -   **closed**：失效
-   **valid**：有效

 |
|TotalCount|Integer|1|返回结果的总数。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

https://ddosbgp.aliyuncs.com/?Action=DescribeResourcePackInstances
&CurrentPage=1
&PageSize=10
&公共请求参数

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeResourcePackInstancesResponse>
     <TotalCount>1</TotalCount>
     <ResourcePacks>
           <ResourcePack>
                 <Status>valid</Status>
                 <ResourcePackId>DDOSFLOWBAG-cn-xx</ResourcePackId>
                 <InitCapacity>100000000000000</InitCapacity>
                 <EndTime>1649433600000</EndTime>
                 <StartTime>1554708226000</StartTime>
                 <CurrCapacity>0</CurrCapacity>
           </ResourcePack>
     </ResourcePacks>
     <RequestId>40B322C3-464E-477F-B137-46E64349F0E9</RequestId>
</DescribeResourcePackInstancesResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"TotalCount":1,
	"ResourcePacks":[
		{
			"Status":"valid",
			"ResourcePackId":"DDOSFLOWBAG-cn-o4012thfl000b5",
			"InitCapacity":100000000000000,
			"EndTime":1649433600000,
			"StartTime":1554708226000,
			"CurrCapacity":0
		}
	],
	"RequestId":"40B322C3-464E-477F-B137-46E64349F0E9"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/ddosbgp)查看更多错误码。

