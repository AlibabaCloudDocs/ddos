# DescribeDomainQPSList

Queries the statistics on the queries per second \(QPS\) of a website.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=ddoscoo&api=DescribeDomainQPSList&type=RPC&version=2020-01-01)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeDomainQPSList|The operation that you want to perform. Set the value to **DescribeDomainQPSList**. |
|EndTime|Long|Yes|1583683200|The end of the time range to query. This value is a UNIX timestamp representing the number of seconds that have elapsed since the epoch time January 1, 1970, 00:00:00 UTC.

 **Note:** This UNIX timestamp must indicate a time that is accurate to the minute. |
|Interval|Long|Yes|1000|The intervals for returning statistics. Unit: seconds. |
|StartTime|Long|Yes|1582992000|The beginning of the time range to query. This value is a UNIX timestamp representing the number of seconds that have elapsed since the epoch time January 1, 1970, 00:00:00 UTC.

 **Note:** This UNIX timestamp must indicate a time that is accurate to the minute. |
|ResourceGroupId|String|No|default|The ID of the resource group to which the instance belongs in Resource Management. This parameter is empty by default, which indicates that the instance belongs to the default resource group. |
|RegionId|String|No|cn-hangzhou|The region ID of the instance. Valid values:

 -   **cn-hangzhou**: mainland China, which indicates an Anti-DDoS Pro instance
-   **ap-southeast-1**: outside mainland China, which indicates an Anti-DDoS Premium instance |
|Domain|String|No|www.aliyun.com|The domain name of the website. If you do not specify this parameter, the statistics on the QPS of all domain names are queried.

 **Note:** A forwarding rule must be configured for the domain name. You can call the [DescribeDomains](~~91724~~) operation to query all domain names. |

All Alibaba Cloud API operations must include common request parameters. For more information about common request parameters, see [Common parameters](~~157269~~).

For more information about sample requests, see the **"Examples"** section of this topic.

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|DomainQPSList|Array of DomainQPS| |The statistics on the QPS of the website. |
|AttackQps|Long|1|The attack QPS. |
|CacheHits|Long|0|The number of cache hits. |
|Index|Long|0|The index number of the returned data. |
|MaxAttackQps|Long|37|The peak attack QPS. |
|MaxNormalQps|Long|93|The peak of normal QPS. |
|MaxQps|Long|130|The peak of total QPS. |
|Time|Long|1582992000|The time when the statistic was recorded. This value is a UNIX timestamp representing the number of seconds that have elapsed since the epoch time January 1, 1970, 00:00:00 UTC. |
|TotalCount|Long|20008|The total number of queries. |
|TotalQps|Long|1|The total number of QPS. |
|RequestId|String|327F2ABB-104D-437A-AAB5-D633E29A8C51|The ID of the request. |

## Examples

Sample requests

```
http(s)://[Endpoint]/? Action=DescribeDomainQPSList
&Interval=1000
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeDomainQPSListResponse>
	  <DomainQPSList>
		    <MaxAttackQps>37</MaxAttackQps>
		    <TotalQps>1</TotalQps>
		    <TotalCount>20008</TotalCount>
		    <MaxQps>130</MaxQps>
		    <MaxNormalQps>93</MaxNormalQps>
		    <AttackQps>1</AttackQps>
		    <Index>0</Index>
		    <Time>1582992000</Time>
		    <CacheHits>0</CacheHits>
	  </DomainQPSList>
	  <RequestId>327F2ABB-104D-437A-AAB5-D633E29A8C51</RequestId>
</DescribeDomainQPSListResponse>
```

`JSON` format

```
{
	"DomainQPSList": [
		{
			"MaxAttackQps": 37,
			"TotalQps": 1,
			"TotalCount": 20008,
			"MaxQps": 130,
			"MaxNormalQps": 93,
			"AttackQps": 1,
			"Index": 0,
			"Time": 1582992000,
			"CacheHits": 0
		}
	],
	"RequestId": "327F2ABB-104D-437A-AAB5-D633E29A8C51"
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/ddoscoo).

