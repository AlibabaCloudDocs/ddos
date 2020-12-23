# DescribeWebRules

Queries the forwarding rules of a website.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=ddoscoo&api=DescribeWebRules&type=RPC&version=2020-01-01)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeWebRules|The operation that you want to perform. Set the value to **DescribeWebRules**. |
|PageSize|Integer|Yes|10|The number of entries to return on each page. Minimum value: **10**. |
|RegionId|String|No|cn-hangzhou|The region ID of the instance. Valid values:

-   **cn-hangzhou**: mainland China, which indicates an Anti-DDoS Pro instance
-   **ap-southeast-1**: outside mainland China, which indicates an Anti-DDoS Premium instance |
|ResourceGroupId|String|No|rg-acfm2pz25js\*\*\*\*|The ID of the resource group to which the instance belongs in Resource Management. This parameter is empty by default, which indicates that the instance belongs to the default resource group.

For more information about resource groups, see [Create a resource group](~~94485~~). |
|Domain|String|No|www.aliyun.com|The domain name of the website.

**Note:** A forwarding rule must be configured for the domain name. You can call the [DescribeDomains](~~91724~~) operation to query domain names for which the forwarding rules are created. |
|QueryDomainPattern|String|No|fuzzy|The match mode. Valid values:

-   **fuzzy**: fuzzy match. This is the default value.
-   **exact**: exact match. |
|PageNumber|Integer|No|1|The number of the page to return. Pages start from page **1**. |
|InstanceIds.N|RepeatList|No|ddoscoo-cn-mp91j1ao\*\*\*\*|The ID of instance N that you want to query. A maximum of 100 instances can be queried at a time.

**Note:** You can call the [DescribeInstanceIds](~~157459~~) operation to query the IDs of all instances. |

All Alibaba Cloud API operations must include common request parameters. For more information about common request parameters, see [Common parameters](~~157269~~).

For more information about sample requests, see the **"Examples"** section of this topic.

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|0F5B72DD-96F4-423A-B12B-A5151DD746B8|The ID of the request. |
|TotalCount|Long|1|The total number of returned forwarding rules. |
|WebRules|Array of WebRule| |The details about the forwarding rule. |
|BlackList|List|\[1. \*\*\*. \*\*\*.1\]|The IP addresses in the blacklist for the domain name.

**Note:** This parameter is returned only when you configure an IP address blacklist for the domain name. You can call the [ConfigWebIpSet](~~157469~~) operation to query the IP address whitelist and blacklist configured for the domain name. |
|CcEnabled|Boolean|true|Indicates whether the Frequency Control policy is enabled. Valid values:

-   **true**
-   **false** |
|CcRuleEnabled|Boolean|false|Indicates whether the Custom Rule switch of the Frequency Control policy is turned on. Valid values:

-   **true**
-   **false** |
|CcTemplate|String|default|The mode of the Frequency Control policy. Valid values:

-   **default**: the Normal mode
-   **gf\_under\_attack**: the Emergency mode
-   **gf\_sos\_verify**: the Strict mode
-   **gf\_sos\_enhance**: the Super Strict mode |
|CertName|String|testcert|The name of the certificate. |
|Cname|String|o8fzz0ocxere\*\*\*\*.aliyunddos\*\*\*\*.com|The CNAME of the Anti-DDoS Pro or Anti-DDoS Premium instance to which the domain name is added. |
|Domain|String|www.aliyun.com|The domain name of the website. |
|Http2Enable|Boolean|true|Indicates whether Enable HTTP/2 is turned on. Valid values:

-   **true**
-   **false** |
|Http2HttpsEnable|Boolean|true|Indicates whether Enforce HTTPS Routing is turned on. Valid values:

-   **true**
-   **false** |
|Https2HttpEnable|Boolean|true|Indicates whether Enable HTTP is turned on. Valid values:

-   **true**
-   **false** |
|PolicyMode|String|ip\_hash|The load balancing algorithm for back-to-origin traffic. Valid values:

-   **ip\_hash**: the IP hash algorithm. This algorithm is used to redirect the requests from the same IP address to the same origin server.
-   **rr**: the round-robin algorithm. This algorithm is used to redirect requests to origin servers in turn.
-   **least\_time**: the least response time algorithm. This algorithm is used to minimize the latency when requests are forwarded from Anti-DDoS Pro or Anti-DDoS Premium instances to origin servers based on the intelligent DNS resolution feature. |
|ProxyEnabled|Boolean|true|Indicates whether the traffic forwarding rule is enabled. Valid values:

-   **true**
-   **false** |
|ProxyTypes|Array of ProxyConfig| |The details of the protocol type and port number. |
|ProxyPorts|List|\[80\]|The port number. |
|ProxyType|String|http|The type of the protocol. Valid values: **http**, **https**, **websocket**, and **websockets**. |
|RealServers|Array of RealServer| |The details about the address of the origin server. |
|RealServer|String|1.\*\*\*. \*\*\*.1|The address of the origin server. |
|RsType|Integer|0|The address type of the origin server. Valid values:

-   **0**: IP address.
-   **1**: domain name. Use the domain name of the origin server if you deploy proxies, such as Web Application Firewall \(WAF\), between the origin server and the Anti-DDoS Pro or Anti-DDoS Premium instance. If you use the domain name, you must enter the address of the proxy, such as the CNAME of WAF. |
|SslCiphers|String|default|The type of the cipher suite. Valid values:

-   **default**: default cipher suites, which contain only strong cipher suites. This is the default value.
-   **all**: all cipher suites, which contain strong and weak cipher suites.
-   **strong**: strong cipher suites. |
|SslProtocols|String|tls1.0|The version of the TLS protocol. Valid values:

-   **tls1.0**: TLS 1.0 or later
-   **tls1.1**: TLS 1.1 or later
-   **tls1.2**: TLS 1.2 or later |
|WhiteList|List|\[1. \*\*\*. \*\*\*.1\]|The IP addresses in the whitelist for the domain name.

**Note:** This parameter is returned only when you configure an IP address whitelist for the domain name. You can call the [ConfigWebIpSet](~~157469~~) operation to query the IP address whitelist and blacklist configured for the domain name. |

## Examples

Sample requests

```
http(s)://[Endpoint]/?Action=DescribeWebRules
&PageSize=10
&<Common request parameters>
```

Sample success responses

`XML` format

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
                  <RealServer>1. ***. ***.1</RealServer>
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

`JSON` format

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
                    "RealServer": "1. ***. ***.1",
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

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/ddoscoo).

