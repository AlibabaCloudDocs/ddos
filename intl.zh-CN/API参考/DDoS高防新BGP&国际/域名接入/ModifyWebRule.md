# ModifyWebRule

调用ModifyWebRule修改已经创建的网站业务转发规则。

您可以修改网站业务转发规则中的源站服务器和协议信息、关联的DDoS高防实例、HTTPS高级设置。

关于如何通过控制台操作创建网站业务转发规则，请参见[添加网站](~~143347~~)（该文档介绍了更详细的将网站业务接入DDoS高防进行防护的流程和参数描述）。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=ddoscoo&api=ModifyWebRule&type=RPC&version=2020-01-01)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|ModifyWebRule|要执行的操作。取值：**ModifyWebRule**。 |
|Domain|String|是|www.aliyun.com|网站业务的域名。

 **说明：** 域名必须已经配置过网站业务转发规则。您可以调用[DescribeDomains](~~91724~~)查询所有已经配置过网站业务转发规则的域名。 |
|ProxyTypes|String|是|\[\{"ProxyType":"http","ProxyPorts":\[80\]\},\{"ProxyType":"https","ProxyPorts":\[443\]\}\]|网站业务转发规则的协议信息。使用JSON数组转化的字符串格式表示。JSON数组中的每个元素是一个JSON结构体，包含以下字段：

 -   **ProxyType**：String类型 \| 必选 \| 网站协议类型。取值：**http** \| **https** \| **websocket** \| **websockets**。
-   **ProxyPort**：Integer类型 \| 必选 \| 端口号。 |
|RealServers.N|RepeatList|是|1.xxx.xxx.1|服务器地址列表。 |
|RsType|Integer|是|0|源站服务器的地址类型。取值：

 -   **0**：表示源站服务器的IP地址。
-   **1**：表示源站服务器的域名地址。通常适用于源站和高防之间还部署有其他代理服务（例如WAF）的场景，具体指代理服务的跳转地址（例如WAF CNAME地址）。 |
|RegionId|String|否|cn-hangzhou|DDoS高防服务的地域ID。取值：

 -   **cn-hangzhou**：表示DDoS高防（新BGP）服务。
-   **ap-southeast-1**：表示DDoS高防（国际）服务。 |
|ResourceGroupId|String|否|rg-acfm2pz25js\*\*\*\*|DDoS高防实例在资源管理产品中所属的资源组ID。默认为空，即属于默认资源组。

 关于资源组的更多信息，请参见[创建资源组](~~94485~~)。 |
|InstanceIds.N|RepeatList|否|ddoscoo-cn-mp91j1ao\*\*\*\*|要关联的DDoS高防实例的ID列表。最多支持关联100个实例。

 **说明：** 您可以调用[DescribeInstanceIds](~~157459~~)查询所有DDoS高防实例的ID信息。 |
|HttpsExt|String|否|\{"Http2":1,"Http2https":1，"Https2http":1\}|HTTPS高级设置，仅在网站协议类型支持HTTPS（**ProxyType**包含**https**）时生效。使用JSON结构体转化的字符串格式表示，JSON结构体包含以下字段：

 -   **Http2https**：Integer类型 \| 可选 \| 是否开启HTTPS的强制跳转功能，取值：**0**（表示关闭） \| **1**（表示开启），默认关闭。

适用于您的网站同时支持HTTP和HTTPS协议。开启该设置后，所有HTTP请求将强制转换为HTTPS请求，且默认跳转到443端口。

-   **Https2http**：Integer类型 \| 可选 \| 是否开启HTTP回源功能，取值：**0**（表示关闭） \| **1**（表示开启），默认关闭。

适用于您的网站不支持HTTPS回源。开启该设置后，所有HTTPS协议请求将通过HTTP回源（Websockets协议会通过Websocket回源），且默认回源端口为80。

-   **Http2**：Integer类型 \| 可选 \| 是否启用HTTP2.0协议类型，取值：**0**（表示关闭） \| **1**（表示开启），默认关闭。

开启该设置后，协议版本为HTTP2.0。 |

调用API时，除了本文中该API的请求参数，还需加入阿里云API公共请求参数。公共请求参数的详细介绍，请参见[公共参数](~~157269~~)。

调用API的请求格式，请参见本文**示例**中的请求示例。

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc|本次请求的ID。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=ModifyWebRule
&Domain=www.aliyun.com
&ProxyTypes=[{\"ProxyType\":\"http\",\"ProxyPorts\":[80]},{\"ProxyType\":\"https\",\"ProxyPorts\":[443]}]
&RealServers.1=1.xxx.xxx.1
&RsType=0
&<公共请求参数>
```

正常返回示例

`XML` 格式

```
<ModifyWebRuleResponse>
	  <RequestId>0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc</RequestId>
</ModifyWebRuleResponse>
```

`JSON` 格式

```
{
  "RequestId": "0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc"
}
```

## 错误码

访问[错误中心](https://error-center.alibabacloud.com/status/product/ddoscoo)查看更多错误码。

