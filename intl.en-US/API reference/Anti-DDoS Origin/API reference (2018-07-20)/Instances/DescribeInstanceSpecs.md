# DescribeInstanceSpecs

Queries the specifications of a specific Anti-DDoS Origin Enterprise instance.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=ddosbgp&api=DescribeInstanceSpecs&type=RPC&version=2018-07-20)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeInstanceSpecs|The operation that you want to perform. Set the value to **DescribeInstanceSpecs**. |
|InstanceIdList|String|Yes|\["ddosbgp-cn-n6w1r7nz\*\*\*\*"\]|The ID of the Anti-DDoS Origin Enterprise instance. This parameter value is a string consisting of JSON arrays. Each element in a JSON array indicates an instance ID. If you want to query more than one instance, separate instance IDs with commas \(,\).

**Note:** You can call the [DescribeInstanceList](~~118698~~) operation to query the IDs of all Anti-DDoS Origin Enterprise instances in a specific region. |
|RegionId|String|No|cn-hangzhou|The region ID of the Anti-DDoS Origin Enterprise instance. Default value: **cn-hangzhou**, which indicates the China \(Hangzhou\) region.

**Note:** If your instance does not reside in the China \(Hangzhou\) region, you must specify this parameter to the region ID of your instance. You can call the [DescribeRegions](~~118703~~) operation to query the regions of cloud assets that are supported by an Anti-DDoS Origin instance. |
|ResourceGroupId|String|No|rg-acfm2pz25js\*\*\*\*|The ID of the resource group to which the Anti-DDoS Origin Enterprise instance belongs in Resource Management. This parameter is empty by default, which indicates that the Anti-DDoS Origin Enterprise instance belongs to the default resource group.

For more information about resource groups, see [Create a resource group](~~94485~~). |

All Alibaba Cloud API operations must include common request parameters. For more information about common request parameters, see [Common parameters](~~118841~~).

For more information about sample requests, see the **"Examples"** section of this topic.

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|InstanceSpecs|Array of InstanceSpec| |The specifications of the Anti-DDoS Origin Enterprise instance, including whether the unlimited protection feature is enabled, and the numbers of times that the unlimited protection feature can be enabled and has been enabled. |
|AvailableDefenseTimes|Integer|2|The number of times that the unlimited protection feature can be enabled. |
|AvailableDeleteBlackholeCount|String|100|The number of times that blackhole filtering can be deactivated. |
|InstanceId|String|ddosbgp-cn-n6w1r7nz\*\*\*\*|The ID of the Anti-DDoS Origin Enterprise instance. |
|IsFullDefenseMode|Integer|1|Indicates whether the unlimited protection feature is enabled. Valid values:

-   **0**: The unlimited protection feature is disabled.
-   **1**: The unlimited protection feature is enabled. |
|PackConfig|Struct| |The configurations of the Anti-DDoS Origin Enterprise instance, including the number of protected IP addresses and protection bandwidth. |
|BindIpCount|Integer|0|The number of IP addresses that are protected by the Anti-DDoS Origin Enterprise instance. |
|IpAdvanceThre|Integer|300|The burstable bandwidth of each protected IP address. Unit: Gbit/s. |
|IpBasicThre|Integer|20|The basic bandwidth of each protected IP address. Unit: Gbit/s. |
|IpSpec|Integer|100|The number of IP addresses that can be protected by the Anti-DDoS Origin Enterprise instance. |
|NormalBandwidth|Integer|200|The normal clean bandwidth. Unit: Mbit/s. |
|PackAdvThre|Integer|300|The burstable protection bandwidth of the Anti-DDoS Origin Enterprise instance. Unit: Gbit/s. |
|PackBasicThre|Integer|20|The basic protection bandwidth of the Anti-DDoS Origin Enterprise instance. Unit: Gbit/s. |
|Region|String|cn-hangzhou|The region ID of the Anti-DDoS Origin Enterprise instance.

**Note:** You can call the [DescribeRegions](~~118703~~) operation to query the name of the region. |
|TotalDefenseTimes|Integer|2|The number of times that the unlimited protection feature can be enabled. |
|RequestId|String|5840AB9F-1419-4620-807D-5EA476090247|The ID of the request. |

## Examples

Sample requests

```
http(s)://[Endpoint]/? Action=DescribeInstanceSpecs
&InstanceIdList=[\"ddosbgp-cn-n6w1r7nz****\"]
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeInstanceSpecsResponse>
      <RequestId>5840AB9F-1419-4620-807D-5EA476090247</RequestId>
      <InstanceSpecs>
            <TotalDefenseTimes>2</TotalDefenseTimes>
            <IsFullDefenseMode>1</IsFullDefenseMode>
            <InstanceId>ddosbgp-cn-n6w1r7nz****</InstanceId>
            <AvailableDefenseTimes>2</AvailableDefenseTimes>
            <Region>cn-hangzhou</Region>
            <AvailableDeleteBlackholeCount>100</AvailableDeleteBlackholeCount>
            <PackConfig>
                  <PackAdvThre>300</PackAdvThre>
                  <IpSpec>100</IpSpec>
                  <NormalBandwidth>200</NormalBandwidth>
                  <BindIpCount>0</BindIpCount>
                  <IpAdvanceThre>300</IpAdvanceThre>
                  <PackBasicThre>20</PackBasicThre>
                  <IpBasicThre>20</IpBasicThre>
            </PackConfig>
      </InstanceSpecs>
</DescribeInstanceSpecsResponse>
```

`JSON` format

```
{
    "RequestId": "5840AB9F-1419-4620-807D-5EA476090247",
    "InstanceSpecs": [
        {
            "TotalDefenseTimes": 2,
            "IsFullDefenseMode": 1,
            "InstanceId": "ddosbgp-cn-n6w1r7nz****",
            "AvailableDefenseTimes": 2,
            "Region": "cn-hangzhou",
            "AvailableDeleteBlackholeCount": 100,
            "PackConfig": {
                "PackAdvThre": 300,
                "IpSpec": 100,
                "NormalBandwidth": 200,
                "BindIpCount": 0,
                "IpAdvanceThre": 300,
                "PackBasicThre": 20,
                "IpBasicThre": 20
            }
        }
    ]
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/ddosbgp).

