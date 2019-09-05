# DescribeInstances {#doc_api_ddoscoo_DescribeInstances .reference}

调用DescribeInstances分页查询新BGP高防实例信息列表。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=ddoscoo&api=DescribeInstances&type=RPC&version=2017-12-28)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeInstances|系统规定参数。取值：**DescribeInstances**。

 |
|PageNo|String|是|1|分页页号，即从几页开始显示。最小值是**1**。

 |
|PageSize|String|是|10|分页大小，即每页显示多少条结果。最大值是**50**。

 |
|InstanceIds|String|否|\["ddoscoo-cn-XXXXX"\]|通过实例Id查询实例信息，传入要查询的实例Id数组（JSON字符串）。支持精确匹配。例如，\\"ddoscoo-cn-XXXX1", "ddoscoo-cn-XXXX2"。

 **说明：** 若传入该参数，则无需传入**Ip**和**Remark**。

 |
|Ip|String|否|1.1.1.1|通过实例Ip查询实例信息，传入要查询的实例Ip地址。支持精确匹配查询。

 **说明：** 若传入该参数，则无需传入**InstanceIds**和**Remark**。

 |
|Remark|String|否|testRemark|通过实例备注查询实例信息，传入要查询的实例的备注信息。支持模糊查询。

 **说明：** 若传入该参数，则无需传入**InstanceIds**和**Ip**。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Instances| | |实例信息列表。

 |
|ExpireTime|Long|2308402384|过期时间时间戳，单位：毫秒。

 |
|GmtCreate|Long|2308402384|创建时间时间戳，单位：毫秒。

 |
|InstanceId|String|ddoscoo-cn-XXXXX|实例ID。

 |
|Remark|String|testRemark|实例备注信息。最大500字节。

 |
|Status|Integer|1|实例售卖状态。

 -   **1**：正常
-   **2**：过期
-   **3**：释放

 |
|RequestId|String|CF33B4C3-196E-4015-AADD-5CAD00057B80|本次请求的ID。

 |
|Total|Long|10|实例总数。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://ddoscoo.cn-hangzhou.aliyuncs.com/?Action=DescribeInstances
&PageNo=1
&PageSize=10
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeInstancesResponse>
     <Instances>
          <element>
               <ExpireTime>20384032</ExpireTime>
               <GmtCreate>2308402384</GmtCreate>
               <InstanceId>0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc</InstanceId>
               <Remark>xxx</Remark>
               <Status>1</Status>
          </element>
     </Instances>
     <RequestId>0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc</RequestId>
     <Total>1</Total>
</DescribeInstancesResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc",
	"Instances":[
		{
			"Status":1,
			"ExpireTime":20384032,
			"InstanceId":"0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc",
			"GmtCreate":2308402384,
			"Remark":"xxx"
		}
	],
	"Total":1
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/ddoscoo)查看更多错误码。

