# CreateSchedruleOnDemand

调用CreateSchedruleOnDemand为代播实例创建一条调度规则。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=ddosbgp&api=CreateSchedruleOnDemand&type=RPC&version=2018-07-20)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|CreateSchedruleOnDemand|要执行的操作。取值：**CreateSchedruleOnDemand**。 |
|InstanceId|String|是|ddosbgp-cn-z2q1qzxb\*\*\*\*|要操作的代播实例的ID。

 **说明：** 您可以调用[DescribeOnDemandInstance](~~152120~~)查询所有代播实例的ID。 |
|RuleAction|String|是|declare|调度动作。取值固定为**declare**，表示宣告路由。 |
|RuleConditionCnt|String|是|3|从互联网访问IDC的网络带宽或者报文数量连续超过阈值多少次时，将触发调度规则并开启代播防护。

 **说明：** 带宽阈值通过**RuleConditionMbps**参数设置，报文数阈值通过**RuleConditionKpps**参数设置。 |
|RuleConditionKpps|String|是|10|入方向报文数阈值，单位：Kpps。最小值：**10**。 |
|RuleConditionMbps|String|是|100|入方向带宽阈值，单位：Mbps。最小值：**100**。 |
|RuleName|String|是|ddosbgp-cn-z2q1qzxb\*\*\*\*|调度规则的名称。

 支持使用英文小写字母、数字、短划线（-）和下划线（\_），不超过32个字符。建议您使用代播实例的ID作为调度规则名称，例如，`ddosbgp-cn-z2q1qzxb****`。 |
|RuleSwitch|String|是|on|调度规则的开关状态。取值：

 -   **on**：表示开启。
-   **off**：表示关闭。 |
|RuleUndoBeginTime|String|是|03:00|自动停止调度的开始时间。使用24小时制表示，格式：`hh:mm`。

 当系统检测到攻击停止后，会在此处设置的时间开始停止代播防护。建议您将该时间设置为业务低峰期。

 **说明：** 该参数仅在使用自动停止调度（**RuleUndoMode**设置为**auto**）时生效。 |
|RuleUndoMode|String|是|auto|调度规则的停止方式。取值：

 -   **auto**：表示自动停止调度。
-   **manual**：表示手动停止调度。 |
|TimeZone|String|是|GMT-08:00|自动停止调度时间对应的时区。使用格林威治时间表示，格式：`GMT-hh:mm`。

 例如，`GMT-08:00`表示东八区。

 **说明：** 该参数仅在使用自动停止调度（**RuleUndoMode**设置为**auto**）时生效。 |
|RuleUndoEndTime|String|否|03:05|自动停止调度的结束时间。使用24小时制表示，格式：`hh:mm`。 |
|RegionId|String|否|cn-zhangjiakou|代播实例的地域ID。

 **说明：** 您可以调用[DescribeRegions](~~118703~~)查询DDoS原生防护支持的所有地域信息。 |

调用API时，除了本文中该API的请求参数，还需加入阿里云API公共请求参数。公共请求参数的详细介绍，请参见[公共参数](~~118841~~)。

调用API的请求格式，请参见本文**示例**中的请求示例。

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|BD06F539-2FBE-450D-9391-7EFF787128F5|本次请求的ID。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=CreateSchedruleOnDemand
&InstanceId=ddosbgp-cn-z2q1qzxb****
&RuleAction=declare
&RuleConditionCnt=3
&RuleConditionKpps=10
&RuleConditionMbps=100
&RuleName=ddosbgp-cn-z2q1qzxb****
&RuleSwitch=on
&RuleUndoBeginTime=03:00
&RuleUndoMode=auto
&TimeZone=GMT-08:00
&<公共请求参数>
```

正常返回示例

`XML` 格式

```
<CreateSchedruleOnDemandResponse>
	  <RequestId>BD06F539-2FBE-450D-9391-7EFF787128F5</RequestId>
</CreateSchedruleOnDemandResponse>
```

`JSON` 格式

```
{
    "RequestId": "BD06F539-2FBE-450D-9391-7EFF787128F5"
}
```

## 错误码

访问[错误中心](https://error-center.aliyun.com/status/product/ddosbgp)查看更多错误码。

