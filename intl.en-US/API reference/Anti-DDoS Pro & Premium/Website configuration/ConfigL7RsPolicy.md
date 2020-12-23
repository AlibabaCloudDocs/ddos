# ConfigL7RsPolicy

Configures a back-to-origin policy for the forwarding rule of a website.

If multiple origin servers are configured for a website that is added to Anti-DDoS Pro or Anti-DDoS Premium, you can modify the load balancing algorithms for back-to-origin traffic based on back-to-origin policies. The IP hash algorithm is used by default. You can change the algorithm to the round-robin or least response time algorithm. For more information, see the description of the **Policy** parameter in the "Request parameters" section of this topic.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=ddoscoo&api=ConfigL7RsPolicy&type=RPC&version=2020-01-01)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|ConfigL7RsPolicy|The operation that you want to perform. Set the value to **ConfigL7RsPolicy**. |
|Domain|String|Yes|www.aliyun.com|The domain name of the website.

**Note:** A forwarding rule must be configured for the domain name. You can call the [DescribeDomains](~~91724~~) operation to query the domain names for which the forwarding rules are created. |
|Policy|String|Yes|\{"ProxyMode":"rr","Attributes":\[\{"RealServer":"1. \*\*\*. \*\*\*.1","Attribute":\{"Weight":100\}\},\{"RealServer":"2. \*\*\*. \*\*\*.2","Attribute":\{"Weight":100\}\}\]\}|The back-to-origin policy. This parameter is a string that contains a JSON struct. The JSON struct includes the following fields:

-   **ProxyMode**: The load balancing algorithm for back-to-origin traffic. This field is required and must be a string. Valid values:
    -   **ip\_hash**: the IP hash algorithm. This algorithm is used to redirect the requests from the same IP address to the same origin server.
    -   **rr**: the round-robin algorithm. This algorithm is used to redirect requests to origin servers in turn. If you use this algorithm, you can configure different weights for different servers based on server performance.
    -   **least\_time**: the least response time algorithm. This algorithm is used to minimize the latency when requests are forwarded from Anti-DDoS Pro or Anti-DDoS Premium instances to origin servers based on the intelligent DNS resolution feature.
-   **Attributes**: the parameters for back-to-origin. This field is optional and must be a JSON array. Each element in the array contains the following fields:
    -   **RealServer**: the address of the origin server. This field is optional and must be a string.
    -   **Attribute**: the parameter for back-to-origin. This field is optional and must be a JSON object. The value contains the following field:
        -   **Weight**: the weight of the server. This field is optional and must be an integer. This field takes effect only when **ProxyMode** is set to **rr**. Valid values: **1** to **100**. Default value: **100**. A server with a higher weight receives more requests. |
|RegionId|String|No|cn-hangzhou|The region ID of the instance. Valid values:

-   **cn-hangzhou**: mainland China, which indicates an Anti-DDoS Pro instance
-   **ap-southeast-1**: outside mainland China, which indicates an Anti-DDoS Premium instance |
|ResourceGroupId|String|No|rg-acfm2pz25js\*\*\*\*|The ID of the resource group to which the instance belongs in Resource Management. This parameter is empty by default, which indicates that the instance belongs to the default resource group.

For more information about resource groups, see [Create a resource group](~~94485~~). |

All Alibaba Cloud API operations must include common request parameters. For more information about common request parameters, see [Common parameters](~~157269~~).

For more information about sample requests, see the **"Examples"** section of this topic.

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc|The ID of the request. |

## Examples

Sample requests

```
http(s)://[Endpoint]/?Action=ConfigL7RsPolicy
&Domain=www.aliyun.com
&Policy={\"ProxyMode\":\"rr\",\"Attributes\":[{\"RealServer\":\"1. ***. ***.1\",\"Attribute\":{\"Weight\":100}},{\"RealServer\":\"2. ***. ***.2\",\"Attribute\":{\"Weight\":100}}]}
&<Common request parameters>
```

Sample success responses

`XML` format

```
<ConfigL7RsPolicyResponse>
      <RequestId>0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc</RequestId>
</ConfigL7RsPolicyResponse>
```

`JSON` format

```
{
  "RequestId": "0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc"
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/ddoscoo).

