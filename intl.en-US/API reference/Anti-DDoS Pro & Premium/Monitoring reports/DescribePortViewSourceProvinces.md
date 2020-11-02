# DescribePortViewSourceProvinces

Queries the administrative regions inside China from which requests are sent to one or more Anti-DDoS Pro or Anti-DDoS Premium instances within a specific period of time.

**Note:** This operation cannot reflect the actual traffic volume because Layer 4 identity authentication algorithms are updated for Anti-DDoS Pro and Anti-DDoS Premium. You can call this operation to calculate only the proportion of requests sent from different administrative regions. If you want to obtain the request traffic volume, we recommend that you call the [DescribePortFlowList](~~157460~~) operation.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=ddoscoo&api=DescribePortViewSourceProvinces&type=RPC&version=2020-01-01)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribePortViewSourceProvinces|The operation that you want to perform. Set the value to **DescribePortViewSourceProvinces**. |
|InstanceIds.N|RepeatList|Yes|ddoscoo-cn-mp91j1ao\*\*\*\*|The ID of the instance.

 **Note:** You can call the [DescribeInstanceIds](~~157459~~) operation to query the IDs of all instances. |
|StartTime|Long|Yes|1582992000|The beginning of the time range to query. This value is a UNIX timestamp representing the number of seconds that have elapsed since the epoch time January 1, 1970, 00:00:00 UTC.

 **Note:** This UNIX timestamp must indicate a time that is accurate to the minute. |
|RegionId|String|No|cn-hangzhou|The ID of the region where you service is deployed. Valid values:

 -   **cn-hangzhou**: mainland China, which indicates an Anti-DDoS Pro instance
-   **ap-southeast-1**: outside mainland China, which indicates an Anti-DDoS Premium instance |
|ResourceGroupId|String|No|default|The ID of the resource group to which the instance belongs in Resource Management. This parameter is empty by default, which indicates that the instance belongs to the default resource group. |
|EndTime|Long|No|1583683200|The end of the time range to query. This value is a UNIX timestamp representing the number of seconds that have elapsed since the epoch time January 1, 1970, 00:00:00 UTC. If you do not specify this parameter, the current system time is used as the end time.

 **Note:** This UNIX timestamp must indicate a time that is accurate to the minute. |

All Alibaba Cloud API operations must include common request parameters. For more information about common request parameters, see [Common parameters](~~157269~~).

For more information about sample requests, see the **"Examples"** section of this topic.

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E|The ID of the request. |
|SourceProvinces|Array of Province| |Details about the administrative region inside China from which the requests are sent. |
|Count|Long|3390671|The number of requests.

 **Note:** This parameter does not indicate the accurate number of requests. You can use this parameter to calculate the proportion of requests from different administrative regions. |
|ProvinceId|String|440000|The ID of the administrative region. For more information, see [Codes of administrative regions in China and codes of countries and areas](~~167926~~). For example, **110000** indicates Beijing, and **120000** indicates Tianjin. |

## Examples

Sample requests

```
http(s)://[Endpoint]/? Action=DescribePortViewSourceProvinces
&InstanceIds.1=ddoscoo-cn-mp91j1ao****
&StartTime=1582992000
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribePortViewSourceProvincesResponse>
	  <RequestId>C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E</RequestId>
	  <SourceProvinces>
		    <Count>3390671</Count>
		    <ProvinceId>440000</ProvinceId>
	  </SourceProvinces>
</DescribePortViewSourceProvincesResponse>
```

`JSON` format

```
{
    "RequestId": "C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E",
    "SourceProvinces": [
        {
            "Count": 3390671,
            "ProvinceId": "440000"
        }
    ]
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/ddoscoo).

