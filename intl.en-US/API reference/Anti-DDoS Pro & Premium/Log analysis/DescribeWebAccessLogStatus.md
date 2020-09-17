# DescribeWebAccessLogStatus

Queries the Log Analysis configuration of a single website, such as the feature status and the Log Service project and Logstore that are used.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer automatically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=ddoscoo&api=DescribeWebAccessLogStatus&type=RPC&version=2020-01-01)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeWebAccessLogStatus|The operation that you want to perform. Set the value to **DescribeWebAccessLogStatus**. |
|Domain|String|Yes|www.aliyun.com|The domain name of the website.

**Note:** A forwarding rule must be configured for the domain name. You can call the [DescribeDomains](~~91724~~) operation to query all domain names. |
|RegionId|String|No|cn-hangzhou|The ID of the region where your service is deployed. Valid values:

-   **cn-hangzhou**: mainland China, which indicates an Anti-DDoS Pro instance
-   **ap-southeast-1**: outside mainland China, which indicates an Anti-DDoS Premium instance |
|ResourceGroupId|String|No|default|The ID of the resource group to which the instance belongs in Resource Management. This parameter is empty by default, which indicates that the instance belongs to the default resource group. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|CF33B4C3-196E-4015-AADD-5CAD00057B80|The ID of the request. |
|SlsLogstore|String|ddoscoo-logstore|The Logstore of the Anti-DDoS Pro or Anti-DDoS Premium instance. |
|SlsProject|String|ddoscoo-project-128965410602\*\*\*\*-cn-hangzhou|The Log Service project of the Anti-DDoS Pro or Anti-DDoS Premium instance. |
|SlsStatus|Boolean|true|Indicates whether the Log Analysis feature is enabled for the website. Valid values:

-   **true**: enabled
-   **false**: disabled |

## Examples

Sample requests

```
http(s)://[Endpoint]/?Action=DescribeWebAccessLogStatus
&Domain=www.aliyun.com
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeWebAccessLogStatusResponse>
      <RequestId>CF33B4C3-196E-4015-AADD-5CAD00057B80</RequestId>
      <SlsStatus>true</SlsStatus>
      <SlsProject>ddoscoo-project-128965410602****-cn-hangzhou</SlsProject>
      <SlsLogstore>ddoscoo-logstore</SlsLogstore>
</DescribeWebAccessLogStatusResponse>
```

`JSON` format

```
{
    "RequestId": "CF33B4C3-196E-4015-AADD-5CAD00057B80",
    "SlsStatus": true,
    "SlsProject": "ddoscoo-project-128965410602****-cn-hangzhou",
    "SlsLogstore": "ddoscoo-logstore"
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/ddoscoo).

