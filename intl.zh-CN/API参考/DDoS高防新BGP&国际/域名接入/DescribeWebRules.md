# DescribeWebRules

调用DescribeWebRules查询已经创建的网站业务转发规则。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=ddoscoo&api=DescribeWebRules&type=RPC&version=2020-01-01)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeWebRules|要执行的操作。取值：**DescribeWebRules**。 |
|PageSize|Integer|是|10|页面显示的记录数量。最大值：**10**。 |
|RegionId|String|否|cn-hangzhou|DDoS高防服务地域ID。取值：

 -   **cn-hangzhou**：表示DDoS高防（新BGP）服务。
-   **ap-southeast-1**：表示DDoS高防（国际）服务。 |
|ResourceGroupId|String|否|rg-acfm2pz25js\*\*\*\*|DDoS高防实例在资源管理产品中所属的资源组ID。默认为空，即属于默认资源组。

 关于资源组的更多信息，请参见[创建资源组](~~94485~~)。 |
|Domain|String|否|www.aliyun.com|网站业务的域名。

 **说明：** 域名必须已经配置网站业务转发规则。您可以调用[DescribeDomains](~~91724~~)查询所有已经配置过网站业务转发规则的域名。 |
|QueryDomainPattern|String|否|fuzzy|查询匹配模式。取值：

 -   **fuzzy**（默认）：表示模糊查询。
-   **exact**：表示精确查询。 |
|PageNumber|Integer|否|1|分页查询请求时返回的页码。例如，查询第一页的返回结果，则填写**1**。 |
|InstanceIds.N|RepeatList|否|ddoscoo-cn-mp91j1ao\*\*\*\*|要查询的DDoS高防实例的ID列表。最多支持查询100个实例。

 **说明：** 您可以调用[DescribeInstanceIds](~~157459~~)查询所有DDoS高防实例的ID信息。 |

调用API时，除了本文中该API的请求参数，还需加入阿里云API公共请求参数。公共请求参数的详细介绍，请参见[公共参数](~~157269~~)。

调用API的请求格式，请参见本文**示例**中的请求示例。

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|0F5B72DD-96F4-423A-B12B-A5151DD746B8|本次请求的ID。 |
|TotalCount|Long|1|网站业务转发规则的总数。 |
|WebRules|Array of WebRule| |网站业务转发规则信息。 |
|BlackList|List|\[1.\*\*\*.\*\*\*.1\]|IP黑名单（针对域名）列表。

 **说明：** 仅在您已经为该域名配置了IP黑名单（针对域名）时返回该结果。您可以调用[ConfigWebIpSet](~~157469~~)为网站域名配置IP黑白名单。 |
|CcEnabled|Boolean|true|是否开启了频率控制防护（CC防护）。取值：

 -   **true**：已开启
-   **false**：未开启 |
|CcRuleEnabled|Boolean|false|是否开启了自定义频率控制防护（CC防护）。取值：

 -   **true**：已开启
-   **false**：未开启 |
|CcTemplate|String|default|频率控制防护（CC防护）的模式。取值：

 -   **default**：正常
-   **gf\_under\_attack**：攻击紧急
-   **gf\_sos\_verify**：严格
-   **gf\_sos\_enhance**：超级严格 |
|CertName|String|testcert|证书名称。 |
|Cname|String|o8fzz0ocxere\*\*\*\*.aliyunddos\*\*\*\*.com|网站域名对应的DDoS高防CNAME地址。 |
|Domain|String|www.aliyun.com|网站域名。 |
|Http2Enable|Boolean|true|是否开启了HTTP2.0。取值：

 -   **true**：已开启
-   **false**：未开启 |
|Http2HttpsEnable|Boolean|true|是否开启了HTTPS的强制跳转功能。取值：

 -   **true**：已开启
-   **false**：未开启 |
|Https2HttpEnable|Boolean|true|是否开启了HTTP回源功能。取值：

 -   **true**：已开启
-   **false**：未开启 |
|PolicyMode|String|ip\_hash|回源负载算法的类型。取值：

 -   **ip\_hash**：表示IP Hash算法。根据请求来源IP进行HASH映射，将同一个IP的所有请求定向到一个源站服务器。
-   **rr**：表示轮转算法。将所有请求轮流分配给不同源站服务器。
-   **least\_time**：表示Least Time算法。该算法通过智能DNS解析能力，保证业务流量从接入防护节点到转发回源站服务器整个链路的时延最短。 |
|ProxyEnabled|Boolean|true|网站业务转发规则是否已开启。取值：

 -   **true**：已开启
