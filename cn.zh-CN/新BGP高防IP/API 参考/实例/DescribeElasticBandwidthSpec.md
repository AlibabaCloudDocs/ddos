# DescribeElasticBandwidthSpec {#doc_api_ddoscoo_DescribeElasticBandwidthSpec .reference}

调用DescribeElasticBandwidthSpec查询指定实例的弹性带宽规格。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=ddoscoo&api=DescribeElasticBandwidthSpec&type=RPC&version=2017-12-28)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeElasticBandwidthSpec|系统规定参数。取值：**DescribeElasticBandwidthSpec**。

 |
|InstanceId|String|是|ddoscoo-cn-XXXXX|要查询的实例ID。单次请求只支持查询1个实例。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|ElasticBandwidthSpec| |\[5, 10, 20, 30\]|弹性带宽规格。

 |
|RequestId|String|CF33B4C3-196E-4015-AADD-5CAD00057B80|本次请求的ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeElasticBandwidthSpec
&InstanceId=ddoscoo-cn-XXXXX
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeElasticBandwidthSpecResponse>
     <ElasticBandwidthSpec>
          <element>5</element>
          <element>10</element>
          <element>20</element>
          <element>30</element>
     </ElasticBandwidthSpec>
     <RequestId>0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc</RequestId>
</DescribeElasticBandwidthSpecResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc",
	"ElasticBandwidthSpec":[
		5,
		10,
		20,
		30
	]
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/ddoscoo)查看更多错误码。

