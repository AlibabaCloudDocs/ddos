# ConfigLayer4RuleAttribute {#doc_api_ddoscoo_ConfigLayer4RuleAttribute .reference}

调用ConfigLayer4RuleAttribute配置4层转发规则属性，包括会话保持和DDoS防护策略。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=ddoscoo&api=ConfigLayer4RuleAttribute&type=RPC&version=2017-12-28)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|ConfigLayer4RuleAttribute|系统规定参数。取值：**ConfigLayer4RuleAttribute**。

 |
|Config|String|是|\{"Slimit":\{"CpsEnable":1,"MaxconnEnable":1,"Cps":1,"Maxconn":1\},"Sla":\{"CpsEnable":1,"MaxconnEnable":1,"Cps":100,"Maxconn":1000\},"PayloadLen":\{"Min":0,"Max":6000\}\}|配置信息，传入**TcpConfig**或**UdpConfig**对象JSON串。

 **TcpConfig**的具体结构描述见如下：

 -   **PersistenceTimeout**，Integer类型，必选，会话保持的超时时间，单位为秒。默认为**0**，表示关闭。
-   **Synproxy**，String类型，必选，DDoS防护策略的虚假源，取值：**off**、**on**。
-   **NodataConn**，String类型，必选，DDoS防护策略的空连接，取值：**off**、**on**。
-   **Sla**，Struct类型，必选，目的限制配置。具体结构描述见**Sla**。
-   **Slimit**，Struct类型，必选，源限制配置。具体结构描述见**Slimit**。
-   **PayloadLen**，Struct类型，必选，包过滤配置。具体结构描述见**PayloadLen**。

 **UdpConfig**的具体结构描述如下：

 -   **PersistenceTimeout**，Integer类型，必选，会话保持的超时时间，单位为秒。默认为**0**，表示关闭。
-   **Synproxy**，String类型，必选，DDoS防护策略的虚假源，取值：**off**、**on**。
-   **NodataConn**，String类型，必选，DDoS防护策略的空连接，取值：**off**、**on**。
-   **Sla**，Struct类型，必选，目的限制配置。具体结构描述见**Sla**。
-   **Slimit**，Struct类型，必选，源限制配置。具体结构描述见**Slimit**。
-   **PayloadLen**，Struct类型，必选，包过滤配置。具体结构描述见**PayloadLen**。

 **Sla**的具体结构描述如下：

 -   **Cps**，Integer类型，必选，DDoS防护策略/目的新建连接限速，取值范围：100~100,000。
-   **Maxconn**，Integer类型，必选，DDoS防护策略/目的并发连接限速，取值范围：1,000~1,000,000。
-   **CpsEnable**，Integer类型，必选，是否开启Cps，取值：**0**（禁用cps）、**1**（默认，启用cps）。
-   **MaxconnEnable**，Integer类型，必选，是否开启Maxconnection，取值：**0**（禁用maxconn）、**1**（默认，启用maxconn）。

 **Slimit**的具体结构描述如下：

 -   **Cps**，Integer类型，必选，DDoS防护策略/源新建连接限速，取值范围：100~100,000。
-   **Maxconn**，Integer类型，必选，DDoS防护策略/源并发连接限速，取值范围：1,000~1,000,000。
-   **CpsEnable**，Integer类型，必选，是否开启Cps，取值：**0**（禁用cps）、**1**（默认，启用cps）。
-   **MaxconnEnable**，Integer类型，必选，是否开启Maxconnection，取值：**0**（禁用maxconn）、**1**（默认，启用maxconn）。
-   **CpsMode**，Integer类型，必选，源新建连接限速开关，取值：**1**（关闭）、**2**（自动）。

 **PayloadLen**的具体结构描述如下：

 -   **Min**，Integer类型，必选，DDoS防护策略/包长度过滤，包长度的最小值，取值范围为0~6,000。
-   **Max**，Integer类型，必选，DDoS防护策略/包长度过滤，包长度的最大值，取值范围为0~6,000。

 |
|ForwardProtocol|String|是|TCP|转发协议，取值：**TCP**、**UDP**。

 |
|FrontendPort|Integer|是|233|前端端口。

 |
|InstanceId|String|是|ddoscoo-cn-XXXXX|要操作的实例ID。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|CF33B4C3-196E-4015-AADD-5CAD00057B80|本次请求的ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=ConfigLayer4RuleAttribute
&Config={"Slimit":{"CpsEnable":1,"MaxconnEnable":1,"Cps":1,"Maxconn":1},"Sla":{"CpsEnable":1,"MaxconnEnable":1,"Cps":100,"Maxconn":1000},"PayloadLen":{"Min":0,"Max":6000}}
&ForwardProtocol=TCP
&FrontendPort=233
&InstanceId=ddoscoo-cn-XXXXX
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<ConfigLayer4RuleAttributeResponse>
     <RequestId>0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc</RequestId>
</ConfigLayer4RuleAttributeResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/ddoscoo)查看更多错误码。

