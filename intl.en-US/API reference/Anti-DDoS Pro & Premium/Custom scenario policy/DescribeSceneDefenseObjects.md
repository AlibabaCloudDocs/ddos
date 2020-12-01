# DescribeSceneDefenseObjects

Queries the protected asset of a custom mitigation policy.

For more information, see [Create custom mitigation policies for specific scenarios](~~148079~~).

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=ddoscoo&api=DescribeSceneDefenseObjects&type=RPC&version=2020-01-01)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeSceneDefenseObjects|The operation that you want to perform. Set the value to **DescribeSceneDefenseObjects**. |
|PolicyId|String|Yes|47e07ebd-0ba5-4afc-957b-59d15b90\*\*\*\*|The ID of the policy that you want to query.

 **Note:** You can call the [DescribeSceneDefensePolicies](~~159382~~) operation to query the IDs of all policies. |
|RegionId|String|No|cn-hangzhou|The ID of the region where your Anti-DDoS Pro or Anti-DDoS Premium instance resides. Valid values:

 -   **cn-hangzhou**: mainland China, which indicates an Anti-DDoS Pro instance
-   **ap-southeast-1**: outside mainland China, which indicates an Anti-DDoS Premium instance |
|ResourceGroupId|String|No|rg-acfm2pz25js\*\*\*\*|The ID of the resource group to which the instance belongs in Resource Management. This parameter is empty by default, which indicates that the instance belongs to the default resource group. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Objects|Array of Object| |The information about the protected assets. |
|Domain|String|\*\*\*.aliyun.com|The domain name protected by the policy. |
|PolicyId|String|47e07ebd-0ba5-4afc-957b-59d15b90\*\*\*\*|The ID of the policy. |
|Vip|String|203.\*\*\*. \*\*\*.119|The IP address of the Anti-DDoS Pro or Anti-DDoS Premium instance that is protected by this policy. |
|RequestId|String|FE07E73F-F19E-4A51-B62F-AC59E3B962D8|The ID of the request. |
|Success|Boolean|true|Indicates whether the request is successful. Valid values:

 -   **true:** The request is successful.
-   **false**: The request fails. |

## Examples

Sample requests

```
http(s)://[Endpoint]/? Action=DescribeSceneDefenseObjects
&PolicyId=47e07ebd-0ba5-4afc-957b-59d15b90****
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeSceneDefenseObjectsResponse>
	  <RequestId>FE07E73F-F19E-4A51-B62F-AC59E3B962D8</RequestId>
	  <Objects>
		    <Domain>***.aliyun.com</Domain>
		    <PolicyId>47e07ebd-0ba5-4afc-957b-59d15b90****</PolicyId>
	  </Objects>
	  <Objects>
		    <Vip>203. ***. ***.119</Vip>
		    <PolicyId>47e07ebd-0ba5-4afc-957b-59d15b90****</PolicyId>
	  </Objects>
	  <Success>true</Success>
</DescribeSceneDefenseObjectsResponse>
```

`JSON` format

```
{
	"RequestId": "FE07E73F-F19E-4A51-B62F-AC59E3B962D8",
	"Objects": [
		{
			"Domain": "***.aliyun.com",
			"PolicyId": "47e07ebd-0ba5-4afc-957b-59d15b90****"
		},
		{
			"Vip": "203. ***. ***.119",
			"PolicyId": "47e07ebd-0ba5-4afc-957b-59d15b90****"
		}
	],
	"Success": true
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/ddoscoo).

