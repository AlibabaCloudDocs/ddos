# DescribePackIpList {#doc_api_ddosbgp_DescribePackIpList .reference}

调用DescribePackIpList接口查询防护包的防护IP列表信息。

**说明：** DDoS防护包的API接口目前仅对企业版DDoS防护包用户开放。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=ddosbgp&api=DescribePackIpList&type=RPC&version=2018-07-20)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribePackIpList|要执行的操作，取值：**DescribePackIpList**。

 |
|DdosRegionId|String|是|cn-hangzhou|实例所在地区ID。

 |
|InstanceId|String|是|ddosbgp-cn-x1|要查询的防护包实例ID。

 |
|PageNo|Integer|是|1|列表的页码，默认值为**1**。

 |
|PageSize|Integer|是|10|分页查询时每页的行数，最大值为**50**，默认值为**10**。

 |
|Ip|String|否|1.1.1.1|要查询的防护对象IP，设置后只返回指定IP的信息。

 |
|ProductName|String|否|ECS|要查询的防护对象IP的归属产品类型，取值：

 **说明：** 设置后只返回指定产品的防护IP信息。

 -   **ECS**
-   **SLB**
-   **EIP**
-   **WAF**

 |
|ResourceGroupId|String|否|test|资源组ID。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|200|响应状态码。

 |
|IpList| | |防护IP列表。

 |
|Ip|String|1.1.1.1|被防护IP。

 |
|Product|String|ECS|IP的归属产品，取值：

 -   **ECS**
-   **SLB**
-   **EIP**
-   **WAF**

 |
|Remark|String|test|归属产品备注，比如ECS实例的备注。

 |
|Status|String|normal|IP的状态，取值：

 -   **normal**：正常
-   **hole\_begin**：黑洞中

 |
|RequestId|String|B479FE9B-F0EB-423B-81E5-ECE2167BCF40|本次请求的ID。

 |
|Success|Boolean|true|是否成功调用请求。

 |
|Total|Integer|1|返回结果的数量。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribePackIpList
&DdosRegionId=cn-hangzhou
&InstanceId=ddosbgp-cn-x1
&PageNo=1
&PageSize=10
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribePackIpListResponse>
     <RequestId>8584D3B6-BB3C-441E-B1D6-E154ED25C032</RequestId>
     <IpList>
           <Ipitem>
                 <Status>normal</Status>
                 <Ip>1.1.1.1</Ip>
                 <Product>ECS</Product>
                 <Remark>test</Remark>
           </Ipitem>
     </IpList>
     <Success>true</Success>
     <Code>200</Code>
     <Total>1</Total>
</DescribePackIpListResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"B479FE9B-F0EB-423B-81E5-ECE2167BCF40",
	"IpList":[
		{
			"Ip":"1.1.1.1",
			"Status":"normal",
			"Product":"ECS",
			"Remark":"test"
		}
	],
	"Success":true,
	"Code":"200",
	"Total":1
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/ddosbgp)查看更多错误码。

