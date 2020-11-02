# DescribeDomainViewTopCostTime

Queries the top N URLs that require the longest time to respond to requests within a specific period of time.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=ddoscoo&api=DescribeDomainViewTopCostTime&type=RPC&version=2020-01-01)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeDomainViewTopCostTime|The operation that you want to perform. Set the value to **DescribeDomainViewTopCostTime**. |
|EndTime|Long|Yes|1583683200|The end of the time range to query. This value is a UNIX timestamp representing the number of seconds that have elapsed since the epoch time January 1, 1970, 00:00:00 UTC.

 **Note:** This UNIX timestamp must indicate a time that is accurate to the minute. |
|StartTime|Long|Yes|1582992000|The beginning of the time range to query. This value is a UNIX timestamp representing the number of seconds that have elapsed since the epoch time January 1, 1970, 00:00:00 UTC.

 **Note:** This UNIX timestamp must indicate a time that is accurate to the minute. |
|Top|Integer|Yes|5|The number of URLs to query. Valid values: **1** to **100**. |
|ResourceGroupId|String|No|default|The ID of the resource group to which the instance belongs in Resource Management. This parameter is empty by default, which indicates that the instance belongs to the default resource group. |
|RegionId|String|No|cn-hangzhou|The region ID of the instance. Valid values:

 -   **cn-hangzhou**: mainland China, which indicates an Anti-DDoS Pro instance
-   **ap-southeast-1**: outside mainland China, which indicates an Anti-DDoS Premium instance |
|Domain|String|No|www.aliyun.com|The domain name of the website.

 **Note:** A forwarding rule must be configured for the domain name. You can call the [DescribeDomains](~~91724~~) operation to query all domain names. |

All Alibaba Cloud API operations must include common request parameters. For more information about common request parameters, see [Common parameters](~~157269~~).

For more information about sample requests, see the **"Examples"** section of this topic.

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E|The ID of the request. |
|UrlList|Array of Url| |The URLs who require the longest time to respond to requests. |
|CostTime|Float|3000|The response duration. Unit: milliseconds. |
|Domain|String|www.aliyun.com|The domain name of the website. |
|Url|String|Lw==|The URL that is Base64-encoded. |

## Examples

Sample requests

```
http(s)://[Endpoint]/? Action=DescribeDomainViewTopCostTime
&EndTime=1583683200
&StartTime=1582992000
&Top=5
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeDomainViewTopCostTimeResponse>
	  <RequestId>C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E</RequestId>
	  <UrlList>
		    <CostTime>3000</CostTime>
		    <Domain>www.aliyun.com</Domain>
		    <Url>Lw==</Url>
	  </UrlList>
</DescribeDomainViewTopCostTimeResponse>
```

`JSON` format

```
{
    "RequestId": "C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E",
    "UrlList": [
        {
            "CostTime": 3000,
            "Domain": "www.aliyun.com",
            "Url": "Lw=="
        }
    ]
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/ddoscoo).

