# DescribeDomainTopAttackList

Queries the peak queries per second \(QPS\) information of a website, such as the attack QPS and total QPS, within a specified period of time.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=ddoscoo&api=DescribeDomainTopAttackList&type=RPC&version=2020-01-01)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeDomainTopAttackList|The operation that you want to perform. Set the value to **DescribeDomainTopAttackList**. |
|EndTime|Long|Yes|1583683200|The end of the time range to query. This value is a UNIX timestamp representing the number of seconds that have elapsed since the epoch time January 1, 1970, 00:00:00 UTC.

 **Note:** This UNIX timestamp must indicate a time that is accurate to the minute. |
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
|AttackList|Array of Data| |The peak QPS of the website. |
|Attack|Long|0|The attack QPS. Unit: queries per second. |
|Count|Long|294|The number of all QPS, which includes normal and attack QPS. Unit: queries per second. |
|Domain|String|www.aliyun.com|The domain name of the website. |
|RequestId|String|C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E|The ID of the request. |

## Examples

Sample requests

```
http(s)://[Endpoint]/? Action=DescribeDomainTopAttackList
&EndTime=1583683200
&StartTime=1582992000
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeDomainTopAttackListResponse>
	  <RequestId>C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E</RequestId>
	  <AttackList>
		    <Count>294</Count>
		    <Attack>0</Attack>
		    <Domain>www.aliyun.com</Domain>
	  </AttackList>
</DescribeDomainTopAttackListResponse>
```

`JSON` format

```
{
    "RequestId": "C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E",
    "AttackList": [
        {
            "Count": 294,
            "Attack": 0,
            "Domain": "www.aliyun.com"
        }
    ]
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/ddoscoo).

