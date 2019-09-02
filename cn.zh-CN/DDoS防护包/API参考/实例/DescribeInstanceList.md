# DescribeInstanceList {#doc_api_ddosbgp_DescribeInstanceList .reference}

调用DescribeInstanceList接口查询防护包实例的详细信息。

**说明：** DDoS防护包的API接口目前仅对企业版DDoS防护包用户开放。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=ddosbgp&api=DescribeInstanceList&type=RPC&version=2018-07-20)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeInstanceList|要执行的操作，取值：**DescribeInstanceList**。

 |
|PageNo|Integer|是|1|列表的页码，默认值为**1**。

 |
|PageSize|Integer|是|10|分页查询时每页的行数，最大值为**50**，默认值为**10**。

 |
|DdosRegionId|String|否|cn-hangzhou|实例所在地区ID。

 |
|InstanceIdList|String|否|\['ddosbgp-cn-xx','ddosbpg-cn-xxx'\]|指定要查询的防护包实例ID，多个ID间用逗号分隔。以JSON数组串格式传入，例如，\\'ddosbgp-cn-xx','ddosbpg-cn-xxx'。

 **说明：** 若不传入该参数，则返回所有防护包信息。

 |
|InstanceType|String|否|0|指定要查询的防护包实例的类型，取值：

 **说明：** 若不传入该参数，则返回所有防护包信息。

 -   0：专业版
-   1：企业版

 |
|Ip|String|否|1.1.1.1|指定要查询的防护包实例的防护对象IP。

 **说明：** 若不传入该参数，则返回所有防护包信息。

 |
|IpVersion|String|否|IPv4|指定要查询的防护包实例的防护IP类型，取值：

 **说明：** 若不传入该参数，则返回所有防护包信息。

 -   IPv4
-   IPv6

 |
|Orderby|String|否|expireTime|排序字段，取值：**expireTime**（到期时间）。

 |
|Orderdire|String|否|asc|排序方向，取值：

 -   **desc**：倒序
-   **asc**：顺序

 |
|Remark|String|否|test|指定要查询的防护包实例的备注。

 **说明：** 若不传入该参数，则返回所有防护包信息。

 |
|ResourceGroupId|String|否|test|资源组ID。

 |
|Tag.N.Key|String|否|test|标签的Key值。若有多个标签，依次传入Tag.1.Key、Tag.2.Key、Tag.3.Key ...

 |
|Tag.N.Value|String|否|test|标签的Value值。若有多个标签，依次传入Tag.1.Value、Tag.2.Value、Tag.3.Value ...

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|InstanceList| | |防护包实例的详细信息。

 |
|AutoRenewal|Boolean|false|是否开启自动续费。

 |
|BlackholdingCount|String|0|防护包中正在黑洞中的IP数量。

 |
|ExpireTime|Long|1560009600000|防护包的到期时间。

 |
|GmtCreate|Long|1554708159000|防护包的创建时间。

 |
|InstanceId|String|ddosbgp-cn-xx|防护包实例ID。

 |
|IpType|String|IPv4|防护包的防护IP类型。

 |
|Remark|String|test|防护包的备注。

 |
|Status|String|1|实例状态，取值：

 -   **1**：正常
-   **2**：过期
-   **3**：释放

 |
|RequestId|String|C3F7E6AE-43B2-4730-B6A3-FD17552B8F65|本次请求的ID。

 |
|Total|Long|1|返回结果的总数。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeInstanceList
&PageNo=1
&PageSize=10
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeInstanceListResponse>
     <RequestId>5DE4D6B1-8D6D-4AC3-84AF-5EE0A4C2778E</RequestId>
     <InstanceList>
           <Instance>
                 <Status>1</Status>
                 <AutoRenewal>true</AutoRenewal>
                 <IpType>IPv4</IpType>
                 <ExpireTime>1560009600000</ExpireTime>
                 <InstanceId>ddosbgp-cn-xx</InstanceId>
                 <GmtCreate>1554708159000</GmtCreate>
                 <Remark>test</Remark>
                 <BlackholdingCount>0</BlackholdingCount>
           </Instance>
     </InstanceList>
     <Total>1</Total>
</DescribeInstanceListResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"C3F7E6AE-43B2-4730-B6A3-FD17552B8F65",
	"Total":1,
	"InstanceList":[
		{
			"Status":"1",
			"AutoRenewal":true,
			"IpType":"IPv4",
			"ExpireTime":1560009600000,
			"InstanceId":"ddosbgp-cn-xx",
			"Remark":"test",
			"GmtCreate":1554708159000,
			"BlackholdingCount":0
		}
	]
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/ddosbgp)查看更多错误码。

