# DescribeDomainQpsWithCache

Queries the queries per second \(QPS\) information of a website, such as the total QPS, QPS blocked by different protection policies, and cache hit ratio.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=ddoscoo&api=DescribeDomainQpsWithCache&type=RPC&version=2020-01-01)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeDomainQpsWithCache|The operation that you want to perform. Set the value to **DescribeDomainQpsWithCache**. |
|EndTime|Long|Yes|1583683200|The end of the time range to query. This value is a UNIX timestamp representing the number of seconds that have elapsed since the epoch time January 1, 1970, 00:00:00 UTC.

 **Note:** This UNIX timestamp must indicate a time that is accurate to the minute. |
|StartTime|Long|Yes|1582992000|The beginning of the time range to query. This value is a UNIX timestamp representing the number of seconds that have elapsed since the epoch time January 1, 1970, 00:00:00 UTC.

 **Note:** This UNIX timestamp must indicate a time that is accurate to the minute. |
|RegionId|String|No|cn-hangzhou|The region ID of the instance. Valid values:

 -   **cn-hangzhou**: mainland China, which indicates an Anti-DDoS Pro instance
-   **ap-southeast-1**: outside mainland China, which indicates an Anti-DDoS Premium instance |
|ResourceGroupId|String|No|default|The ID of the resource group to which the instance belongs in Resource Management. This parameter is empty by default, which indicates that the instance belongs to the default resource group. |
|Domain|String|No|www.aliyun.com|The domain name of the website.

 **Note:** A forwarding rule must be configured for the domain name. You can call the [DescribeDomains](~~91724~~) operation to query all domain names. |

All Alibaba Cloud API operations must include common request parameters. For more information about common request parameters, see [Common parameters](~~157269~~).

For more information about sample requests, see the **"Examples"** section of this topic.

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Blocks|List|\[20,30,20\]|The attack QPS. |
|CacheHits|List|\[0.3,0.4,0.5\]|The cache hit ratios. This parameter is decimals. For example, 0.5 indicates that the cache hit ratio is 50%. |
|CcBlockQps|List|\[1,0,0\]|Details about the QPS blocked by the Frequency Control policy. |
|CcJsQps|List|\[1,0,0\]|Details about the QPS for which the Frequency Control policy triggers Completely Automated Public Turing test to tell Computers and Humans Apart \(CAPTCHA\). |
|Interval|Integer|20384|The intervals between every two adjacent records. Unit: seconds. |
|IpBlockQps|List|\[1,0,0\]|Details about the QPS blocked by the blacklist for domain names. |
|PreciseBlocks|List|\[1,0,0\]|Details about the QPS blocked by the Accurate Access Control policy. |
|PreciseJsQps|List|\[1,0,0\]|Details about the QPS for which the Accurate Access Control policy triggers the JavaScript challenge. |
|RegionBlocks|List|\[1,0,0\]|Details about the QPS blocked by the Blocked Regions policy. |
|RequestId|String|0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc|The ID of the request. |
|StartTime|Long|1582992000|The start time of the query. This value is a UNIX timestamp representing the number of seconds that have elapsed since the epoch time January 1, 1970, 00:00:00 UTC. |
|Totals|List|\[100,400,200\]|The total numbers of returned QPS. |

## Examples

Sample requests

```
http(s)://[Endpoint]/? Action=DescribeDomainQpsWithCache
&EndTime=1583683200
&StartTime=1582992000
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeDomainQpsWithCacheResponse>
	  <Interval>20384</Interval>
	  <StartTime>1582992000</StartTime>
	  <Totals>100</Totals>
	  <Totals>400</Totals>
	  <Totals>200</Totals>
	  <Blocks>20</Blocks>
	  <Blocks>30</Blocks>
	  <Blocks>20</Blocks>
	  <CacheHits>0.3</CacheHits>
	  <CacheHits>0.4</CacheHits>
	  <CacheHits>0.5</CacheHits>
	  <CcBlockQps>1</CcBlockQps>
	  <CcBlockQps>0</CcBlockQps>
	  <CcBlockQps>0</CcBlockQps>
	  <CcJsQps>1</CcJsQps>
	  <CcJsQps>0</CcJsQps>
	  <CcJsQps>0</CcJsQps>
	  <IpBlockQps>1</IpBlockQps>
	  <IpBlockQps>0</IpBlockQps>
	  <IpBlockQps>0</IpBlockQps>
	  <PreciseBlocks>1</PreciseBlocks>
	  <PreciseBlocks>0</PreciseBlocks>
	  <PreciseBlocks>0</PreciseBlocks>
	  <PreciseJsQps>1</PreciseJsQps>
	  <PreciseJsQps>0</PreciseJsQps>
	  <PreciseJsQps>0</PreciseJsQps>
	  <RegionBlocks>1</RegionBlocks>
	  <RegionBlocks>0</RegionBlocks>
	  <RegionBlocks>0</RegionBlocks>
	  <RequestId>0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc</RequestId>
</DescribeDomainQpsWithCacheResponse>
```

`JSON` format

```
{
    "Interval": 20384,
    "StartTime": 1582992000,
    "Totals": [
        100,
        400,
        200
    ],
    "Blocks": [
        20,
        30,
        20
    ],
    "CacheHits": [
        0.3,
        0.4,
        0.5
    ],
    "CcBlockQps": [
        1,
        0,
        0
    ],
    "CcJsQps": [
        1,
        0,
        0
    ],
    "IpBlockQps": [
        1,
        0,
        0
    ],
    "PreciseBlocks": [
        1,
        0,
        0
    ],
    "PreciseJsQps": [
        1,
        0,
        0
    ],
    "RegionBlocks": [
        1,
        0,
        0
    ],
    "RequestId": "0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc"
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/ddoscoo).

