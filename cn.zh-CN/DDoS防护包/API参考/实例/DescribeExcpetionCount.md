# DescribeExcpetionCount {#doc_api_ddosbgp_DescribeExcpetionCount .reference}

调用DescribeExcpetionCount接口查询防护包异常信息。

**说明：** DDoS防护包的API接口目前仅对企业版DDoS防护包用户开放。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=ddosbgp&api=DescribeExcpetionCount&type=RPC&version=2018-07-20)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeExcpetionCount|要执行的操作，取值：**DescribeExcpetionCount**。

 |
|DdosRegionId|String|是|cn-hangzhou|实例所在地区ID。

 |
|ResourceGroupId|String|否|test|资源组ID。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|ExceptionIpCount|Integer|0|异常IP的数量，如被防护的ECS IP、SLB IP等。

 |
|ExpireTimeCount|Integer|1|7天内即将到期的实例数量。

 |
|RequestId|String|A3EEE55F-3B9F-4765-8C03-1A1A904F3451|本次请求的ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeExcpetionCount
&DdosRegionId=cn-hangzhou
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeExcpetionCountResponse>
     <ExpireTimeCount>1</ExpireTimeCount>
     <RequestId>58609615-FCF9-41DF-8B25-0D5C8DAB92BA</RequestId>
     <ExceptionIpCount>0</ExceptionIpCount>
</DescribeExcpetionCountResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"A3EEE55F-3B9F-4765-8C03-1A1A904F3451",
	"ExpireTimeCount":1,
	"ExceptionIpCount":0
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/ddosbgp)查看更多错误码。

