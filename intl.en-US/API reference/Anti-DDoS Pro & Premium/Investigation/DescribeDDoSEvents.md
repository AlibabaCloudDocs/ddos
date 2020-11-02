# DescribeDDoSEvents

Queries attack events launched against one or more Anti-DDoS Pro or Anti-DDoS Premium instances.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=ddoscoo&api=DescribeDDoSEvents&type=RPC&version=2020-01-01)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeDDoSEvents|The operation that you want to perform. Set the value to **DescribeDdoSEvents**. |
|InstanceIds.N|RepeatList|Yes|ddoscoo-cn-mp91j1ao\*\*\*\*|The ID of the instance.

 **Note:** You can call the [DescribeInstanceIds](~~157459~~) operation to query the IDs of all instances. |
|PageNumber|Integer|Yes|1|The number of the page to return. Pages start from page **1**. |
|PageSize|Integer|Yes|10|The number of entries to return on each page. |
|StartTime|Long|Yes|1582992000|The beginning of the time range to query. This value is a UNIX timestamp representing the number of seconds that have elapsed since the epoch time January 1, 1970, 00:00:00 UTC.

 **Note:** This UNIX timestamp must indicate a time that is accurate to the minute. |
|RegionId|String|No|cn-hangzhou|The region ID of the instance. Valid values:

 -   **cn-hangzhou**: mainland China, which indicates an Anti-DDoS Pro instance
-   **ap-southeast-1**: outside mainland China, which indicates an Anti-DDoS Premium instance |
|ResourceGroupId|String|No|default|The ID of the resource group to which the instance belongs in Resource Management. This parameter is empty by default, which indicates that the instance belongs to the default resource group. |
|EndTime|Long|No|1583683200|The end of the time range to query. This value is a UNIX timestamp representing the number of seconds that have elapsed since the epoch time January 1, 1970, 00:00:00 UTC.

 **Note:** This UNIX timestamp must indicate a time that is accurate to the minute. |

All Alibaba Cloud API operations must include common request parameters. For more information about common request parameters, see [Common parameters](~~157269~~).

For more information about sample requests, see the **"Examples"** section of this topic.

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|DDoSEvents|Array of Data| |The DDoS attack events. |
|Bps|Long|0|The bandwidth of attack traffic. Unit: bit/s. |
|EndTime|Long|1583933330|The time when the attack stopped. This value is a UNIX timestamp representing the number of seconds that have elapsed since the epoch time January 1, 1970, 00:00:00 UTC. |
|EventType|String|blackhole|The type of the attack event. Valid values:

 -   **defense**: traffic scrubbing events
-   **blackhole**: blackhole filtering events |
|Ip|String|203.\*\*\*. \*\*\*.132|The attacked IP address. |
|Port|String|80|The attacked port. |
|Pps|Long|0|The packet forwarding rate of attack traffic. Unit: packets per second. |
|Region|String|cn|The region from which the attack was launched. Valid values:

 -   **cn**: mainland China
-   **alb-ap-northeast-1-gf-x**: Japan
-   **alb-ap-southeast-gf-x**: Singapore
-   **alb-cn-hongkong-gf-x**: Hong Kong \(China\)
-   **alb-eu-central-1-gf-x**: Germany
-   **alb-us-west-1-gf-x**: Western United States

 **Note:** The values except **cn** are only returned when **RegionId** is **ap-southeast-1**. |
|StartTime|Long|1583933277|The time when the attack event started. This value is a UNIX timestamp representing the number of seconds that have elapsed since the epoch time January 1, 1970, 00:00:00 UTC. |
|RequestId|String|0CA72AF5-1795-4350-8C77-50A448A2F334|The ID of the request. |
|Total|Long|1|The total number of returned attack events. |

## Examples

Sample requests

```
http(s)://[Endpoint]/? Action=DescribeDDoSEvents
&InstanceIds.1=ddoscoo-cn-mp91j1ao****
&PageNumber=1
&PageSize=10
&StartTime=1582992000
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeDDoSEventsResponse>
	  <RequestId>0CA72AF5-1795-4350-8C77-50A448A2F334</RequestId>
	  <Total>1</Total>
	  <DDoSEvents>
		    <Pps>0</Pps>
		    <Bps>0</Bps>
		    <EndTime>1583933330</EndTime>
		    <EventType>blackhole</EventType>
		    <Ip>203. ***. ***.132</Ip>
		    <Port></Port>
		    <StartTime>1583933277</StartTime>
	  </DDoSEvents>
</DescribeDDoSEventsResponse>
```

`JSON` format

```
{
	"RequestId": "0CA72AF5-1795-4350-8C77-50A448A2F334",
	"Total": 1,
	"DDoSEvents": [
		{
			"Pps": 0,
			"Bps": 0,
			"EndTime": 1583933330,
			"EventType": "blackhole",
			"Ip": "203. ***. ***.132",
			"Port": "",
			"StartTime": 1583933277
		}
	]
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/ddoscoo).

