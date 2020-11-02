# DescribePortMaxConns

Queries the maximum number of connections that can be established over the ports of one or more Anti-DDoS Pro or Anti-DDoS Premium instances.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=ddoscoo&api=DescribePortMaxConns&type=RPC&version=2020-01-01)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribePortMaxConns|The operation that you want to perform. Set the value to **DescribePortMaxConns**. |
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

All Alibaba Cloud API operations must include common request parameters. For more information about common request parameters, see [Common parameters](~~157269~~).

For more information about sample requests, see the **"Examples"** section of this topic.

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|PortMaxConns|Array of PortMaxConns| |Details about the maximum number of connections that are established over a port of the instance. |
|Cps|Long|100|The maximum number of connections per second \(CPS\). |
|Ip|String|203.\*\*\*. \*\*\*.117|The IP address of the instance. |
|Port|String|80|The port of the instance. |
|RequestId|String|08F79110-2AF5-4FA7-998E-7C5E75EACF9C|The ID of the request. |

## Examples

Sample requests

```
http(s)://[Endpoint]/? Action=DescribePortMaxConns
&EndTime=1583683200
&InstanceIds.1= ddoscoo-cn-mp91j1ao****
&StartTime=1582992000
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribePortMaxConnsResponse>
	  <PortMaxConns>
		    <Port>80</Port>
		    <Ip>203. ***. ***.117</Ip>
		    <Cps>0</Cps>
	  </PortMaxConns>
	  <PortMaxConns>
		    <Port>443</Port>
		    <Ip>203. ***. ***.117</Ip>
		    <Cps>0</Cps>
	  </PortMaxConns>
	  <RequestId>08F79110-2AF5-4FA7-998E-7C5E75EACF9C</RequestId>
</DescribePortMaxConnsResponse>
```

`JSON` format

```
{
	"PortMaxConns": [
		{
			"Port": "80",
			"Ip": "203. ***. ***.117",
			"Cps": 0
		},
		{
			"Port": "443",
			"Ip": "203. ***. ***.117",
			"Cps": 0
		}
	],
	"RequestId": "08F79110-2AF5-4FA7-998E-7C5E75EACF9C"
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/ddoscoo).

