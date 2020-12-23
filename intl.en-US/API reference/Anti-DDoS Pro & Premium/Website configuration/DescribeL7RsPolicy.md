# DescribeL7RsPolicy

Queries the back-to-origin policies for the forwarding rule of a website.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=ddoscoo&api=DescribeL7RsPolicy&type=RPC&version=2020-01-01)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeL7RsPolicy|The operation that you want to perform. Set the value to **DescribeL7RsPolicy**. |
|RegionId|String|No|cn-hangzhou|The region ID of the instance. Valid values:

-   **cn-hangzhou**: mainland China, which indicates an Anti-DDoS Pro instance
-   **ap-southeast-1**: outside mainland China, which indicates an Anti-DDoS Premium instance |
|ResourceGroupId|String|No|rg-acfm2pz25js\*\*\*\*|The ID of the resource group to which the instance belongs in Resource Management. This parameter is empty by default, which indicates that the instance belongs to the default resource group.

For more information about resource groups, see [Create a resource group](~~94485~~). |
|Domain|String|No|www.aliyun.com|The domain name of the website.

**Note:** A forwarding rule must be configured for the domain name. You can call the [DescribeDomains](~~91724~~) operation to query the domain names for which the forwarding rules are created. |
|RealServers.N|RepeatList|No|1.\*\*\*. \*\*\*.1|The IP address of origin server N that you want to query. |

All Alibaba Cloud API operations must include common request parameters. For more information about common request parameters, see [Common parameters](~~157269~~).

For more information about sample requests, see the **"Examples"** section of this topic.

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Attributes|Array of AttributeItem| |The details of the parameters for back-to-origin. |
|Attribute|Struct| |The parameter for back-to-origin. |
|Weight|Integer|100|The weight of the server. This parameter takes effect only when **ProxyMode** is set to **rr**.

Valid values: **1** to **100**. Default value: **100**. A server with a higher weight receives more requests. |
|RealServer|String|1.\*\*\*. \*\*\*.1|The address of the origin server. |
|RsType|Integer|0|The address type of the origin server. Valid values:

-   **0**: IP address
-   **1**: domain name |
|ProxyMode|String|rr|The load balancing algorithm for back-to-origin traffic. Valid values:

-   **ip\_hash**: the IP hash algorithm. This algorithm is used to redirect the requests from the same IP address to the same origin server.
-   **rr**: the round-robin algorithm. This algorithm is used to redirect requests to origin servers in turn.
-   **least\_time**: the least response time algorithm. This algorithm is used to minimize the latency when requests are forwarded from Anti-DDoS Pro or Anti-DDoS Premium instances to origin servers based on the intelligent DNS resolution feature. |
|RequestId|String|9E7F6B2C-03F2-462F-9076-B782CF0DD502|The ID of the request. |

## Examples

Sample requests

```
http(s)://[Endpoint]/?Action=DescribeL7RsPolicy
&Domain=www.aliyun.com
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeL7RsPolicyResponse>
      <RequestId>9E7F6B2C-03F2-462F-9076-B782CF0DD502</RequestId>
      <Attributes>
            <RealServer>1. ***. ***.1</RealServer>
            <Attribute>
                  <Weight>100</Weight>
            </Attribute>
      </Attributes>
      <Attributes>
            <RealServer>2. ***. ***.2</RealServer>
            <Attribute>
                  <Weight>100</Weight>
            </Attribute>
      </Attributes>
      <ProxyMode>rr</ProxyMode>
</DescribeL7RsPolicyResponse>
```

`JSON` format

```
{
    "RequestId": "9E7F6B2C-03F2-462F-9076-B782CF0DD502",
    "Attributes": [
        {
            "RealServer": "1. ***. ***.1",
            "Attribute": {
                "Weight": 100
            }
        },
        {
            "RealServer": "2. ***. ***.2",
            "Attribute": {
                "Weight": 100
            }
        }
    ],
    "ProxyMode": "rr"
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/ddoscoo).

