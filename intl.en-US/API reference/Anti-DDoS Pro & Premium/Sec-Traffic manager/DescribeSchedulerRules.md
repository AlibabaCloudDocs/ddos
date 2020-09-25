# DescribeSchedulerRules

Queries the scheduling rules that are created for Sec-Traffic Manager.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=ddoscoo&api=DescribeSchedulerRules&type=RPC&version=2020-01-01)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeSchedulerRules|The operation that you want to perform. Set the value to **DescribeSchedulerRules**. |
|PageSize|Integer|Yes|10|The number of entries to return on each page. |
|RegionId|String|No|cn-hangzhou|The region ID of the instance. Valid values:

-   **cn-hangzhou**: mainland China, which specifies an Anti-DDoS Pro instance
-   **ap-southeast-1**: outside mainland China, which specifies an Anti-DDoS Premium instance |
|ResourceGroupId|String|No|default|The ID of the resource group to which the instance belongs in Resource Management. This parameter is empty by default, which indicates that the instance belongs to the default resource group. |
|RuleName|String|No|testrule|The name of the scheduling rule. |
|PageNumber|Integer|No|1|The number of the page to return. Pages start from page **1**. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|11C55595-1757-4B17-9ACE-4ACB68C2D989|The ID of the request. |
|SchedulerRules|Array of SchedulerRule| |The information about the scheduling rule. |
|Cname|String|4eru5229a843\*\*\*\*.aliyunddos0001.com|The Canonical Name \(CNAME\) record assigned by Sec-Traffic Manager for the scheduling rule. |
|Param|Struct| |The scheduling rule for the Global Accelerator instance that interacts with Anti-DDoS Pro or Anti-DDoS Premium. |
|ParamData|Struct| |The interaction resource. |
|CloudInstanceId|String|ga-bp1htlajy5509rc99\*\*\*\*|The ID of the Global Accelerator instance. |
|ParamType|String|GA|The type of the interaction resource. Valid value: **GA**, which indicates that the Global Accelerator instance is used. |
|RuleName|String|doctest|The name of the scheduling rule. |
|RuleType|String|6|The type of the scheduling rule. Valid values:

-   **2**: tiered protection
-   **3**: network acceleration
-   **5**: CDN interaction
-   **6**: cloud service interaction |
|Rules|Array of Rule| |The information about the scheduling rules. |
|Priority|Integer|100|The priority of the scheduling rule. |
|RegionId|String|1|The region where the interaction resource that is used in the scheduling rule is deployed.

**Note:** This parameter is returned only if the **RuleType** parameter is set to **2**. |
|RestoreDelay|Integer|60|The waiting time of switching back. Unit: minutes. |
|Status|Integer|0|The status of the scheduling rule. Valid values:

-   **0**: disabled
-   **1**: enabled |
|Type|String|A|The address type of the interaction resource. Valid values:

-   **A**: IPv4 address
-   **CNAME**: CNAME record |
|Value|String|203.\*\*\*. \*\*\*.39|The address of the interaction resource. |
|ValueType|Integer|1|The address type of the interaction resource. Valid values:

-   **1**: the IP address of Anti-DDoS Pro or Anti-DDoS Premium
-   **2**: the IP address of the interaction resource \(in the tiered protection scenario\)
-   **3**: the IP address used to accelerate access \(in the network acceleration scenario\)
-   **5**: the domain name configured in CDN \(in the CDN interaction scenario\)
-   **6** the IP address of the interaction resource \(in the cloud service interaction scenario\) |
|TotalCount|String|1|The total number of returned scheduling rules. |

## Examples

Sample requests

```
http(s)://[Endpoint]/? Action=DescribeSchedulerRules
&PageSize=10
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeSchedulerRulesResponse>
          <TotalCount>1</TotalCount>
          <RequestId>11C55595-1757-4B17-9ACE-4ACB68C2D989</RequestId>
          <SchedulerRules>
                <Param>
                      <ParamData>
                            <CloudInstanceId>ga-bp1htlajy5509rc99****</CloudInstanceId>
                      </ParamData>
                      <ParamType>GA</ParamType>
                </Param>
                <RuleType>6</RuleType>
                <Cname>4eru5229a843****.aliyunddos0001.com</Cname>
                <Rules>
                      <Status>0</Status>
                      <Type>A</Type>
                      <RestoreDelay>60</RestoreDelay>
                      <ValueType>1</ValueType>
                      <Priority>100</Priority>
                      <Value>203. ***. ***.39</Value>
                      <RegionId></RegionId>
                </Rules>
                <Rules>
                      <Status>1</Status>
                      <Type>A</Type>
                      <ValueType>6</ValueType>
                      <Priority>50</Priority>
                      <Value>47. ***. ***.47</Value>
                      <RegionId>cn-hangzhou</RegionId>
                </Rules>
                <RuleName>doctest</RuleName>
          </SchedulerRules>
    </DescribeSchedulerRulesResponse>
```

`JSON` format

```
{
    "TotalCount": 1,
    "RequestId": "11C55595-1757-4B17-9ACE-4ACB68C2D989",
    "SchedulerRules": [
        {
            "Param": {
                "ParamData": {
                    "CloudInstanceId": "ga-bp1htlajy5509rc99****"
                },
                "ParamType": "GA"
            },
            "RuleType": 6,
            "Cname": "4eru5229a843****.aliyunddos0001.com",
            "Rules": [
                {
                    "Status": 0,
                    "Type": "A",
                    "RestoreDelay": 60,
                    "ValueType": 1,
                    "Priority": 100,
                    "Value": "203. ***. ***.39",
                    "RegionId": ""
                },
                {
                    "Status": 1,
                    "Type": "A",
                    "ValueType": 6,
                    "Priority": 50,
                    "Value": "47. ***. ***.47",
                    "RegionId": "cn-hangzhou"
                }
            ],
            "RuleName": "doctest"
        }
    ]
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/ddoscoo).

