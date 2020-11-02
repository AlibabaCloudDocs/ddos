# DescribeDomainAttackEvents

Queries attack events launched against a website.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=ddoscoo&api=DescribeDomainAttackEvents&type=RPC&version=2020-01-01)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeDomainAttackEvents|The operation that you want to perform. Set the value to **DescribeDomainAttackEvents**. |
|EndTime|Long|Yes|1583683200|The end of the time range to query. This value is a UNIX timestamp representing the number of seconds that have elapsed since the epoch time January 1, 1970, 00:00:00 UTC.

 **Note:** This UNIX timestamp must indicate a time that is accurate to the minute. |
|PageNumber|Integer|Yes|1|The number of the page to return. Pages start from page **1**. |
|PageSize|Integer|Yes|10|The number of entries returned per page. |
|StartTime|Long|Yes|1582992000|The beginning of the time range to query. This value is a UNIX timestamp representing the number of seconds that have elapsed since the epoch time January 1, 1970, 00:00:00 UTC.

 **Note:** This UNIX timestamp must indicate a time that is accurate to the minute. |
|RegionId|String|No|cn-hangzhou|The region ID of the instance. Valid values:

 -   **cn-hangzhou**: mainland China, which indicates an Anti-DDoS Pro instance
-   **ap-southeast-1**: outside mainland China, which indicates an Anti-DDoS Premium instance |
|ResourceGroupId|String|No|default|The ID of the resource group to which the instance belongs in Resource Management. This parameter is empty by default, which indicates that the instance belongs to the default resource group. |
|Domain|String|No|www.aliyun.com|The domain name of the website.

 **Note:** A forwarding rule must be configured for the domain name. You can call the [DescribeDomains](~~91724~~) operation to query all domain names. |

All Alibaba Cloud API operations must include common request parameters. For more information about common request parameters, see [Common parameters](~~157269~~).

For more information about sample requests, see the **"Examples"** section of this topic.

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|DomainAttackEvents|Array of Data| |Details about the DDoS attack event. |
|Domain|String|www.aliyun.com|The attacked domain name. |
|EndTime|Long|1560320160|The time when the DDoS attack stopped. This value is a UNIX timestamp representing the number of seconds that have elapsed since the epoch time January 1, 1970, 00:00:00 UTC. |
|MaxQps|Long|1000|The peak attack QPS. |
|StartTime|Long|1560312900|The time when the DDoS attack started. This value is a UNIX timestamp representing the number of seconds that have elapsed since the epoch time January 1, 1970, 00:00:00 UTC. |
|RequestId|String|C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E|The ID of the request. |
|TotalCount|Long|1|The total number of returned DDoS attack events. |

## Examples

Sample requests

```
http(s)://[Endpoint]/? Action=DescribeDomainAttackEvents
&EndTime=1583683200
&PageNumber=1
&PageSize=10
&StartTime=1582992000
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeDomainAttackEventsResponse>
	  <RequestId>C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E</RequestId>
	  <TotalCount>1</TotalCount>
	  <DomainAttackEvents>
		    <Domain>www.aliyun.com</Domain>
		    <MaxQps>1000</MaxQps>
		    <StartTime>1560312900</StartTime>
		    <EndTime>1560320160</EndTime>
	  </DomainAttackEvents>
</DescribeDomainAttackEventsResponse>
```

`JSON` format

```
{
    "RequestId": "C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E",
    "TotalCount": 1,
    "DomainAttackEvents": [{
        "Domain": "www.aliyun.com",
        "MaxQps": 1000,
        "StartTime": 1560312900,
        "EndTime": 1560320160
      }]
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/ddoscoo).

