# DescribePortViewSourceIsps

Queries the Internet service providers \(ISPs\) from which requests are sent to one or more Anti-DDoS Pro or Anti-DDoS Premium instances within a specific period of time.

**Note:** This operation cannot reflect the actual traffic volume because Layer 4 identity authentication algorithms are updated for Anti-DDoS Pro and Anti-DDoS Premium. You can call this operation to calculate only the proportion of requests sent from different ISPs. If you want to obtain the request traffic volume, we recommend that you call the [DescribePortFlowList](~~157460~~) operation.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=ddoscoo&api=DescribePortViewSourceIsps&type=RPC&version=2020-01-01)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribePortViewSourceIsps|The operation that you want to perform. Set the value to **DescribePortViewSourceIsps**. |
|EndTime|Long|Yes|1583683200|The end of the time range to query. This value is a UNIX timestamp representing the number of seconds that have elapsed since the epoch time January 1, 1970, 00:00:00 UTC. If you do not specify this parameter, the current system time is used as the end time.

 **Note:** This UNIX timestamp must indicate a time that is accurate to the minute. |
|InstanceIds.N|RepeatList|Yes|ddoscoo-cn-mp91j1ao\*\*\*\*|The ID of the instance.

 **Note:** You can call the [DescribeInstanceIds](~~157459~~) operation to query the IDs of all instances. |
|StartTime|Long|Yes|1582992000|The beginning of the time range to query. This value is a UNIX timestamp representing the number of seconds that have elapsed since the epoch time January 1, 1970, 00:00:00 UTC.

 **Note:** This UNIX timestamp must indicate a time that is accurate to the minute. |
|RegionId|String|No|cn-hangzhou|The region ID of the instance. Valid values:

 -   **cn-hangzhou**: mainland China, which indicates an Anti-DDoS Pro instance
-   **ap-southeast-1**: outside mainland China, which indicates an Anti-DDoS Premium instance |
|ResourceGroupId|String|No|default|The ID of the resource group to which the instance belongs in Resource Management. This parameter is empty by default, which indicates that the instance belongs to the default resource group. |

All Alibaba Cloud API operations must include common request parameters. For more information about common request parameters, see [Common parameters](~~157269~~).

For more information about sample requests, see the **"Examples"** section of this topic.

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Isps|Array of Isp| |Detail about the ISP. |
|Count|Long|3390671|The total number of requests transmitted from the ISP.

 **Note:** This parameter does not indicate the accurate number of requests. You can use this parameter to calculate the proportion of requests from different ISPs. |
|IspId|String|100017|The code of the ISP. For more information, see the ISP codes table. |
|RequestId|String|C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E|The ID of the request. |

**ISP codes**

|Code

|ISP |
|------|-----|
|100017

|China Telecom |
|100026

|China Unicom |
|100025

|China Mobile |
|100027

|China Education and Research Network |
|100020

|China Mobile Tietong |
|1000143

|Dr.Peng Telecom & Media Group |
|100080

|Beijing Gehua CATV Network |
|1000139

|National Radio and Television Administration |
|100023

|Oriental Cable Network |
|100063

|Founder Broadband |
|1000337

|China Internet Exchange |
|100021

|21Vianet |
|1000333

|Wasu Media Holding |
|100093

|Wangsu Science & Technology |
|1000401

|Tencent |
|100099

|Baidu |
|1000323

|Alibaba Cloud |
|100098

|Alibaba |

## Examples

Sample requests

```
http(s)://[Endpoint]/? Action=DescribePortViewSourceIsps
&EndTime=1583683200
&InstanceIds.1=ddoscoo-cn-mp91j1ao****
&StartTime=1582992000
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribePortViewSourceIspsResponse>
	  <RequestId>C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E</RequestId>
	  <Isps>
		    <Count>3390671</Count>
		    <IspId>100017</IspId>
	  </Isps>
</DescribePortViewSourceIspsResponse>
```

`JSON` format

```
{
    "RequestId": "C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E",
    "Isps": [
        {
            "Count": 3390671,
            "IspId": "100017"
        }
    ]
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/ddoscoo).