-   **false**：未开启 |
|ProxyTypes|Array of ProxyConfig| |协议类型和端口号信息。 |
|ProxyPorts|List|\[80\]|端口号。 |
|ProxyType|String|http|协议类型。取值：**http**、**https**、**websocket**、**websockets**。 |
|RealServers|Array of RealServer| |源站服务器地址信息。 |
|RealServer|String|1.\*\*\*.\*\*\*.1|源站服务器地址。 |
|RsType|Integer|0|源站服务器地址的类型。取值：

 -   **0**：表示源站服务器的IP地址。
-   **1**：表示源站服务器的域名地址。通常适用于源站和高防之间还部署有其他代理服务（例如WAF）的场景，具体指代理服务的跳转地址（例如WAF CNAME地址）。 |
|SslCiphers|String|default|加密套件类型。取值：

 -   **default**（默认）：仅包含强加密套件。
-   **all**：全部加密套件，包含强加密套件和弱加密套件。
-   **strong**：强加密套件。 |
|SslProtocols|String|tls1.0|TLS版本。取值：

 -   **tls1.0**：表示支持TLS 1.0及以上版本。
-   **tls1.1**：表示支持TLS 1.1及以上版本。
-   **tls1.2**：表示支持TLS 1.2及以上版本。 |
|WhiteList|List|\[1.\*\*\*.\*\*\*.1\]|IP白名单（针对域名）列表。

 **说明：** 仅在您已经为该域名配置了IP白名单（针对域名）时返回该结果。您可以调用[ConfigWebIpSet](~~157469~~)为网站域名配置IP黑白名单。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=DescribeWebRules
&PageSize=10
&<公共请求参数>
```

正常返回示例

`XML` 格式

```
<DescribeWebRulesResponse>
	  <TotalCount>1</TotalCount>
	  <WebRules>
		    <CcEnabled>true</CcEnabled>
		    <SslProtocols>tls1.0</SslProtocols>
		    <ProxyTypes>
			      <ProxyPorts>80</ProxyPorts>
			      <ProxyType>http</ProxyType>
		    </ProxyTypes>
		    <ProxyTypes>
			      <ProxyPorts>443</ProxyPorts>
			      <ProxyType>https</ProxyType>
		    </ProxyTypes>
		    <CcRuleEnabled>false</CcRuleEnabled>
		    <SslCiphers>default</SslCiphers>
		    <Cname>o8fzz0ocxere****.aliyunddos****.com</Cname>
		    <ProxyEnabled>true</ProxyEnabled>
		    <Https2HttpEnable>true</Https2HttpEnable>
		    <RealServers>
			      <RealServer>1.***.***.1</RealServer>
			      <RsType>0</RsType>
		    </RealServers>
		    <Http2HttpsEnable>true</Http2HttpsEnable>
		    <CertName>testcert</CertName>
		    <Domain>www.aliyun.com</Domain>
		    <Http2Enable>true</Http2Enable>
		    <PolicyMode>ip_hash</PolicyMode>
		    <CcTemplate>default</CcTemplate>
	  </WebRules>
	  <RequestId>0F5B72DD-96F4-423A-B12B-A5151DD746B8</RequestId>
</DescribeWebRulesResponse>
```

`JSON` 格式

```
{
    "TotalCount": 1,
    "WebRules": [
        {
            "CcEnabled": true,
            "SslProtocols": "tls1.0",
            "ProxyTypes": [
                {
                    "ProxyPorts": [
                        80
                    ],
                    "ProxyType": "http"
                },
                {
                    "ProxyPorts": [
                        443
                    ],
                    "ProxyType": "https"
                }
            ],
            "CcRuleEnabled": false,
            "SslCiphers": "default",
            "Cname": "o8fzz0ocxere****.aliyunddos****.com",
            "ProxyEnabled": true,
            "Https2HttpEnable": true,
            "RealServers": [
                {
                    "RealServer": "1.***.***.1",
                    "RsType": 0
                }
            ],
            "Http2HttpsEnable": true,
            "CertName": "testcert",
            "Domain": "www.aliyun.com",
            "Http2Enable": true,
            "PolicyMode": "ip_hash",
            "CcTemplate": "default"
        }
    ],
    "RequestId": "0F5B72DD-96F4-423A-B12B-A5151DD746B8"
}
```

## 错误码

访问[错误中心](https://error-center.alibabacloud.com/status/product/ddoscoo)查看更多错误码。

