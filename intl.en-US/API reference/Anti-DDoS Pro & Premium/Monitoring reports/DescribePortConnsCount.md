# DescribePortConnsCount

Queries the statistics on the connections established over the ports of one or more Anti-DDoS Pro or Anti-DDoS Premium instances.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=ddoscoo&api=DescribePortConnsCount&type=RPC&version=2020-01-01)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribePortConnsCount|The operation that you want to perform. Set the value to **DescribePortConnsCount**. |
|EndTime|Long|Yes|1583683200|The end of the time range to query. This value is a UNIX timestamp representing the number of seconds that have elapsed since the epoch time January 1, 1970, 00:00:00 UTC.

 **Note:** This UNIX timestamp must indicate a time that is accurate to the minute. |
|InstanceIds.N|RepeatList|Yes|ddoscoo-cn-mp91j1ao\*\*\*\*|The ID of the instance.

 **Note:** You can call the [DescribeInstanceIds](~~157459~~) operation to query the IDs of all instances. |
|StartTime|Long|Yes|1582992000|The beginning of the time range to query. This value is a UNIX timestamp representing the number of seconds that have elapsed since the epoch time January 1, 1970, 00:00:00 UTC.

 **Note:** This UNIX timestamp must indicate a time that is accurate to the minute. |
|RegionId|String|No|cn-hangzhou|The region ID of the instance. Valid values:

 -   **cn-hangzhou**: mainland China, which indicates an Anti-DDoS Pro instance
-   **ap-southeast-1**: outside mainland China, which indicates an Anti-DDoS Premium instance |
|ResourceGroupId|String|No|default|The ID of the resource group to which the instance belongs in Resource Management. This parameter is empty by default, which indicates that the instance belongs to the default resource group. |
|Port|String|No|80|The number of port that you want to query. If you do not specify this parameter, all ports are queried. |

All Alibaba Cloud API operations must include common request parameters. For more information about common request parameters, see [Common parameters](~~157269~~).

For more information about sample requests, see the **"Examples"** section of this topic.

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|ActConns|Long|159|The number of active connections. |
|Conns|Long|46340|The number of concurrent connections. |
|Cps|Long|0|The number of new connections. |
|InActConns|Long|121|The number of inactive connections. |
|RequestId|String|48859E14-A9FB-4100-99FF-AAB75CA46776|The ID of the request. |

## Examples

Sample requests

```
http(s)://[Endpoint]/? Action=DescribePortConnsCount
&EndTime=1583683200
&InstanceIds.1=ddoscoo-cn-mp91j1ao****
&StartTime=1582992000
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribePortConnsCountResponse>
	  <Conns>46340</Conns>
	  <RequestId>48859E14-A9FB-4100-99FF-AAB75CA46776</RequestId>
	  <Cps>0</Cps>
	  <ActConns>159</ActConns>
	  <InActConns>121</InActConns>
</DescribePortConnsCountResponse>
```

`JSON` format

```
{
	"Conns": 46340,
	"RequestId": "48859E14-A9FB-4100-99FF-AAB75CA46776",
	"Cps": 0,
	"ActConns": 159,
	"InActConns": 121
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/ddoscoo).

