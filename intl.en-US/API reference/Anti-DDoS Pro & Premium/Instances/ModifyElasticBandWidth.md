# ModifyElasticBandWidth

Modifies the burstable protection bandwidth of an Anti-DDoS Pro instance.

**Note:** This API operation is suitable only for Anti-DDoS Pro.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=ddoscoo&api=ModifyElasticBandWidth&type=RPC&version=2020-01-01)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|ModifyElasticBandWidth|The operation that you want to perform. Set the value to **ModifyElasticBandWidth**. |
|ElasticBandwidth|Integer|Yes|50|The burstable protection bandwidth that you want to modify. Unit: Gbit/s.

**Note:** You can call the [DescribeElasticBandwidthSpec](~~91502~~) operation to query the available burstable protection bandwidth of the Anti-DDoS Pro instance. |
|InstanceId|String|Yes|ddoscoo-cn-mp91j1ao\*\*\*\*|The ID of the instance.

**Note:** The instance must be in the normal status. You can call the [DescribeInstanceIds](~~157459~~) operation to query the IDs of all instances. |
|RegionId|String|No|cn-hangzhou|The region ID of the instance. Set the value to **cn-hangzhou**, which indicates an Anti-DDoS Pro instance. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc|The ID of the request. |

## Examples

Sample requests

```
http(s)://[Endpoint]/? Action=ModifyElasticBandWidth
&ElasticBandwidth=50
&InstanceId=ddoscoo-cn-mp91j1ao****
&<Common request parameters>
```

Sample success responses

`XML` format

```
<ModifyElasticBandWidthResponse>
      <RequestId>0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc</RequestId>
</ModifyElasticBandWidthResponse>
```

`JSON` format

```
{
    "RequestId": "0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc"
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/ddoscoo).

