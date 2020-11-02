# DescribeDomainStatusCodeCount

Queries the statistics on different response status codes of a website within a specific period of time.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=ddoscoo&api=DescribeDomainStatusCodeCount&type=RPC&version=2020-01-01)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeDomainStatusCodeCount|The operation that you want to perform. Set the value to **DescribeDomainStatusCodeCount**. |
|EndTime|Long|Yes|1583683200|The end of the time range to query. This value is a UNIX timestamp representing the number of seconds that have elapsed since the epoch time January 1, 1970, 00:00:00 UTC.

 **Note:** This UNIX timestamp must indicate a time that is accurate to the minute. |
|StartTime|Long|Yes|1582992000|The beginning of the time range to query. This value is a UNIX timestamp representing the number of seconds that have elapsed since the epoch time January 1, 1970, 00:00:00 UTC.

 **Note:** This UNIX timestamp must indicate a time that is accurate to the minute. |
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
|Status200|Long|951159|The number of 200 response status codes within a specific period of time. |
|Status2XX|Long|951472|The number of 2xx response status codes within a specific period of time. |
|Status3XX|Long|133209|The number of 3xx response status codes within a specific period of time. |
|Status403|Long|0|The number of 403 response status codes within a specific period of time. |
|Status404|Long|897|The number of 404 response status codes within a specific period of time. |
|Status405|Long|0|The number of 405 response status codes within a specific period of time. |
|Status4XX|Long|5653|The number of 4xx response status codes within a specific period of time. |
|Status501|Long|0|The number of 501 response status codes within a specific period of time. |
|Status502|Long|0|The number of 502 response status codes within a specific period of time. |
|Status503|Long|0|The number of 503 response status codes within a specific period of time. |
|Status504|Long|0|The number of 504 response status codes within a specific period of time. |
|Status5XX|Long|14|The number of 5xx response status codes within a specific period of time. |

## Examples

Sample requests

```
http(s)://[Endpoint]/? Action=DescribeDomainStatusCodeCount
&EndTime=1583683200
&StartTime=1582992000
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeDomainStatusCodeCountResponse>
	  <RequestId>C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E</RequestId>
	  <Status2XX>951472</Status2XX>
	  <Status200>951159</Status200>
	  <Status3XX>133209</Status3XX>
	  <Status4XX>5653</Status4XX>
	  <Status403>0</Status403>
	  <Status404>897</Status404>
	  <Status405>0</Status405>
	  <Status5XX>14</Status5XX>
	  <Status501>0</Status501>
	  <Status502>0</Status502>
	  <Status503>0</Status503>
	  <Status504>0</Status504>
</DescribeDomainStatusCodeCountResponse>
```

`JSON` format

```
{
    "RequestId": "C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E",
    "Status2XX": 951472,
    "Status200": 951159,
    "Status3XX": 133209,
    "Status4XX": 5653,
    "Status403": 0,
    "Status404": 897,
    "Status405": 0,
    "Status5XX": 14,
    "Status501": 0,
    "Status502": 0,
    "Status503": 0,
    "Status504": 0
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/ddoscoo).

