# DescribeRegions

调用DescribeRegions查询DDoS原生防护支持防护的云资产的地域信息。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=ddosbgp&api=DescribeRegions&type=RPC&version=2018-07-20)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeRegions|要执行的操作。取值：**DescribeRegions**。 |
|ResourceGroupId|String|否|rg-acfm2pz25js\*\*\*\*|DDoS原生防护实例在资源管理服务中所属的资源组ID。默认为空，即属于默认资源组。

 关于资源组的更多信息，请参见[创建资源组](~~94485~~)。 |
|RegionId|String|否|cn-hangzhou|要查询的地域ID。默认为**cn-hangzhou**，表示查询华东1（杭州）地域的DDoS原生防护实例支持防护的云资产的地域。

 如果需要查询其他地域ID，请参见[地域和可用区](~~40654~~)，获取对应的**RegionId**。 |

调用API时，除了本文中该API的请求参数，还需加入阿里云API公共请求参数。公共请求参数的详细介绍，请参见[公共参数](~~118841~~)。

调用API的请求格式，请参见本文**示例**中的请求示例。

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|200|HTTP状态码。 |
|Regions|Array of Region| |DDoS原生防护支持防护的云资产的地域信息，包含地域ID和名称等。 |
|RegionEnName|String|China \(Hangzhou\)|地域的英文名称。 |
|RegionId|String|cn-hangzhou|地域ID。 |
|RegionName|String|华东1（杭州）|地域的中文名称。 |
|RequestId|String|F7CA8B4E-FB15-4336-A351-8DC29D66EA82|本次请求的ID。 |
|Success|Boolean|true|是否调用成功。取值：

 -   **true**：表示调用成功。
-   **false**：表示调用失败。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=DescribeRegions
&<公共请求参数>
```

正常返回示例

`XML` 格式

```
<DescribeRegionsResponse>
	  <RequestId>F7CA8B4E-FB15-4336-A351-8DC29D66EA82</RequestId>
	  <Regions>
		    <RegionName>俄罗斯（莫斯科）</RegionName>
		    <RegionEnName>Russia (Moscow)</RegionEnName>
		    <RegionId>rus-west-1</RegionId>
	  </Regions>
	  <Regions>
		    <RegionName>华北2（北京）</RegionName>
		    <RegionEnName>China (Beijing)</RegionEnName>
		    <RegionId>cn-beijing</RegionId>
	  </Regions>
	  <Regions>
		    <RegionName>华北6（乌兰察布）</RegionName>
		    <RegionEnName>China (Ulanqab)</RegionEnName>
		    <RegionId>cn-wulanchabu</RegionId>
	  </Regions>
	  <Regions>
		    <RegionName>印度（孟买）</RegionName>
		    <RegionEnName>India (Mumbai)</RegionEnName>
		    <RegionId>ap-south-1</RegionId>
	  </Regions>
	  <Regions>
		    <RegionName>华北1（青岛）</RegionName>
		    <RegionEnName>China (Qingdao)</RegionEnName>
		    <RegionId>cn-qingdao</RegionId>
	  </Regions>
	  <Regions>
		    <RegionName>华东2（上海）</RegionName>
		    <RegionEnName>China (Shanghai)</RegionEnName>
		    <RegionId>cn-shanghai</RegionId>
	  </Regions>
	  <Regions>
		    <RegionName>中国（香港）</RegionName>
		    <RegionEnName>China (Hong Kong)</RegionEnName>
		    <RegionId>cn-hongkong</RegionId>
	  </Regions>
	  <Regions>
		    <RegionName>华南2（河源）</RegionName>
		    <RegionEnName>China (Heyuan)</RegionEnName>
		    <RegionId>cn-heyuan</RegionId>
	  </Regions>
	  <Regions>
		    <RegionName>德国（法兰克福）</RegionName>
		    <RegionEnName>Germany (Frankfurt)</RegionEnName>
		    <RegionId>eu-central-1</RegionId>
	  </Regions>
	  <Regions>
		    <RegionName>华北3（张家口）</RegionName>
		    <RegionEnName>China (Zhangjiakou)</RegionEnName>
		    <RegionId>cn-zhangjiakou</RegionId>
	  </Regions>
	  <Regions>
		    <RegionName>美国（硅谷）</RegionName>
		    <RegionEnName>US (Silicon Valley)</RegionEnName>
		    <RegionId>us-west-1</RegionId>
	  </Regions>
	  <Regions>
		    <RegionName>华南1（深圳）</RegionName>
		    <RegionEnName>China (Shenzhen)</RegionEnName>
		    <RegionId>cn-shenzhen</RegionId>
	  </Regions>
	  <Regions>
		    <RegionName>英国（伦敦）</RegionName>
		    <RegionEnName>UK (London)</RegionEnName>
		    <RegionId>eu-west-1</RegionId>
	  </Regions>
	  <Regions>
		    <RegionName>日本（东京）</RegionName>
		    <RegionEnName>Japan (Tokyo)</RegionEnName>
		    <RegionId>ap-northeast-1</RegionId>
	  </Regions>
	  <Regions>
		    <RegionName>阿联酋（迪拜）</RegionName>
		    <RegionEnName>UAE (Dubai)</RegionEnName>
		    <RegionId>me-east-1</RegionId>
	  </Regions>
	  <Regions>
		    <RegionName>西南1（成都）</RegionName>
		    <RegionEnName>China (Chengdu)</RegionEnName>
		    <RegionId>cn-chengdu</RegionId>
	  </Regions>
	  <Regions>
		    <RegionName>华南3（广州）</RegionName>
		    <RegionEnName>China (Guangzhou)</RegionEnName>
		    <RegionId>cn-guangzhou</RegionId>
	  </Regions>
	  <Regions>
		    <RegionName>新加坡</RegionName>
		    <RegionEnName>Singapore</RegionEnName>
		    <RegionId>ap-southeast-1</RegionId>
	  </Regions>
	  <Regions>
		    <RegionName>澳大利亚（悉尼）</RegionName>
		    <RegionEnName>Australia (Sydney)</RegionEnName>
		    <RegionId>ap-southeast-2</RegionId>
	  </Regions>
	  <Regions>
		    <RegionName>马来西亚（吉隆坡）</RegionName>
		    <RegionEnName>Malaysia (Kuala Lumpur)</RegionEnName>
		    <RegionId>ap-southeast-3</RegionId>
	  </Regions>
	  <Regions>
		    <RegionName>华北5（呼和浩特）</RegionName>
		    <RegionEnName>China (Hohhot)</RegionEnName>
		    <RegionId>cn-huhehaote</RegionId>
	  </Regions>
	  <Regions>
		    <RegionName>印度尼西亚（雅加达）</RegionName>
		    <RegionEnName>Indonesia (Jakarta)</RegionEnName>
		    <RegionId>ap-southeast-5</RegionId>
	  </Regions>
	  <Regions>
		    <RegionName>美国（弗吉尼亚）</RegionName>
		    <RegionEnName>US (Virginia)</RegionEnName>
		    <RegionId>us-east-1</RegionId>
	  </Regions>
	  <Regions>
		    <RegionName>华东1（杭州）</RegionName>
		    <RegionEnName>China (Hangzhou)</RegionEnName>
		    <RegionId>cn-hangzhou</RegionId>
	  </Regions>
	  <Code>200</Code>
	  <Success>true</Success>
