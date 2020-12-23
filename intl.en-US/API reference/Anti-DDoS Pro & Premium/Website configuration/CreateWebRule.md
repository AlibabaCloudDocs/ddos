# CreateWebRule

Creates a forwarding rule for a website.

For more information about how to create a forwarding rule in the Anti-DDoS Pro or Anti-DDoS Premium console, see [Add a website](~~143347~~). This topic describes how to add a website to an Anti-DDoS Pro or Anti-DDoS Premium instance. It also describes the configuration parameters.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=ddoscoo&api=CreateWebRule&type=RPC&version=2020-01-01)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|CreateWebRule|The operation that you want to perform. Set the value to **CreateWebRule**. |
|Domain|String|Yes|www.aliyun.com|The domain name of the website that you want to add to the instance. |
|RsType|Integer|Yes|0|The address type of the origin server. Valid values:

-   **0**: IP address.
-   **1**: domain name. Use the domain name of the origin server if you deploy proxies, such as Web Application Firewall \(WAF\), between the origin server and the Anti-DDoS Pro or Anti-DDoS Premium instance. If you use the domain name, you must enter the address of the proxy, such as the CNAME of WAF. |
|Rules|String|Yes|\[\{"ProxyRules":\[\{"ProxyPort":80,"RealServers":\["1.xxx.xxx.1"\]\}\],"ProxyType":"http"\},\{"ProxyRules":\[\{"ProxyPort":443,"RealServers":\["1.xxx.xxx.1"\]\}\],"ProxyType":"https"\}\]|The details about the forwarding rule. This parameter is a string consisting of JSON arrays. Each element in a JSON array is a JSON struct that includes the following fields:

-   **ProxyRules**: the information of the origin server. The information includes the port number and IP address. This field is required and must be a JSON array. Each element in the array contains the following fields:
    -   **ProxyPort**: the port number. This field is required and must be an integer.
    -   **RealServers**: the IP address. This field is required and must be a string array.
-   **ProxyType**: the protocol type. This field is required and must be a string. Valid values: **http**, **https**, **websocket**, and **websockets**. |
|RegionId|String|No|cn-hangzhou|The region ID of the instance. Valid values:

-   **cn-hangzhou**: mainland China, which indicates an Anti-DDoS Pro instance
-   **ap-southeast-1**: outside mainland China, which indicates an Anti-DDoS Premium instance |
|ResourceGroupId|String|No|rg-acfm2pz25js\*\*\*\*|The ID of the resource group to which the instance belongs in Resource Management. This parameter is empty by default, which indicates that the instance belongs to the default resource group.

For more information about resource groups, see [Create a resource group](~~94485~~). |
|HttpsExt|String|No|\{"Http2":1,"Http2https":1,"Https2http":1\}|The advanced HTTPS settings. This parameter takes effect only when the value of **ProxyType** includes **https**. This parameter is a string that contains a JSON struct. The JSON struct includes the following fields:

-   **Http2https**: specifies whether to turn on Enforce HTTPS Routing. This field is optional and must be an integer. Valid values: **0** and **1**. The value 0 indicates that Enforce HTTPS Routing is turned off. The value 1 indicates that Enforce HTTPS Routing is turned on. The default value is 0.

If your website supports both HTTP and HTTPS, this feature suits your needs. If you turn on the switch, all HTTP requests are redirected to HTTPS requests on port 443 by default.

-   **Https2http**: specifies whether to turn on Enable HTTP. This field is optional and must be an integer. Valid values: **0** and **1**. The value 0 indicates that Enable HTTP is turned off. The value 1 indicates that Enable HTTP is turned on. The default value is 0.

If your website does not support HTTPS, this feature suits your needs. If you turn on the switch, all HTTPS requests are redirected to HTTP requests and forwarded to origin servers. The feature can also redirect WebSockets requests to WebSocket requests. All requests are redirected over port 80.

-   **Http2**: specifies whether to turn on Enable HTTP/2. This field is optional and must be an integer. Valid values: **0** and **1**. The value 0 indicates that Enable HTTP/2 is turned off. The value 1 indicates that Enable HTTP/2 is turned on. The default value is 0.

After you turn on the switch, the protocol type is HTTP/2. |
|DefenseId|String|No|aaa.bbb.cn|The ID of the associated defense. This parameter applies to scenarios where other cloud services, such as Object Storage Service \(OSS\), are integrated with Anti-DDoS Pro or Anti-DDoS Premium.

**Note:** This parameter is in internal preview. Do not use this parameter.

For example, if you integrate OSS with Anti-DDoS Pro or Anti-DDoS Premium, Anti-DDoS Pro or Anti-DDoS Premium allocates an IP address pool for the OSS production account. Each IP address corresponds to a unique defense ID. A defense ID is a CNAME, which is automatically resolved to the IP address of the required Anti-DDoS Pro or Anti-DDoS Premium instance. A defense ID can be resolved to the same IP address to facilitate scheduling.

**Note:** You can specify only one of the following parameters: **InstanceIds** and **DefenseId**. |
|InstanceIds.N|RepeatList|No|ddoscoo-cn-mp91j1ao\*\*\*\*|The ID of instance N that you want to associate. If this parameter is empty, only the domain name of the website is added but no instance is associated with the website.

**Note:** You can call the [DescribeInstanceIds](~~157459~~) operation to query the IDs of all instances. |

All Alibaba Cloud API operations must include common request parameters. For more information about common request parameters, see [Common parameters](~~157269~~).

For more information about sample requests, see the **"Examples"** section of this topic.

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc|The ID of the request. |

## Examples

Sample requests

```
http(s)://[Endpoint]/?Action=CreateWebRule
&Domain=www.aliyun.com
&RsType=0
&Rules=[{\"ProxyRules\":[{\"ProxyPort\":80,\"RealServers\":[\"1.xxx.xxx.1\"]}],\"ProxyType\":\"http\"},{\"ProxyRules\":[{\"ProxyPort\":443,\"RealServers\":[\"1.xxx.xxx.1\"]}],\"ProxyType\":\"https\"}]
&<Common request parameters>
```

Sample success responses

`XML` format

```
<CreateWebRuleResponse>
      <RequestId>0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc</RequestId>
</CreateWebRuleResponse>
```

`JSON` format

```
{
  "RequestId": "0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc"
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/ddoscoo).

