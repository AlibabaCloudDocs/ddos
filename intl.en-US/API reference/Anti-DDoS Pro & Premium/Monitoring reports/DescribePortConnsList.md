# DescribePortConnsList

Queries the connections established over the port of one or more Anti-DDoS Pro or Anti-DDoS Premium instances.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=ddoscoo&api=DescribePortConnsList&type=RPC&version=2020-01-01)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribePortConnsList|The operation that you want to perform. Set the value to **DescribePortConnsList**. |
|EndTime|Long|Yes|1583683200|The end of the time range to query. This value is a UNIX timestamp representing the number of seconds that have elapsed since the epoch time January 1, 1970, 00:00:00 UTC.

 **Note:** This UNIX timestamp must indicate a time that is accurate to the minute. |
|InstanceIds.N|RepeatList|Yes|ddoscoo-cn-mp91j1ao\*\*\*\*|The ID of the instance.

 **Note:** You can call the [DescribeInstanceIds](~~157459~~) operation to query the IDs of all instances. |
|Interval|Integer|Yes|1000|The intervals for returning statistics. Unit: seconds. |
|StartTime|Long|Yes|1582992000|The beginning of the time range to query. This value is a UNIX timestamp representing the number of seconds that have elapsed since the epoch time January 1, 1970, 00:00:00 UTC.

 **Note:** This UNIX timestamp must indicate a time that is accurate to the minute. |
|RegionId|String|No|cn-hangzhou|The region ID of the instance. Valid values:

 -   **cn-hangzhou**: mainland China, which indicates an Anti-DDoS Pro instance
-   **ap-southeast-1**: outside mainland China, which indicates an Anti-DDoS Premium instance |
|ResourceGroupId|String|No|default|The ID of the resource group to which the instance belongs in Resource Management. This parameter is empty by default, which indicates that the instance belongs to the default resource group. |
|Port|String|No|null|The number of port that you want to query. If you do not specify this parameter, all ports are queried. |

All Alibaba Cloud API operations must include common request parameters. For more information about common request parameters, see [Common parameters](~~157269~~).

For more information about sample requests, see the **"Examples"** section of this topic.

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|ConnsList|Array of Conn| |Details about the connections established over the port. |
|ActConns|Long|2|The number of active connections. |
|Conns|Long|20|The number of concurrent connections. |
|Cps|Long|0|The number of new connections. |
|InActConns|Long|4|The number of inactive connections. |
|Index|Long|0|The index number of the returned data. |
|Time|Long|1582992000|The time when the statistic was recorded. This value is a UNIX timestamp representing the number of seconds that have elapsed since the epoch time January 1, 1970, 00:00:00 UTC. |
|RequestId|String|7E6BF16F-27A9-49BC-AD18-F79B409DE753|The ID of the request. |

## Examples

Sample requests

```
http(s)://[Endpoint]/? Action=DescribePortConnsList
&EndTime=1583683200
&InstanceIds.1=ddoscoo-cn-mp91j1ao****
&Interval=1000
&StartTime=1582992000
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribePortConnsListResponse>
	  <ConnsList>
		    <Conns>20</Conns>
		    <Cps>0</Cps>
		    <Index>0</Index>
		    <ActConns>2</ActConns>
		    <InActConns>4</InActConns>
            <Time>1582992000</Time>
	  </ConnsList>
	  <ConnsList>
		    <Conns>24</Conns>
		    <Cps>0</Cps>
		    <Index>1</Index>
		    <ActConns>2</ActConns>
		    <InActConns>5</InActConns>
            <Time>1582993000</Time>
	  </ConnsList>
	  <RequestId>7E6BF16F-27A9-49BC-AD18-F79B409DE753</RequestId>
</DescribePortConnsListResponse>
```

`JSON` format

```
{
	"ConnsList": [
		{
			"Conns": 20,
			"Cps": 0,
			"Index": 0,
			"ActConns": 2,
			"InActConns": 4,
            "Time": 1582992000
		},
		{
			"Conns": 24,
			"Cps": 0,
			"Index": 1,
			"ActConns": 2,
			"InActConns": 5,
            "Time": 1582993000
		}
	],
	"RequestId": "7E6BF16F-27A9-49BC-AD18-F79B409DE753"
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/ddoscoo).

