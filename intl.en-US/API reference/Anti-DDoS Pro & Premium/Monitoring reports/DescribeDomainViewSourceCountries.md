# DescribeDomainViewSourceCountries

Queries the regions outside China from which requests are sent to a website within a specific period of time.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=ddoscoo&api=DescribeDomainViewSourceCountries&type=RPC&version=2020-01-01)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeDomainViewSourceCountries|The operation that you want to perform. Set the value to **DescribeDomainViewSourceCountries**. |
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
|SourceCountrys|Array of Country| |Details about the country or area from which the requests are sent. |
|Count|Long|3390671|The number of requests. |
|CountryId|String|cn|The abbreviation of the country or area. For more information, see the **Codes of countries and areas** section of the [Codes of administrative regions in China and codes of countries and areas](~~167926~~) topic. For example, **cn** indicates China, and **us** indicates the United States. |

## Examples

Sample requests

```
http(s)://[Endpoint]/? Action=DescribeDomainViewSourceCountries
&EndTime=1583683200
&StartTime=1582992000
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeDomainViewSourceCountriesResponse>
	  <RequestId>C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E</RequestId>
	  <SourceCountrys>
		    <Count>3390671</Count>
		    <CountryId>cn</CountryId>
	  </SourceCountrys>
</DescribeDomainViewSourceCountriesResponse>
```

`JSON` format

```
{
    "RequestId": "C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E",
    "SourceCountrys": [
        {
            "Count": 3390671,
            "CountryId": "cn"
        }
    ]
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/ddoscoo).

