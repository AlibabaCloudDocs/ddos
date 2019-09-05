# CreateLayer7Rule {#doc_api_ddoscoo_CreateLayer7Rule .reference}

调用CreateLayer7Rule创建7层转发规则。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=ddoscoo&api=CreateLayer7Rule&type=RPC&version=2017-12-28)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|CreateLayer7Rule|系统规定参数。取值：**CreateLayer7Rule**。

 |
|Domain|String|是|www.aliyun.com|要添加的域名。

 |
|RsType|Integer|是|0|源站类型，取值：

 -   **0**：IP
-   **1**：域名

 |
|Rules|String|是|\[\{"ProxyRules":\[\{"ProxyPort":443,"RealServers":\["1.1.1.1:443"\]\}\],"ProxyType":"https"\},\{"ProxyRules":\[\{"ProxyPort":80,"RealServers":\["1.1.1.1:80"\]\}\],"ProxyType":"http"\}\]|传入7层规则Layer7Rule数组JSON串。具体结构描述如下：

 -   **ProxyRules**，数组类型，必选，规则对象数组，包含以下元素：
    -   **ProxyPort**，Integer类型，必选，协议端口，取值：**80**、**443**。
    -   **RealServers**，String类型，必选，用户源站。例如，1.1.1.1:443。
-   **ProxyType**，String类型，必选，协议类型，取值：**http**、**https**、**websocket**、**websockets**。

 |
|InstanceIds.N|RepeatList|否|ddoscoo-cn-XXXXX|要绑定的实例ID。若有多个实例，依次传入InstanceIds.1, InstanceIds.2, InstanceIds.3, ..

 **说明：** 若不传入该参数，则只添加域名，不绑定到具体IP。

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

http(s)://[Endpoint]/?Action=CreateLayer7Rule
&Domain=www.aliyun.com
&RsType=0
&Rules=[{"ProxyRules":[{"ProxyPort":443,"RealServers":["1.1.1.1:443"]}],"ProxyType":"https"},{"ProxyRules":[{"ProxyPort":80,"RealServers":["1.1.1.1:80"]}],"ProxyType":"http"}]
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<CreateLayer7RuleResponse>
     <RequestId>0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc</RequestId>
</CreateLayer7RuleResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/ddoscoo)查看更多错误码。

