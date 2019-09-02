# DescribeInstanceSpecs {#doc_api_ddosbgp_DescribeInstanceSpecs .reference}

调用DescribeInstanceSpecs接口查询防护包的规格信息。

**说明：** DDoS防护包的API接口目前仅对企业版DDoS防护包用户开放。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=ddosbgp&api=DescribeInstanceSpecs&type=RPC&version=2018-07-20)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeInstanceSpecs|要执行的操作，取值：**DescribeInstanceSpecs**。

 |
|InstanceIdList|String|是|\["ddosbgp-cn-x1","ddosbgp-cn-x2"\]|要查询的防护包实例ID，多个ID间以逗号分隔。以JSON字符串格式传入，例如，\\"ddosbgp-cn-x1","ddosbgp-cn-x2"。

 |
|DdosRegionId|String|否|cn-hangzhou|实例所在地区ID。

 |
|ResourceGroupId|String|否|test|资源组ID。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|InstanceSpecs| | |防护包实例的规格信息。

 |
|AvailableDeleteBlackholeCount|String|100|可用的解除黑洞次数。

 |
|InstanceId|String|ddosbgp-cn-x1|防护包实例ID。

 |
|PackConfig| | |防护包实例的配置信息。

 |
|BindIpCount|Integer|0|已添加的防护IP数量。

 |
|IpAdvanceThre|Integer|101|被防护IP的弹性防护阈值，单位为Gb。

 |
|IpBasicThre|Integer|20|被防护IP的基础防护阈值，单位为Gb。

 |
|IpSpec|Integer|100|可添加IP的数量。

 |
|PackAdvThre|Integer|100|防护包的弹性防护带宽，单位为Gb。

 |
|PackBasicThre|Integer|20|防护包的基础防护带宽，单位为Gb。

 |
|Region|String|cn-hangzhou|防护包实例的区域。

 |
|RequestId|String|CEB7F4F5-1DA8-41ED-A9C4-E0F0033E9E1F|本次请求的ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeInstanceSpecs
&InstanceIdList=["ddosbgp-cn-x1","ddosbgp-cn-x2"]
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeInstanceSpecsResponse>
     <InstanceSpecs>
           <InstanceSpec>
                 <Region>cn-hangzhou</Region>
                 <InstanceId>ddosbgp-cn-x1</InstanceId>
                 <AvailableDeleteBlackholeCount>100</AvailableDeleteBlackholeCount>
                 <PackConfig>
                       <IpBasicThre>20</IpBasicThre>
                       <BindIpCount>0</BindIpCount>
                       <PackBasicThre>20</PackBasicThre>
                       <IpAdvanceThre>101</IpAdvanceThre>
                       <IpSpec>100</IpSpec>
                       <PackAdvThre>101</PackAdvThre>
                 </PackConfig>
           </InstanceSpec>
     </InstanceSpecs>
     <RequestId>CEB7F4F5-1DA8-41ED-A9C4-E0F0033E9E1F</RequestId>
</DescribeInstanceSpecsResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"InstanceSpecs":[
		{
			"Region":"cn-hangzhou",
			"AvailableDeleteBlackholeCount":100,
			"InstanceId":"ddosbgp-cn-x1",
			"PackConfig":{
				"IpBasicThre":20,
				"BindIpCount":0,
				"PackBasicThre":20,
				"IpAdvanceThre":100,
				"PackAdvThre":101,
				"IpSpec":100
			}
		}
	],
	"RequestId":"D8D786F2-2008-4280-B9AB-8E6C4E8C2A16"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/ddosbgp)查看更多错误码。

