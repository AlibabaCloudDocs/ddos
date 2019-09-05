# ConfigLayer7CCRule {#doc_api_ddoscoo_ConfigLayer7CCRule .reference}

调用ConfigLayer7CCRule编辑7层CC规则。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=ddoscoo&api=ConfigLayer7CCRule&type=RPC&version=2017-12-28)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Act|String|是|close|规则触发后的操作，取值：

 -   **close**：封禁
-   **captcha**：人机识别

 |
|Action|String|是|ConfigLayer7CCRule|系统规定参数。取值：**ConfigLayer7CCRule**。

 |
|Count|Integer|是|2|访问次数，与**Interval**结和使用。当同一个IP在Interval指定的间隔时间内连续访问Count中指定的访问次数，则触发规则。取值范围为2~2,000。

 |
|Domain|String|是|www.aliyun.com|要操作的域名。

 |
|Interval|Integer|是|5|间隔时间，与**Count**结和使用。当同一个IP在Interval指定的间隔时间内连续访问Count中指定的访问次数，则触发规则。取值范围为5~10,800。

 |
|Mode|String|是|match|URI匹配模式，取值：

 -   **match**：完全匹配。访问请求的URI与指定的Uri完全相同，才计入访问次数。
-   **prefix**：前缀匹配。访问请求的URI包含指定的Uri，则计入访问次数。

 |
|Name|String|是|testCcRule1|CC自定义规则名。

 |
|Ttl|Integer|是|60|若规则触发后动作指定为封禁，设置封禁时间，单位为秒，取值范围为60~86,400。

 |
|Uri|String|是|/a/b/c|被防护的URI。

 |
|ResourceGroupId|String|否|test|资源组ID。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|CF33B4C3-196E-4015-AADD-5CAD00057B80|本次请求的ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=ConfigLayer7CCRule
&Act=close
&Count=2
&Domain=www.aliyun.com
&Interval=5
&Mode=match
&Name=testCcRule1
&Ttl=60
&Uri=/a/b/c
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<ConfigLayer7CCRuleResponse>
     <RequestId>0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc</RequestId>
</ConfigLayer7CCRuleResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/ddoscoo)查看更多错误码。