</DescribeRegionsResponse>
```

`JSON` 格式

```
{
	"RequestId": "F7CA8B4E-FB15-4336-A351-8DC29D66EA82",
	"Regions": [
		{
			"RegionName": "俄罗斯（莫斯科）",
			"RegionEnName": "Russia (Moscow)",
			"RegionId": "rus-west-1"
		},
		{
			"RegionName": "华北2（北京）",
			"RegionEnName": "China (Beijing)",
			"RegionId": "cn-beijing"
		},
		{
			"RegionName": "华北6（乌兰察布）",
			"RegionEnName": "China (Ulanqab)",
			"RegionId": "cn-wulanchabu"
		},
		{
			"RegionName": "印度（孟买）",
			"RegionEnName": "India (Mumbai)",
			"RegionId": "ap-south-1"
		},
		{
			"RegionName": "华北1（青岛）",
			"RegionEnName": "China (Qingdao)",
			"RegionId": "cn-qingdao"
		},
		{
			"RegionName": "华东2（上海）",
			"RegionEnName": "China (Shanghai)",
			"RegionId": "cn-shanghai"
		},
		{
			"RegionName": "中国（香港）",
			"RegionEnName": "China (Hong Kong)",
			"RegionId": "cn-hongkong"
		},
		{
			"RegionName": "华南2（河源）",
			"RegionEnName": "China (Heyuan)",
			"RegionId": "cn-heyuan"
		},
		{
			"RegionName": "德国（法兰克福）",
			"RegionEnName": "Germany (Frankfurt)",
			"RegionId": "eu-central-1"
		},
		{
			"RegionName": "华北3（张家口）",
			"RegionEnName": "China (Zhangjiakou)",
			"RegionId": "cn-zhangjiakou"
		},
		{
			"RegionName": "美国（硅谷）",
			"RegionEnName": "US (Silicon Valley)",
			"RegionId": "us-west-1"
		},
		{
			"RegionName": "华南1（深圳）",
			"RegionEnName": "China (Shenzhen)",
			"RegionId": "cn-shenzhen"
		},
		{
			"RegionName": "英国（伦敦）",
			"RegionEnName": "UK (London)",
			"RegionId": "eu-west-1"
		},
		{
			"RegionName": "日本（东京）",
			"RegionEnName": "Japan (Tokyo)",
			"RegionId": "ap-northeast-1"
		},
		{
			"RegionName": "阿联酋（迪拜）",
			"RegionEnName": "UAE (Dubai)",
			"RegionId": "me-east-1"
		},
		{
			"RegionName": "西南1（成都）",
			"RegionEnName": "China (Chengdu)",
			"RegionId": "cn-chengdu"
		},
		{
			"RegionName": "华南3（广州）",
			"RegionEnName": "China (Guangzhou)",
			"RegionId": "cn-guangzhou"
		},
		{
			"RegionName": "新加坡",
			"RegionEnName": "Singapore",
			"RegionId": "ap-southeast-1"
		},
		{
			"RegionName": "澳大利亚（悉尼）",
			"RegionEnName": "Australia (Sydney)",
			"RegionId": "ap-southeast-2"
		},
		{
			"RegionName": "马来西亚（吉隆坡）",
			"RegionEnName": "Malaysia (Kuala Lumpur)",
			"RegionId": "ap-southeast-3"
		},
		{
			"RegionName": "华北5（呼和浩特）",
			"RegionEnName": "China (Hohhot)",
			"RegionId": "cn-huhehaote"
		},
		{
			"RegionName": "印度尼西亚（雅加达）",
			"RegionEnName": "Indonesia (Jakarta)",
			"RegionId": "ap-southeast-5"
		},
		{
			"RegionName": "美国（弗吉尼亚）",
			"RegionEnName": "US (Virginia)",
			"RegionId": "us-east-1"
		},
		{
			"RegionName": "华东1（杭州）",
			"RegionEnName": "China (Hangzhou)",
			"RegionId": "cn-hangzhou"
		}
	],
	"Code": "200",
	"Success": true
}
```

## 错误码

访问[错误中心](https://error-center.aliyun.com/status/product/ddosbgp)查看更多错误码。

