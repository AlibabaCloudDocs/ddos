# DescribeDomainStatusCodeList

Queries the statistics on different response status codes of a website.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=ddoscoo&api=DescribeDomainStatusCodeList&type=RPC&version=2020-01-01)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeDomainStatusCodeList|The operation that you want to perform. Set the value to **DescribeDomainStatusCodeList**. |
|Interval|Long|Yes|1000|The intervals for returning statistics. Unit: seconds. |
|QueryType|String|Yes|gf|The source of the statistics. Valid values:

 -   **gf**: Anti-DDoS Pro or Anti-DDoS Premium
-   **upstrem**: origin server |
|StartTime|Long|Yes|1582992000|The beginning of the time range to query. This value is a UNIX timestamp representing the number of seconds that have elapsed since the epoch time January 1, 1970, 00:00:00 UTC.

 **Note:** This UNIX timestamp must indicate a time that is accurate to the minute. |
|ResourceGroupId|String|No|default|The ID of the resource group to which the instance belongs in Resource Management. This parameter is empty by default, which indicates that the instance belongs to the default resource group. |
|RegionId|String|No|cn-hangzhou|The region ID of the instance. Valid values:

 -   **cn-hangzhou**: mainland China, which indicates an Anti-DDoS Pro instance
-   **ap-southeast-1**: outside mainland China, which indicates an Anti-DDoS Premium instance |
|EndTime|Long|No|1583683200|The end of the time range to query. This value is a UNIX timestamp representing the number of seconds that have elapsed since the epoch time January 1, 1970, 00:00:00 UTC.

 **Note:** This UNIX timestamp must indicate a time that is accurate to the minute. |
|Domain|String|No|www.aliyun.com|The domain name of the website. If you do not specify this parameter, the statistics on response status codes of all domain names are queried.

 **Note:** A forwarding rule must be configured for the domain name. You can call the [DescribeDomains](~~91724~~) operation to query all domain names. |

All Alibaba Cloud API operations must include common request parameters. For more information about common request parameters, see [Common parameters](~~157269~~).

For more information about sample requests, see the **"Examples"** section of this topic.

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|3B63C0DD-8AC5-44B2-95D6-064CA9296B9C|The ID of the request. |
|StatusCodeList|Array of StatusCode| |The statistics on response status codes. |
|Index|Integer|0|The index number of the returned data. |
|Status200|Long|15520|The number of 200 response status codes. |
|Status2XX|Long|15520|The number of 2xx response status codes. |
|Status3XX|Long|0|The number of 3xx response status codes. |
|Status403|Long|0|The number of 403 response status codes. |
|Status404|Long|0|The number of 404 response status codes. |
|Status405|Long|0|The number of 405 response status codes. |
|Status4XX|Long|4486|The number of 4xx response status codes. |
|Status501|Long|0|The number of 501 response status codes. |
|Status502|Long|0|The number of 502 response status codes. |
|Status503|Long|0|The number of 503 response status codes. |
|Status504|Long|0|The number of 504 response status codes. |
|Status5XX|Long|0|The number of 5xx response status codes. |
|Time|Long|1582992000|The time when the statistic was recorded. This value is a UNIX timestamp representing the number of seconds that have elapsed since the epoch time January 1, 1970, 00:00:00 UTC. |

## Examples

Sample requests

```
http(s)://[Endpoint]/? Action=DescribeDomainStatusCodeList
&QueryType=gf
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeDomainStatusCodeListResponse>
	  <RequestId>3B63C0DD-8AC5-44B2-95D6-064CA9296B9C</RequestId>
	  <StatusCodeList>
		    <Status501>0</Status501>
		    <Status502>0</Status502>
		    <Status403>0</Status403>
		    <Index>0</Index>
		    <Time>1582992000</Time>
		    <Status503>0</Status503>
		    <Status404>0</Status404>
		    <Status504>0</Status504>
		    <Status405>0</Status405>
		    <Status2XX>15520</Status2XX>
		    <Status200>15520</Status200>
		    <Status3XX>0</Status3XX>
		    <Status4XX>4486</Status4XX>
		    <Status5XX>0</Status5XX>
	  </StatusCodeList>
</DescribeDomainStatusCodeListResponse>
```

`JSON` format

```
{
	"RequestId": "3B63C0DD-8AC5-44B2-95D6-064CA9296B9C",
	"StatusCodeList": [
		{
			"Status501": 0,
			"Status502": 0,
			"Status403": 0,
			"Index": 0,
			"Time": 1582992000,
			"Status503": 0,
			"Status404": 0,
			"Status504": 0,
			"Status405": 0,
			"Status2XX": 15520,
			"Status200": 15520,
			"Status3XX": 0,
			"Status4XX": 4486,
			"Status5XX": 0
		}
	]
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/ddoscoo).

