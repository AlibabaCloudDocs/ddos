# ModifyElasticBandWidth {#doc_api_ddoscoo_ModifyElasticBandWidth .reference}

调用ModifyElasticBandWidth修改指定实例的弹性防护带宽。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=ddoscoo&api=ModifyElasticBandWidth&type=RPC&version=2017-12-28)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|ModifyElasticBandWidth|系统规定参数。取值：**ModifyElasticBandWidth**。

 |
|ElasticBandwidth|Integer|是|30|新的弹性带宽值。

 |
|InstanceId|String|是|ddoscoo-cn-XXXXX|要操作的实例ID。单次请求只支持修改1个实例的弹性防护带宽，且目标实例必须是正常状态。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|CF33B4C3-196E-4015-AADD-5CAD00057B80|本次请求的ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=ModifyElasticBandWidth
&ElasticBandwidth=30
&InstanceId=ddoscoo-cn-XXXXX
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<ModifyElasticBandWidthResponse>
     <RequestId>0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc</RequestId>
</ModifyElasticBandWidthResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/ddoscoo)查看更多错误码。

