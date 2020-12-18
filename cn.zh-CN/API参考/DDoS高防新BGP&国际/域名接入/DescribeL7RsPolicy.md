# DescribeL7RsPolicy

调用DescribeL7RsPolicy查询网站业务转发规则的回源策略。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=ddoscoo&api=DescribeL7RsPolicy&type=RPC&version=2020-01-01)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeL7RsPolicy|要执行的操作。取值：**DescribeL7RsPolicy**。 |
|Domain|String|是|www.aliyun.com|要查询的网站业务的域名。

 **说明：** 域名必须已经配置过网站业务转发规则。您可以调用[DescribeDomains](~~91724~~)查询所有已经配置过网站业务转发规则的域名。 |
|RegionId|String|否|cn-hangzhou|DDoS高防服务的地域ID。取值：

 -   **cn-hangzhou**：表示DDoS高防（新BGP）服务。
-   **ap-southeast-1**：表示DDoS高防（国际）服务。 |
|ResourceGroupId|String|否|rg-acfm2pz25js\*\*\*\*|DDoS高防实例在资源管理服务中所属的资源组ID。默认为空，即属于默认资源组。

 关于资源组的更多信息，请参见[创建资源组](~~94485~~)。 |
|RealServers.N|RepeatList|否|1.\*\*\*.\*\*\*.1|要查询的源站服务器地址列表。 |

调用API时，除了本文中该API的请求参数，还需加入阿里云API公共请求参数。公共请求参数的详细介绍，请参见[公共参数](~~157269~~)。

调用API的请求格式，请参见本文**示例**中的请求示例。

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|Attributes|Array of AttributeItem| |回源参数信息。 |
|Attribute|Struct| |回源参数。 |
|Weight|Integer|100|服务器的权重。仅在使用轮询算法（**ProxyMode**为**rr**）时生效。

 权重取值范围：**1**~**100**，默认值为**100**。权重越高的服务器分配到的请求越多。 |
|RealServer|String|1.\*\*\*.\*\*\*.1|源站服务器地址。 |
|RsType|Integer|0|源站服务器的地址类型。取值：

 -   **0**：表示源站服务器的IP地址。
-   **1**：表示源站服务器的域名地址。 |
|ProxyMode|String|rr|回源负载均衡算法。取值：

 -   **ip\_hash**：表示IP Hash算法。根据请求来源IP进行HASH映射，将同一个IP的所有请求定向到一个源站服务器。
-   **rr**：表示轮询算法。将所有请求轮流分配给不同源站服务器。
-   **least\_time**：表示Least Time算法。该算法通过智能DNS解析能力，保证业务流量从接入防护节点到转发回源站服务器整个链路的时延最短。 |
|RequestId|String|9E7F6B2C-03F2-462F-9076-B782CF0DD502|本次请求的ID。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=DescribeL7RsPolicy
&Domain=www.aliyun.com
&<公共请求参数>
```

正常返回示例

`XML` 格式

```
<DescribeL7RsPolicyResponse>
	  <RequestId>9E7F6B2C-03F2-462F-9076-B782CF0DD502</RequestId>
	  <Attributes>
		    <RealServer>1.***.***.1</RealServer>
		    <Attribute>
			      <Weight>100</Weight>
		    </Attribute>
	  </Attributes>
	  <Attributes>
		    <RealServer>2.***.***.2</RealServer>
		    <Attribute>
			      <Weight>100</Weight>
		    </Attribute>
	  </Attributes>
	  <ProxyMode>rr</ProxyMode>
</DescribeL7RsPolicyResponse>
```

`JSON` 格式

```
{
	"RequestId": "9E7F6B2C-03F2-462F-9076-B782CF0DD502",
	"Attributes": [
		{
			"RealServer": "1.***.***.1",
			"Attribute": {
				"Weight": 100
			}
		},
		{
			"RealServer": "2.***.***.2",
			"Attribute": {
				"Weight": 100
			}
		}
	],
	"ProxyMode": "rr"
}
```

## 错误码

访问[错误中心](https://error-center.aliyun.com/status/product/ddoscoo)查看更多错误码。

