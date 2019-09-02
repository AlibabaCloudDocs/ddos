# DescribeRegions {#doc_api_ddosbgp_DescribeRegions .reference}

调用DescribeRegions接口查看支持DDoS防护包服务的地域信息。

**说明：** DDoS防护包的API接口目前仅对企业版DDoS防护包用户开放。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=ddosbgp&api=DescribeRegions&type=RPC&version=2018-07-20)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeRegions|要执行的操作，取值：**DescribeRegions**。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|Boolean|true|响应状态码。

 |
|Regions| | |防护包支持的地域信息。

 |
|RegionEnName|String|shanghai|地域英文名称。

 |
|RegionId|String|cn-shanghai|地域ID。

 |
|RegionName|String|上海|地域中文名称。

 |
|RequestId|String|C3D66E07-41BF-41B7-A4BF-83A9E08E1C09|本次请求的ID。

 |
|Success|Boolean|true|是否成功调用请求。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeRegions
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeRegionsResponse>
     <RequestId>C3D66E07-41BF-41B7-A4BF-83A9E08E1C09</RequestId>
     <Regions>
           <Region>
                 <RegionId>cn-shenzhen</RegionId>
           </Region>
           <Region>
                 <RegionId>cn-qingdao</RegionId>
           </Region>
           <Region>
                 <RegionId>cn-beijing</RegionId>
           </Region>
           <Region>
                 <RegionId>cn-shanghai</RegionId>
           </Region>
           <Region>
                 <RegionId>cn-hongkong</RegionId>
           </Region>
           <Region>
                 <RegionId>cn-huhehaote</RegionId>
           </Region>
           <Region>
                 <RegionId>cn-zhangjiakou</RegionId>
           </Region>
           <Region>
                 <RegionId>us-west-1</RegionId>
           </Region>
           <Region>
                 <RegionId>cn-hangzhou</RegionId>
           </Region>
     </Regions>
     <Success>true</Success>
     <Code>200</Code>
</DescribeRegionsResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"9C48E43E-58A6-4A08-A858-4C9BB9631870",
	"Regions":[
		{
			"RegionId":"cn-shenzhen"
		},
		{
			"RegionId":"cn-qingdao"
		},
		{
			"RegionId":"cn-beijing"
		},
		{
			"RegionId":"cn-shanghai"
		},
		{
			"RegionId":"cn-hongkong"
		},
		{
			"RegionId":"cn-huhehaote"
		},
		{
			"RegionId":"cn-zhangjiakou"
		},
		{
			"RegionId":"us-west-1"
		},
		{
			"RegionId":"cn-hangzhou"
		}
	],
	"Success":true,
	"Code":"200"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/ddosbgp)查看更多错误码。

