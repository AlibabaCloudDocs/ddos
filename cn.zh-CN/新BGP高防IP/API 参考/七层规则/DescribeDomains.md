# DescribeDomains {#doc_api_ddoscoo_DescribeDomains .reference}

调用DescribeDomains查询7层转发规则。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=ddoscoo&api=DescribeDomains&type=RPC&version=2017-12-28)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeDomains|系统规定参数。取值：**DescribeDomains**。

 |
|Offset|Integer|是|0|开始索引位置，即从第几条结果开始显示。默认从**0**开始。

 |
|PageSize|String|是|10|分页大小，即每页显示多少条记录。最大值**10**。

 |
|Domain|String|否|www.aliyun.com|要查询的域名。

 |
|QueryDomainPattern|String|否|fuzzy|查询匹配模式。取值：

 -   **fuzzy**：模糊查询（默认）
-   **exact**：精确查询

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|CF33B4C3-196E-4015-AADD-5CAD00057B80|本次请求的ID。

 |
|Total|Long|10|域名总数。

 |
|Domains| | |域名列表。

 |
|BlackList| |\["1.1.1.1/1","1.1.1.2/2"\]|黑名单IP列表。

 |
|CcEnabled|Boolean|true|是否启用CC防护。

 |
|CcRuleEnabled|Boolean|true|是否启用CC规则。

 |
|CcTemplate|String|normal|CC防护模板。

 |
|CertName|String|testCertName|证书名称。

 |
|Domain|String|www.aliyun.com|域名。

 |
|ProxyTypeList| | |协议类型列表。

 |
|ProxyPorts| |111|协议端口。

 |
|ProxyType|String|http|协议类型。取值：

 -   **http**
-   **https**
-   **websocket**
-   **websockets**

 |
|RealServers| | |源站列表。

 |
|RealServer|String|1.1.1.1|源站地址。

 |
|RsType|Integer|0|源站类型。取值：

 -   **0**：IP
-   **1**：域名

 |
|WhiteList| |\["1.1.1.1/1","1.1.1.2/2"\]|白名单IP列表。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeDomains
&Offset=0
&PageSize=10
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeDomainsResponse>
     <Domains>
          <element>
               <BlackList>
                    <element>1.1.1.1/1</element>
                    <element>1.1.1.2/2</element>
               </BlackList>
               <CcEnabled>false</CcEnabled>
               <CcRuleEnabled>true</CcRuleEnabled>
               <CcTemplate>default</CcTemplate>
               <CertName>www_alibaba_com.pem</CertName>
               <Domain>www.alibaba.com</Domain>
               <ProxyTypeList>
                    <element>
                         <ProxyPorts>
                              <element>80</element>
                              <element>8080</element>
                         </ProxyPorts>
                         <ProxyType>http</ProxyType>
                    </element>
               </ProxyTypeList>
               <RealServers>
                    <element>
                         <RealServer>1.1.1.1</RealServer>
                         <RsType>0</RsType>
                    </element>
                    <element>
                         <RealServer>1.1.1.2</RealServer>
                         <RsType>1</RsType>
                    </element>
               </RealServers>
               <WhiteList>
                    <element>1.1.1.1/1</element>
                    <element>1.1.1.2/2</element>
               </WhiteList>
          </element>
          <element>
               <BlackList>
                    <element>1.1.1.1/1</element>
                    <element>1.1.1.2/2</element>
               </BlackList>
               <CcEnabled>false</CcEnabled>
               <CcRuleEnabled>true</CcRuleEnabled>
               <CcTemplate>default</CcTemplate>
               <CertName>www_alibaba_com.pem</CertName>
               <Domain>www.alibaba.com</Domain>
               <ProxyTypeList>
                    <element>
                         <ProxyPorts>
                              <element>80</element>
                              <element>8080</element>
                         </ProxyPorts>
                         <ProxyType>http</ProxyType>
                    </element>
               </ProxyTypeList>
               <RealServers>
                    <element>
                         <RealServer>1.1.1.1</RealServer>
                         <RsType>0</RsType>
                    </element>
                    <element>
                         <RealServer>1.1.1.2</RealServer>
                         <RsType>1</RsType>
                    </element>
               </RealServers>
               <WhiteList>
                    <element>1.1.1.1/1</element>
                    <element>1.1.1.2/2</element>
               </WhiteList>
          </element>
     </Domains>
     <RequestId>0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc</RequestId>
     <Total>2</Total>
</DescribeDomainsResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc",
	"Domains":[
		{
			"BlackList":[
				"1.1.1.1/1",
				"1.1.1.2/2"
			],
			"Domain":"www.alibaba.com",
			"ProxyTypeList":[
				{
					"ProxyPorts":[
						80,
						8080
					],
					"ProxyType":"http"
				}
			],
			"RealServers":[
				{
					"RealServer":"1.1.1.1",
					"RsType":0
				},
				{
					"RealServer":"1.1.1.2",
					"RsType":1
				}
			],
			"CcTemplate":"default",
			"CertName":"www_alibaba_com.pem",
			"CcRuleEnabled":true,
			"WhiteList":[
				"1.1.1.1/1",
				"1.1.1.2/2"
			],
			"CcEnabled":false
		},
		{
			"BlackList":[
				"1.1.1.1/1",
				"1.1.1.2/2"
			],
			"Domain":"www.alibaba.com",
			"ProxyTypeList":[
				{
					"ProxyPorts":[
						80,
						8080
					],
					"ProxyType":"http"
				}
			],
			"RealServers":[
				{
					"RealServer":"1.1.1.1",
					"RsType":0
				},
				{
					"RealServer":"1.1.1.2",
					"RsType":1
				}
			],
			"CcTemplate":"default",
			"CertName":"www_alibaba_com.pem",
			"CcRuleEnabled":true,
			"WhiteList":[
				"1.1.1.1/1",
				"1.1.1.2/2"
			],
			"CcEnabled":false
		}
	],
	"Total":2
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/ddoscoo)查看更多错误码。

