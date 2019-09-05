# DescribeInstanceStatistics {#doc_api_ddoscoo_DescribeInstanceStatistics .reference}

调用DescribeInstanceStatistics查询指定实例的统计信息。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=ddoscoo&api=DescribeInstanceStatistics&type=RPC&version=2017-12-28)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeInstanceStatistics|系统规定参数。取值：**DescribeInstanceStatistics**。

 |
|InstanceIds|String|是|\[\{"InstanceId":"ddoscoo-cn-XXXXX","InstanceId":"ddoscoo-cn-YYYYY"\}\]|要查询的实例ID数组（JSON字符串）。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|InstanceStatistics| | |实例的统计信息列表。

 |
|DefenseCountUsage|Integer|1|已使用防护次数。

 |
|DomainUsage|Integer|10|已使用域名的数量。

 |
|InstanceId|String|ddoscoo-cn-XXXXX|实例ID。

 |
|PortUsage|Integer|20|已使用四层规则的数量。

 |
|SiteUsage|Integer|1|已添加站点的数量。

 |
|RequestId|String|CF33B4C3-196E-4015-AADD-5CAD00057B80|本次请求的ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeInstanceStatistics
&InstanceIds=[{"InstanceId":"ddoscoo-cn-XXXXX","InstanceId":"ddoscoo-cn-YYYYY"}]
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeInstanceStatisticsResponse>
     <InstanceStatistics>
          <element>
               <DomainUsage>10</DomainUsage>
               <InstanceId>0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc</InstanceId>
               <PortUsage>20</PortUsage>
          </element>
     </InstanceStatistics>
     <RequestId>0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc</RequestId>
</DescribeInstanceStatisticsResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc",
	"InstanceStatistics":[
		{
			"DomainUsage":10,
			"PortUsage":20,
			"InstanceId":"0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc"
		}
	]
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/ddoscoo)查看更多错误码。

