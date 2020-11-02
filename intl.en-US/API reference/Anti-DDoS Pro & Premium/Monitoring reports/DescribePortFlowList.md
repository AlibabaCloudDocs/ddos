# DescribePortFlowList

Queries the traffic data of one or more Anti-DDoS Pro or Anti-DDoS Premium instances.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=ddoscoo&api=DescribePortFlowList&type=RPC&version=2020-01-01)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribePortFlowList|The operation that you want to perform. Set the value to **DescribePortFlowList**. |
|EndTime|Long|Yes|1583683200|The end of the time range to query. This value is a UNIX timestamp representing the number of seconds that have elapsed since the epoch time January 1, 1970, 00:00:00 UTC.

 **Note:** This UNIX timestamp must indicate a time that is accurate to the minute. |
|InstanceIds.N|RepeatList|Yes|ddoscoo-cn-mp91j1ao\*\*\*\*|The ID of the instance.

 **Note:** You can call the [DescribeInstanceIds](~~157459~~) operation to query the IDs of all instances. |
|Interval|Integer|Yes|1000|The intervals for returning statistcs. Unit: seconds. |
|StartTime|Long|Yes|1582992000|The beginning of the time range to query. This value is a UNIX timestamp representing the number of seconds that have elapsed since the epoch time January 1, 1970, 00:00:00 UTC.

 **Note:** This UNIX timestamp must indicate a time that is accurate to the minute. |
|ResourceGroupId|String|No|default|The ID of the resource group to which the instance belongs in Resource Management. This parameter is empty by default, which indicates that the instance belongs to the default resource group. |
|RegionId|String|No|cn-hangzhou|The region ID of the instance. Valid values:

 -   **cn-hangzhou**: mainland China, which indicates an Anti-DDoS Pro instance
-   **ap-southeast-1**: outside mainland China, which indicates an Anti-DDoS Premium instance |

All Alibaba Cloud API operations must include common request parameters. For more information about common request parameters, see [Common parameters](~~157269~~).

For more information about sample requests, see the **"Examples"** section of this topic.

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|PortFlowList|Array of PortFlow| |The traffic data. |
|AttackBps|Long|0|The bandwidth of attack traffic. Unit: bit/s. |
|AttackPps|Long|0|The packet forwarding rate of attack traffic. Unit: packets per second. |
|InBps|Long|2176000|The inbound bandwidth. Unit: bit/s. |
|InPps|Long|2934|The packet forwarding rate of inbound traffic. Unit: packets per second. |
|Index|Long|0|The index number of the returned data. |
|OutBps|Long|4389|The outbound bandwidth. Unit: bit/s. |
|OutPps|Long|5|The packet forwarding rate of outbound traffic. Unit: packets per second. |
|Region|String|cn|The region from which the traffic is from. Valid values:

 -   **cn**: mainland China
-   **alb-ap-northeast-1-gf-x**: Japan
-   **alb-ap-southeast-gf-x**: Singapore
-   **alb-cn-hongkong-gf-x**: Hong Kong \(China\)
-   **alb-eu-central-1-gf-x**: Germany
-   **alb-us-west-1-gf-x**: Western United States

 **Note:** The values except **cn** are only returned when **RegionId** is **ap-southeast-1**. |
|Time|Long|1582992000|The time when the statistic was recorded. This value is a UNIX timestamp representing the number of seconds that have elapsed since the epoch time January 1, 1970, 00:00:00 UTC. |
|RequestId|String|FFC77501-BDF8-4BC8-9BF5-B295FBC3189B|The ID of the request. |

## Examples

Sample requests

```
http(s)://[Endpoint]/? Action=DescribePortFlowList
&EndTime=1583683200
&InstanceIds.1=ddoscoo-cn-mp91j1ao****
&Interval=1000
&StartTime=1582992000
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribePortFlowListResponse>
	  <RequestId>FFC77501-BDF8-4BC8-9BF5-B295FBC3189B</RequestId>
	  <PortFlowList>
		    <OutPps>5</OutPps>
		    <OutBps>4389</OutBps>
		    <InBps>2176000</InBps>
		    <InPps>2934</InPps>
		    <Region>cn</Region>
		    <Index>0</Index>
		    <AttackBps>0</AttackBps>
		    <AttackPps>0</AttackPps>
            <Time>1582992000</Time>
	  </PortFlowList>
	  <PortFlowList>
		    <OutPps>5</OutPps>
		    <OutBps>4155</OutBps>
		    <InBps>4648000</InBps>
		    <InPps>6268</InPps>
		    <Region>cn</Region>
		    <Index>1</Index>
		    <AttackBps>0</AttackBps>
		    <AttackPps>0</AttackPps>
            <Time>1582993000</Time>
	  </PortFlowList>
</DescribePortFlowListResponse>
```

`JSON` format

```
{
	"RequestId": "FFC77501-BDF8-4BC8-9BF5-B295FBC3189B",
	"PortFlowList": [
		{
			"OutPps": 5,
			"OutBps": 4389,
			"InBps": 2176000,
			"InPps": 2934,
			"Region": "cn",
			"Index": 0,
			"AttackBps": 0,
			"AttackPps": 0,
            "Time": 1582992000
		},
		{
			"OutPps": 5,
			"OutBps": 4155,
			"InBps": 4648000,
			"InPps": 6268,
			"Region": "cn",
			"Index": 1,
			"AttackBps": 0,
			"AttackPps": 0,
            "Time": 1582993000
		}
	]
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/ddoscoo).

