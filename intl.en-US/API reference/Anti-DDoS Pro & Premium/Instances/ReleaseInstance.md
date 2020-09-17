# ReleaseInstance

Releases an expired Anti-DDoS Pro or Anti-DDoS Premium instance.

If an Anti-DDoS Pro or Anti-DDoS Premium instance expires, DDoS mitigation stops. The instance stops forwarding traffic seven days after it expires.

-   We recommend that you renew your instance before it expires. This eliminates the impacts on service protection and traffic forwarding. You can call the [DescribeInstances](~~91478~~) operation to query the expiration time of all instances. If you want to renew your instance, log on to the [Anti-DDoS Pro console](https://yundun.console.aliyun.com/?p=ddoscoo).
-   If you do not plan to renew your instance, switch the service traffic back to the origin sever before your instance expires. To switch the traffic back, change the service IP address to the IP address of the origin server or modify the CNAME record to stop forwarding service traffic to Anti-DDoS Pro or Anti-DDoS Premium. This avoid service interruptions caused by the expiration.

You can call this operation to release a specific instance after the instance expires.

**Note:** Before you release a specific instance, make sure that the service traffic is switched to the origin server.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer automatically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=ddoscoo&api=ReleaseInstance&type=RPC&version=2020-01-01)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|ReleaseInstance|The operation that you want to perform. Set the value to **ReleaseInstance**. |
|RegionId|String|No|cn-hangzhou|The region ID of the instance. Valid values:

-   **cn-hangzhou**: mainland China, which indicates an Anti-DDoS Pro instance
-   **ap-southeast-1**: outside mainland China, which indicates an Anti-DDoS Premium instance |
|InstanceId|String|No|ddoscoo-cn-mp91j1ao\*\*\*\*|The ID of the instance that you want to release.

**Note:** You can release only expired instances. You can call the [DescribeInstances](~~91478~~) operation to query the IDs and expiration status of all instances. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc|The ID of the request. |

## Examples

Sample requests

```
http(s)://[Endpoint]/?Action=ReleaseInstance
&InstanceId=ddoscoo-cn-mp91j1ao****
&RegionId=cn-hangzhou
&<Common request parameters>
```

Sample success responses

`XML` format

```
<ReleaseInstanceResponse>
      <RequestId>0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc</RequestId>
</ReleaseInstanceResponse>
```

`JSON` format

```
{
  "RequestId": "0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc"
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/ddoscoo).

