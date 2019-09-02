# DescribeDdosEvent {#doc_api_ddosbgp_DescribeDdosEvent .reference}

调用DescribeDdosEvent接口查看指定防护包上的DDoS事件。

**说明：** DDoS防护包的API接口目前仅对企业版DDoS防护包用户开放。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=ddosbgp&api=DescribeDdosEvent&type=RPC&version=2018-07-20)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeDdosEvent|要执行的操作，取值：**DescribeDdosEvent**。

 |
|EndTime|Integer|是|1557909844|查询结束时间，秒级时间戳。

 |
|InstanceId|String|是|ddosbgp-cn-x1|要查询的防护包实例ID。

 |
|PageNo|Integer|是|1|列表的页码，默认值为**1**。

 |
|PageSize|Integer|是|10|分页查询时每页的行数，最大值为**50**，默认值为**10**。

 |
|StartTime|Integer|是|1557305044|查询开始时间，秒级时间戳。

 |
|Ip|String|否|1.1.1.1|要查询的防护对象IP。

 |
|ResourceGroupId|String|否|test|资源组ID。

 |
|ResourceRegionId|String|否|cn-hangzhou|资源组地区ID。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Events| | |DDoS事件信息。

 |
|EndTime|Integer|1557891306|攻击结束时间，秒级时间戳。

 |
|Ip|String|1.1.1.1|被攻击的IP。

 |
|Mbps|Integer|110000|攻击流量大小，单位为Mbps。

 |
|Pps|Integer|0|攻击报文数量，单位为pps

 |
|StartTime|Integer|1557889506|攻击开始时间，秒级时间戳。

 |
|Status|String|defense\_end|事件状态，取值：

 -   **hole\_begin**：黑洞中
-   **hole\_end**：黑洞结束
-   **defense\_begin**：清洗中
-   **defense\_end**：清洗结束

 |
|RequestId|String|6A507DC8-F657-4C13-84E2-D1D1B9400753|本次请求的ID。

 |
|Total|Long|8|DDoS事件总数。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeDdosEvent
&EndTime=1557909844
&InstanceId=ddosbgp-cn-x1
&PageNo=1
&PageSize=10
&StartTime=1557305044
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeDdosEventResponse>
     <RequestId>6A507DC8-F657-4C13-84E2-D1D1B9400753</RequestId>
     <Events>
           <Event>
                 <Pps>0</Pps>
                 <Status>defense_end</Status>
                 <Ip>1.1.1.1</Ip>
                 <Mbps>110000</Mbps>
                 <EndTime>1557891306</EndTime>
                 <StartTime>1557889506</StartTime>
           </Event>
     </Events>
     <Total>1</Total>
</DescribeDdosEventResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"6A507DC8-F657-4C13-84E2-D1D1B9400753",
	"Events":[
		{
			"Pps":0,
			"Ip":"1.1.1.1",
			"Status":"defense_end",
			"Mbps":110000,
			"EndTime":1557891306,
			"StartTime":1557889506
		}
	],
	"Total":8
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/ddosbgp)查看更多错误码。

