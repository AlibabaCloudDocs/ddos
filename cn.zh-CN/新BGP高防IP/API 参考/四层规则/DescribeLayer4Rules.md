# DescribeLayer4Rules {#doc_api_ddoscoo_DescribeLayer4Rules .reference}

调用DescribeLayer4Rules查询指定实例的四层转发规则。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=ddoscoo&api=DescribeLayer4Rules&type=RPC&version=2017-12-28)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeLayer4Rules|系统规定参数。取值：**DescribeLayer4Rules**。

 |
|InstanceId|String|是|ddoscoo-cn-XXXXX|要查询的实例ID。

 |
|Offset|Integer|是|0|开始索引位置，即从第几个结果开始返回。

 **说明：** 如果不传入该参数，则从第0个结果开始返回。

 |
|PageSize|String|是|50|分页大小，即每页显示多少个结果。最大值**50**。

 |
|ForwardProtocol|String|否|tcp|转发协议，取值：**TCP**。

 |
|FrontendPort|Integer|否|233|前端端口。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Listeners| | |Listeners数组。

 |
|BackendPort|Integer|233|后端使用的端口，范围：0-65535。

 |
|FrontendPort|Integer|233|前端使用的端口，范围：0-65535。

 |
|InstanceId|String|ddoscoo-cn-XXXXX|实例ID。

 |
|IsAutoCreate|Boolean|false|是否自动创建。如果是，则不允许删除和修改。

 |
|Protocol|String|tcp|协议类型。

 |
|RealServers| |\["1.1.1.1"\]|源站IP地址。

 |
|RequestId|String|CF33B4C3-196E-4015-AADD-5CAD00057B80|本次请求的ID。

 |
|Total|Long|10|结果总数。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeLayer4Rules
&InstanceId=ddoscoo-cn-XXXXX
&Offset=0
&PageSize=50
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeLayer4RulesResponse>
     <Listeners>
          <element>
               <BackendPort>80</BackendPort>
               <FrontendPort>80</FrontendPort>
               <InstanceId>0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc</InstanceId>
               <IsAutoCreate>true</IsAutoCreate>
               <Protocol>tcp</Protocol>
               <RealServers>
                    <element>1.1.1.1</element>
                    <element>2.2.2.2</element>
               </RealServers>
          </element>
     </Listeners>
     <RequestId>0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc</RequestId>
     <Total>1</Total>
</DescribeLayer4RulesResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Listeners":[
		{
			"RealServers":[
				"1.1.1.1",
				"2.2.2.2"
			],
			"BackendPort":80,
			"FrontendPort":80,
			"InstanceId":"0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc",
			"IsAutoCreate":true,
			"Protocol":"tcp"
		}
	],
	"RequestId":"0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc",
	"Total":1
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/ddoscoo)查看更多错误码。

