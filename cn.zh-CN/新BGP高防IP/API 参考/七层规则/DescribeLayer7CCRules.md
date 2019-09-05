# DescribeLayer7CCRules {#doc_api_ddoscoo_DescribeLayer7CCRules .reference}

调用DescribeLayer7CCRules查询7层CC规则。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=ddoscoo&api=DescribeLayer7CCRules&type=RPC&version=2017-12-28)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeLayer7CCRules|系统规定参数。取值：**DescribeLayer7CCRules**。

 |
|Domain|String|是|www.aliyun.com|要查询的域名。

 |
|Offset|Integer|是|0|开始索引位置，即从第几个结果开始返回。

 **说明：** 若不传入该参数，则从第0个结果开始返回。

 |
|PageSize|String|是|10|分页大小，即每页显示过少个结果。最大值**10**。

 |
|ResourceGroupId|String|否|test|资源组ID。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Layer7CCRules| | |CC规则数组。

 |
|Act|String|close|规则触发后的操作，取值：

 -   **close**：封禁
-   **captcha**：人机识别

 |
|Count|Integer|100|访问次数，与**Interval**结和使用。当同一个IP在Interval指定的间隔时间内连续访问Count中指定的访问次数，则触发规则。

 |
|Interval|Integer|60|间隔时间，与**Count**结和使用。当同一个IP在Interval指定的间隔时间内连续访问Count中指定的访问次数，则触发规则。

 |
|Mode|String|match|URI匹配模式，取值：

 -   **match**：完全匹配。访问请求的URI与指定的Uri完全相同，才计入访问次数。
-   **prefix**：前缀匹配。访问请求的URI包含指定的Uri，则计入访问次数。

 |
|Name|String|testCcRule1|CC自定义规则名。

 |
|Ttl|Integer|1000|若规则触发后动作指定为封禁，设置封禁时间。

 |
|Uri|String|/a/b/c|被防护的URI。

 |
|RequestId|String|CF33B4C3-196E-4015-AADD-5CAD00057B80|本次请求的ID。

 |
|Total|Long|10|规则总数。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeLayer7CCRules
&Domain=www.aliyun.com
&Offset=0
&PageSize=10
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeLayer7CCRulesResponse>
     <Layer7CCRules>
          <element>
               <Act>close</Act>
               <Count>11</Count>
               <Interval>5</Interval>
               <Mode>match</Mode>
               <Name>XXXX</Name>
               <Ttl>1</Ttl>
               <Uri>/a/b/c.htm</Uri>
          </element>
          <element>
               <Act>close</Act>
               <Count>11</Count>
               <Interval>5</Interval>
               <Mode>match</Mode>
               <Name>XXXX</Name>
               <Ttl>1</Ttl>
               <Uri>/a/b/c.htm</Uri>
          </element>
     </Layer7CCRules>
     <RequestId>0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc</RequestId>
     <Total>10</Total>
</DescribeLayer7CCRulesResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc",
	"Layer7CCRules":[
		{
			"Name":"XXXX",
			"Interval":5,
			"Count":11,
			"Act":"close",
			"Ttl":1,
			"Uri":"/a/b/c.htm",
			"Mode":"match"
		},
		{
			"Name":"XXXX",
			"Interval":5,
			"Count":11,
			"Act":"close",
			"Ttl":1,
			"Uri":"/a/b/c.htm",
			"Mode":"match"
		}
	],
	"Total":10
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/ddoscoo)查看更多错误码。

