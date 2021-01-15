# DescribeInstanceSpecs

调用DescribeInstanceSpecs查询指定的DDoS原生防护企业版实例的规格信息。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=ddosbgp&api=DescribeInstanceSpecs&type=RPC&version=2018-07-20)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeInstanceSpecs|要执行的操作，取值：**DescribeInstanceSpecs**。 |
|InstanceIdList|String|是|\["ddosbgp-cn-n6w1r7nz\*\*\*\*"\]|要查询的DDoS原生防护企业版实例的ID。使用JSON数组转化的字符串格式表示。JSON数组中的每个元素表示一个实例ID（字符串格式），多个ID间使用英文逗号（,）分隔。

 **说明：** 您可以调用[DescribeInstanceList](~~118698~~)查询指定地域下所有DDoS原生防护企业版实例的ID。 |
|RegionId|String|否|cn-hangzhou|DDoS原生防护企业版实例的地域ID。默认为**cn-hangzhou**，表示华东1（杭州）。

 **说明：** 如果您的实例不在华东1（杭州）地域，则此处必须填写实例所在地域的ID。您可以调用[DescribeRegions](~~118703~~)查询所有的**RegionId**。 |
|ResourceGroupId|String|否|rg-acfm2pz25js\*\*\*\*|DDoS原生防护企业版实例在资源管理服务中所属的资源组ID。默认为空，即属于默认资源组。

 关于资源组的更多信息，请参见[创建资源组](~~94485~~)。 |

调用API时，除了本文中该API的请求参数，还需加入阿里云API公共请求参数。公共请求参数的详细介绍，请参见[公共参数](~~118841~~)。

调用API的请求格式，请参见本文**示例**中的请求示例。

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|InstanceSpecs|Array of InstanceSpec| |DDoS原生防护企业版实例的规格信息，包含全力防护的开启状态、可用和已用的全力防护次数等。 |
|AvailableDefenseTimes|Integer|2|当前可用的全力防护次数。 |
|AvailableDeleteBlackholeCount|String|100|当前可用的解除黑洞次数。 |
|InstanceId|String|ddosbgp-cn-n6w1r7nz\*\*\*\*|DDoS原生防护企业版实例的ID。 |
|IsFullDefenseMode|Integer|1|该实例是否开启了全力防护模式。取值：

 -   **0**：未开启全力防护模式。
-   **1**：开启了全力防护模式。 |
|PackConfig|Struct| |DDoS原生防护企业版实例的配置信息，包含防护IP数量、防护带宽信息等。 |
|BindIpCount|Integer|0|已添加防护的IP数量。 |
|IpAdvanceThre|Integer|300|被防护IP的弹性防护阈值。单位：Gbps。 |
|IpBasicThre|Integer|20|被防护IP的基础防护阈值。单位：Gbps。 |
|IpSpec|Integer|100|可添加的防护IP的数量。 |
|NormalBandwidth|Integer|200|正常业务带宽。单位：Mbps。 |
|PackAdvThre|Integer|300|原生防护企业版实例的弹性防护带宽。单位：Gbps。 |
|PackBasicThre|Integer|20|原生防护企业版实例的基础防护带宽。单位：Gbps。 |
|Region|String|cn-hangzhou|DDoS原生防护企业版实例的地域ID。

 **说明：** 您可以调用[DescribeRegions](~~118703~~)查询地域ID的具体含义。 |
|TotalDefenseTimes|Integer|2|总共可用的全力防护次数。 |
|RequestId|String|5840AB9F-1419-4620-807D-5EA476090247|本次请求的ID。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=DescribeInstanceSpecs
&InstanceIdList=[\"ddosbgp-cn-n6w1r7nz****\"]
&<公共请求参数>
```

正常返回示例

`XML` 格式

```
<DescribeInstanceSpecsResponse>
	  <RequestId>5840AB9F-1419-4620-807D-5EA476090247</RequestId>
	  <InstanceSpecs>
		    <TotalDefenseTimes>2</TotalDefenseTimes>
		    <IsFullDefenseMode>1</IsFullDefenseMode>
		    <InstanceId>ddosbgp-cn-n6w1r7nz****</InstanceId>
		    <AvailableDefenseTimes>2</AvailableDefenseTimes>
		    <Region>cn-hangzhou</Region>
		    <AvailableDeleteBlackholeCount>100</AvailableDeleteBlackholeCount>
		    <PackConfig>
			      <PackAdvThre>300</PackAdvThre>
			      <IpSpec>100</IpSpec>
			      <NormalBandwidth>200</NormalBandwidth>
			      <BindIpCount>0</BindIpCount>
			      <IpAdvanceThre>300</IpAdvanceThre>
			      <PackBasicThre>20</PackBasicThre>
			      <IpBasicThre>20</IpBasicThre>
		    </PackConfig>
	  </InstanceSpecs>
</DescribeInstanceSpecsResponse>
```

`JSON` 格式

```
{
	"RequestId": "5840AB9F-1419-4620-807D-5EA476090247",
	"InstanceSpecs": [
		{
			"TotalDefenseTimes": 2,
			"IsFullDefenseMode": 1,
			"InstanceId": "ddosbgp-cn-n6w1r7nz****",
			"AvailableDefenseTimes": 2,
			"Region": "cn-hangzhou",
			"AvailableDeleteBlackholeCount": 100,
			"PackConfig": {
				"PackAdvThre": 300,
				"IpSpec": 100,
				"NormalBandwidth": 200,
				"BindIpCount": 0,
				"IpAdvanceThre": 300,
				"PackBasicThre": 20,
				"IpBasicThre": 20
			}
		}
	]
}
```

## 错误码

访问[错误中心](https://error-center.alibabacloud.com/status/product/ddosbgp)查看更多错误码。

