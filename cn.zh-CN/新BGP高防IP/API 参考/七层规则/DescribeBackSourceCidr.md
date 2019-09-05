# DescribeBackSourceCidr {#doc_api_ddoscoo_DescribeBackSourceCidr .reference}

调用DescribeBackSourceCidr查询回源网段。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=ddoscoo&api=DescribeBackSourceCidr&type=RPC&version=2017-12-28)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeBackSourceCidr|系统规定参数。取值：**DescribeBackSourceCidr**。

 |
|Line|String|否|coop-line-001|要查询的防护线路。

 |
|ResourceGroupId|String|否|test|资源组ID。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|CidrList| |\["47.97.128.0/25","47.97.128.128/25"\]|回源IP段列表。

 |
|RequestId|String|CF33B4C3-196E-4015-AADD-5CAD00057B80|本次请求的ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeBackSourceCidr
&Line=coop-line-001
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeBackSourceCidrResponse>
     <CidrList>
          <element>47.xx.xx.0/25</element>
          <element>47.xx.xx.128/25</element>
     </CidrList>
     <RequestId>0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc</RequestId>
</DescribeBackSourceCidrResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc",
	"CidrList":[
		"47.xx.xx.0/25",
		"47.xx.xx.128/25"
	]
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/ddoscoo)查看更多错误码。

