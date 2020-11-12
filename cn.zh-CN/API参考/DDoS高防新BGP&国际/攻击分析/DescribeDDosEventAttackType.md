# DescribeDDosEventAttackType

调用DescribeDDosEventAttackType查询某次流量型攻击的攻击类型详情。

**说明：** 目前该接口仅适用于查询流量型攻击的数据，不适用于查询Web资源消耗型和连接型攻击的数据。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=ddoscoo&api=DescribeDDosEventAttackType&type=RPC&version=2020-01-01)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeDDosEventAttackType|要执行的操作。取值：**DescribeDDosEventAttackType**。 |
|EventType|String|是|defense|要查询的攻击事件的类型。取值：

 -   **defense**：表示流量型攻击清洗事件。
-   **blackhole**：表示流量型攻击黑洞事件。 |
|Ip|String|是|203.\*\*\*.\*\*\*.199|受攻击的高防IP。 |
|StartTime|Long|是|1598948471|要查询事件的开始时间戳，单位：秒。

 **说明：** 您可以调用[DescribeDDosAllEventList](~~188604~~)查询所有事件的开始时间信息。 |

调用API时，除了本文中该API的请求参数，还需加入阿里云API公共请求参数。公共请求参数的详细介绍，请参见[公共参数](~~157269~~)。

调用API的请求格式，请参见本文**示例**中的请求示例。

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|AttackTypes|Array of EventAttackType| |攻击类型信息。 |
|AttackType|String|Tcp-Syn|攻击类型。取值：

 -   **QOTD-Reflect-Flood**：QOTD反射攻击
-   **CharGEN-Reflect-Flood**：CharGEN反射攻击
-   **DNS-Reflect-Flood**：DNS反射攻击
-   **TFTP-Reflect-Flood**：TFTP反射攻击
-   **Portmap-Reflect-Flood**：Portmap反射攻击
-   **NTP-Reflect-Flood**：NTP反射攻击
-   **NetBIOS-Reflect-Flood**：NetBIOS反射攻击
-   **SNMPv2-Reflect-Flood**：SNMPv2反射攻击
-   **CLDAP-Reflect-Flood**：CLDAP反射攻击
-   **Ripv1-Reflect-Flood**：Ripv1反射攻击
-   **OpenVPN-Reflect-Flood**：OpenVPN反射攻击
-   **SSDP-Reflect-Flood**：SSDP反射攻击
-   **NetAssistant-Reflect-Flood**：NetAssistant反射攻击
-   **WSDiscovery-Reflect-Flood**：WSDiscovery反射攻击
-   **Kad-Reflect-Flood**：Kad反射攻击
-   **mDNS-Reflect-Flood**：mDNS反射攻击
-   **10001-Reflect-Flood**：10001反射攻击
-   **Memcached-Reflect-Flood**：Memcached反射攻击
-   **QNP-Reflect-Flood**：QNP反射攻击
-   **DVR-Reflect-Flood**：DVR反射攻击
-   **CoAP-Reflect-Flood**：CoAP反射攻击
-   **ADDP-Reflect-Flood**：ADDP反射攻击
-   **Tcp-Syn**：TCP SYN Flood攻击
-   **Tcp-Fin**：TCP FIN Flood攻击
-   **Tcp-Ack**：TCP ACK Flood攻击
-   **Tcp-Rst**：TCP RST Flood攻击
-   **Tcp-Pushack**：TCP PSH+ACK Flood攻击
-   **Tcp-Synack**：TCP SYN+ACK Flood攻击
-   **Udp-None**：UDP攻击
-   **Udp-Ssh**：UDP SSH协议攻击
-   **Udp-Dns**：UDP DNS协议攻击
-   **Udp-Http**：UDP HTTP协议攻击
-   **Udp-Https**：UDP HTTPS协议攻击
-   **Udp-Ntp**：UDP NTP协议攻击
-   **Udp-Ldap**：UDP LDAP协议攻击
-   **Udp-Ssdp**：UDP SSDP协议攻击
-   **Udp-Memcached**：Memcache UDP反射放大攻击
-   **Tcp-Other**：TCP其他类型攻击
-   **Icmp**：ICMP Flood攻击
-   **Igmp**：IGMP Flood攻击
-   **Ipv6**：IPv6攻击 |
|InPkts|Long|145902|该攻击类型的请求包数量。 |
|RequestId|String|6F644A6E-40E7-483F-9DBB-CC27E16BB555|本次请求的ID。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=DescribeDDosEventAttackType
&EventType=defense
&Ip=203.***.***.199
&StartTime=1598948471
&<公共请求参数>
```

正常返回示例

`XML` 格式

```
<DescribeDDosEventAttackTypeResponse>
	  <RequestId>6F644A6E-40E7-483F-9DBB-CC27E16BB555</RequestId>
	  <AttackTypes>
		    <AttackType>Tcp-Syn</AttackType>
		    <InPkts>145902</InPkts>
	  </AttackTypes>
	  <AttackTypes>
		    <AttackType>Tcp-Other</AttackType>
		    <InPkts>3</InPkts>
	  </AttackTypes>
  </DescribeDDosEventAttackTypeResponse>
```

`JSON` 格式

```
{
	"RequestId": "6F644A6E-40E7-483F-9DBB-CC27E16BB555",
	"AttackTypes": [
		{
			"AttackType": "Tcp-Syn",
			"InPkts": 145902
		},
		{
			"AttackType": "Tcp-Other",
			"InPkts": 3
		}
	]
}
```

## 错误码

访问[错误中心](https://error-center.aliyun.com/status/product/ddoscoo)查看更多错误码。

