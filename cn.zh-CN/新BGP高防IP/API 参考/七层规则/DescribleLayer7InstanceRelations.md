# DescribleLayer7InstanceRelations {#doc_api_ddoscoo_DescribleLayer7InstanceRelations .reference}

调用DescribleLayer7InstanceRelations查询七层防护实例和EIP的对应关系。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=ddoscoo&api=DescribleLayer7InstanceRelations&type=RPC&version=2017-12-28)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribleLayer7InstanceRelations|系统规定参数。取值：**DescribleLayer7InstanceRelations**。

 |
|DomainList.N|RepeatList|是|www.aliyun.com|要查询的域名列表。

 |
|ResourceGroupId|String|否|test|资源组ID。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Layer7InstanceRelations| | |七层实例的防护关系列表。

 |
|Domain|String|www.aliyun.com|域名。

 |
|InstanceDetails| | |实例信息列表。

 |
|EipList| |\["203.107.0.0"\]|绑定的EIP列表。

 |
|FunctionVersion|String|default|功能版本，取值：

 -   **default**：标准版
-   **enhance**：增强版

 |
|InstanceId|String|ddoscoo-cn-XXXXX|实例ID

 |
|RequestId|String|CF33B4C3-196E-4015-AADD-5CAD00057B80|本次请求的ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribleLayer7InstanceRelations
&DomainList.1=www.aliyun.com
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribleLayer7InstanceRelationsResponse>
     <Layer7InstanceRelations>
          <element>
               <Domain>1.aliyun.com</Domain>
               <InstanceDetails>
                    <element>
                         <EipList>
                              <element>203.x.x.0</element>
                              <element>203.x.x.1</element>
                         </EipList>
                         <InstanceId>xxxxxx</InstanceId>
                    </element>
                    <element>
                         <EipList>
                              <element>203.x.x.0</element>
                              <element>203.x.x.1</element>
                         </EipList>
                         <FunctionVersion>default</FunctionVersion>
                         <InstanceId>xxxxxx</InstanceId>
                    </element>
               </InstanceDetails>
          </element>
     </Layer7InstanceRelations>
</DescribleLayer7InstanceRelationsResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Layer7InstanceRelations":[
		{
			"InstanceDetails":[
				{
					"FunctionVersion":"default",
					"InstanceId":"xxxxxx",
					"EipList":[
						"203.x.x.0",
						"203.x.x.1"
					]
				},
				{
					"InstanceId":"xxxxxx",
					"EipList":[
						"203.x.x.0",
						"203.x.x.1"
					]
				}
			],
			"Domain":"1.aliyun.com"
		}
	]
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/ddoscoo)查看更多错误码。

