# ConfigLayer7Rule {#doc_api_ddoscoo_ConfigLayer7Rule .reference}

调用ConfigLayer7Rule编辑7层转发规则。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=ddoscoo&api=ConfigLayer7Rule&type=RPC&version=2017-12-28)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|ConfigLayer7Rule|系统规定参数。取值：**ConfigLayer7Rule**。

 |
|Domain|String|是|www.aliyun.com|要操作的域名。

 |
|RealServers.N|RepeatList|是|1.1.1.1|源站IP。若有多个源站IP，依次传入RealServers.1, RealServers.2, RealServers.3, ...

 |
|RsType|Integer|是|0|源站类型，取值：

 -   **0**：IP
-   **1**：域名

 |
|InstanceIds.N|RepeatList|否|ddoscoo-cn-XXXXXX|要绑定的实例Id。若有多个实例，依次传入InstanceIds.1, InstanceIds.2, InstanceIds.3, ...

 **说明：** 若不传入该参数，则只添加域名，不绑定到具体IP。

 |
|ProxyTypeList|String|否|\[\{"ProxyPorts":\[80,8080\],"ProxyType":"http"\},\{"ProxyPorts":\[443\],"ProxyType":"https"\}\]rts\\":\[443\],\\"ProxyType\\":\\"https\\"\}\]|协议数组。具体结构描述如下：

 -   **ProxyType**，String类型，必选，协议类型，取值：**http**、**https**、**websocket**、**websockets**。
-   **ProxyPorts**，Integer类型，必选，协议端口。

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

http(s)://[Endpoint]/?Action=ConfigLayer7Rule
&Domain=www.aliyun.com
&RealServers.1=1.1.1.1
&RsType=0
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<ConfigLayer7RuleResponse>
     <RequestId>0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc</RequestId>
</ConfigLayer7RuleResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/ddoscoo)查看更多错误码。

