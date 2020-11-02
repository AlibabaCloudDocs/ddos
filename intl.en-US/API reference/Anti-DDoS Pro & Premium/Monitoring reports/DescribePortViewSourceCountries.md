# DescribePortViewSourceCountries

Queries the countries or areas from which requests are sent to one or more Anti-DDoS Pro or Anti-DDoS Premium instances within a specific period of time.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=ddoscoo&api=DescribePortViewSourceCountries&type=RPC&version=2020-01-01)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribePortViewSourceCountries|The operation that you want to perform. Set the value to **DescribePortViewSourceCountries**. |
|EndTime|Long|Yes|1583683200|The end of the time range to query. This value is a UNIX timestamp representing the number of seconds that have elapsed since the epoch time January 1, 1970, 00:00:00 UTC.

 **Note:** This UNIX timestamp must indicate a time that is accurate to the minute. |
|InstanceIds.N|RepeatList|Yes|ddoscoo-cn-mp91j1ao\*\*\*\*|The ID of the instance.

 **Note:** You can call the [DescribeInstanceIds](~~157459~~) operation to query the IDs of all instances. |
|StartTime|Long|Yes|1582992000|The beginning of the time range to query. This value is a UNIX timestamp representing the number of seconds that have elapsed since the epoch time January 1, 1970, 00:00:00 UTC.

 **Note:** This UNIX timestamp must indicate a time that is accurate to the minute. |
|RegionId|String|No|cn-hangzhou|The region ID of the instance. Valid values:

 -   **cn-hangzhou**: mainland China, which indicates an Anti-DDoS Pro instance
-   **ap-southeast-1**: outside mainland China, which indicates an Anti-DDoS Premium instance |
|ResourceGroupId|String|No|default|The ID of the resource group to which the instance belongs. For more information, see [Resource Management](~~94475~~). By default, this parameter is left empty, which indicates that the instance belongs to the default resource group. |

All Alibaba Cloud API operations must include common request parameters. For more information about common request parameters, see [Common parameters](~~157269~~).

For more information about sample requests, see the **"Examples"** section of this topic.

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E|The ID of the request. |
|SourceCountrys|Array of Country| |Details about the country or area from which requests are sent. |
|Count|Long|3390671|The number of requests. |
|CountryId|String|cn|The code of the country or area from which requests are sent. For more information, see [Codes of administrative regions in China and codes of countries and areas](~~167926~~). For example, **cn** indicates China, and **us** indicates the United States. |

## Examples

Sample requests

```
http(s)://[Endpoint]/? Action=DescribePortViewSourceCountries
&EndTime=1583683200
&InstanceIds.1=ddoscoo-cn-mp91j1ao****
&StartTime=1582992000
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribePortViewSourceCountriesResponse>
	  <RequestId>C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E</RequestId>
	  <SourceCountrys>
		    <Count>3390671</Count>
		    <CountryId>cn</CountryId>
	  </SourceCountrys>
</DescribePortViewSourceCountriesResponse>
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

