# DescribeInstanceDetails {#doc_api_ddoscoo_DescribeInstanceDetails .reference}

调用DescribeInstanceDetails查询指定实例的详情信息。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=ddoscoo&api=DescribeInstanceDetails&type=RPC&version=2017-12-28)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeInstanceDetails|系统规定参数。取值：**DescribeInstanceDetails**。

 |
|InstanceIds|String|是|\[\{"InstanceId":"ddoscoo-cn-XXXXX","InstanceId":"ddoscoo-cn-YYYYY"\}\]|要查询的实例ID数组（JSON字符串）。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|InstanceDetails| | |实例详情列表。

 |
|EipInfoList| | |与该实例绑定的EIP信息列表。

 |
|Eip|String|1.1.1.1|EIP值。

 |
|Status|String|normal|EIP状态，取值：

 -   **normal**：正常
-   **cleaning**：清洗中
-   **blackhole**：黑洞中

 |
|InstanceId|String|ddoscoo-cn-XXXXX|实例ID。

 |
|Line|String|coop-line-001|实例线路。例如，**coop-line-001**。

 |
|RequestId|String|CF33B4C3-196E-4015-AADD-5CAD00057B80|本次请求的ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeInstanceDetails
&InstanceIds=[{"InstanceId":"ddoscoo-cn-XXXXX","InstanceId":"ddoscoo-cn-YYYYY"}]
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeInstanceDetailsResponse>
     <InstanceDetails>
          <element>
               <EipInfoList>
                    <element>
                         <Eip>1.1.1.1</Eip>
                         <Status>normal</Status>
                    </element>
               </EipInfoList>
               <InstanceId>0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc</InstanceId>
               <Line>coop-line-001</Line>
          </element>
     </InstanceDetails>
     <RequestId>0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc</RequestId>
</DescribeInstanceDetailsResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"InstanceDetails":[
		{
			"InstanceId":"0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc",
			"Line":"coop-line-001",
			"EipInfoList":[
				{
					"Status":"normal",
					"Eip":"1.1.1.1"
				}
			]
		}
	],
	"RequestId":"0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/ddoscoo)查看更多错误码。

