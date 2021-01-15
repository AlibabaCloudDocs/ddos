# DescribeRegions

Queries the regions of cloud assets that are supported by an Anti-DDoS Origin instance.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=ddosbgp&api=DescribeRegions&type=RPC&version=2018-07-20)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeRegions|The operation that you want to perform. Set the value to **DescribeRegions**. |
|ResourceGroupId|String|No|rg-acfm2pz25js\*\*\*\*|The ID of the resource group to which the Anti-DDoS Origin instance belongs in Resource Management. This parameter is empty by default, which indicates that the instance belongs to the default resource group.

For more information about resource groups, see [Create a resource group](~~94485~~). |
|RegionId|String|No|cn-hangzhou|The region ID to query. The default value is **cn-hangzhou**, which indicates that the regions of cloud assets that are supported by an Anti-DDoS Origin instance in the China \(Hangzhou\) region are queried.

For more information about the IDs of other regions, see [Regions and zones](~~40654~~)****. |

All Alibaba Cloud API operations must include common request parameters. For more information about common request parameters, see [Common parameters](~~118841~~).

For more information about sample requests, see the **"Examples"** section of this topic.

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Code|String|200|The HTTP status code. |
|Regions|Array of Region| |The information about regions of the cloud assets that are supported by the Anti-DDoS Origin instance. The information includes region IDs and names. |
|RegionEnName|String|China \(Hangzhou\)|The English name of the region where the cloud assets reside. |
|RegionId|String|cn-hangzhou|The ID of the region. |
|RegionName|String|China \(Hangzhou\)|The name of the region where the cloud assets reside. |
|RequestId|String|F7CA8B4E-FB15-4336-A351-8DC29D66EA82|The ID of the request. |
|Success|Boolean|true|Indicates whether the request is successful. Valid values:

-   **true**: The request is successful.
-   **false**: The request failed. |

## Examples

Sample requests

```
http(s)://[Endpoint]/? Action=DescribeRegions
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeRegionsResponse>
      <RequestId>F7CA8B4E-FB15-4336-A351-8DC29D66EA82</RequestId>
      <Regions>
            <RegionName>Russia (Moscow)</RegionName>
            <RegionEnName>Russia (Moscow)</RegionEnName>
            <RegionId>rus-west-1</RegionId>
      </Regions>
      <Regions>
            <RegionName>China (Beijing)</RegionName>
            <RegionEnName>China (Beijing)</RegionEnName>
            <RegionId>cn-beijing</RegionId>
      </Regions>
      <Regions>
            <RegionName>China (Ulanqab)</RegionName>
            <RegionEnName>China (Ulanqab)</RegionEnName>
            <RegionId>cn-wulanchabu</RegionId>
      </Regions>
      <Regions>
            <RegionName>India (Mumbai)</RegionName>
            <RegionEnName>India (Mumbai)</RegionEnName>
            <RegionId>ap-south-1</RegionId>
      </Regions>
      <Regions>
            <RegionName>China (Qingdao)</RegionName>
            <RegionEnName>China (Qingdao)</RegionEnName>
            <RegionId>cn-qingdao</RegionId>
      </Regions>
      <Regions>
            <RegionName>China (Shanghai)</RegionName>
            <RegionEnName>China (Shanghai)</RegionEnName>
            <RegionId>cn-shanghai</RegionId>
      </Regions>
      <Regions>
            <RegionName>China (Hong Kong)</RegionName>
            <RegionEnName>China (Hong Kong)</RegionEnName>
            <RegionId>cn-hongkong</RegionId>
      </Regions>
      <Regions>
            <RegionName>China (Heyuan)</RegionName>
            <RegionEnName>China (Heyuan)</RegionEnName>
            <RegionId>cn-heyuan</RegionId>
      </Regions>
      <Regions>
            <RegionName>Germany (Frankfurt)</RegionName>
            <RegionEnName>Germany (Frankfurt)</RegionEnName>
            <RegionId>eu-central-1</RegionId>
      </Regions>
      <Regions>
            <RegionName>China (Zhangjiakou)</RegionName>
            <RegionEnName>China (Zhangjiakou)</RegionEnName>
            <RegionId>cn-zhangjiakou</RegionId>
      </Regions>
      <Regions>
            <RegionName>US (Silicon Valley)</RegionName>
            <RegionEnName>US (Silicon Valley)</RegionEnName>
            <RegionId>us-west-1</RegionId>
      </Regions>
      <Regions>
            <RegionName>China (Shenzhen)</RegionName>
            <RegionEnName>China (Shenzhen)</RegionEnName>
            <RegionId>cn-shenzhen</RegionId>
      </Regions>
      <Regions>
            <RegionName>UK (London)</RegionName>
            <RegionEnName>UK (London)</RegionEnName>
            <RegionId>eu-west-1</RegionId>
      </Regions>
      <Regions>
            <RegionName>Japan (Tokyo)</RegionName>
            <RegionEnName>Japan (Tokyo)</RegionEnName>
            <RegionId>ap-northeast-1</RegionId>
      </Regions>
      <Regions>
            <RegionName>UAE (Dubai)</RegionName>
            <RegionEnName>UAE (Dubai)</RegionEnName>
            <RegionId>me-east-1</RegionId>
      </Regions>
      <Regions>
            <RegionName>China (Chengdu)</RegionName>
            <RegionEnName>China (Chengdu)</RegionEnName>
            <RegionId>cn-chengdu</RegionId>
      </Regions>
      <Regions>
            <RegionName>China (Guangzhou)</RegionName>
            <RegionEnName>China (Guangzhou)</RegionEnName>
            <RegionId>cn-guangzhou</RegionId>
      </Regions>
      <Regions>
            <RegionName>Singapore (Singapore)</RegionName>
            <RegionEnName>Singapore</RegionEnName>
            <RegionId>ap-southeast-1</RegionId>
      </Regions>
      <Regions>
            <RegionName>Australia (Sydney)</RegionName>
            <RegionEnName>Australia (Sydney)</RegionEnName>
            <RegionId>ap-southeast-2</RegionId>
      </Regions>
      <Regions>
            <RegionName>Malaysia (Kuala Lumpur)</RegionName>
            <RegionEnName>Malaysia (Kuala Lumpur)</RegionEnName>
            <RegionId>ap-southeast-3</RegionId>
      </Regions>
      <Regions>
            <RegionName>China (Hohhot)</RegionName>
            <RegionEnName>China (Hohhot)</RegionEnName>
            <RegionId>cn-huhehaote</RegionId>
      </Regions>
      <Regions>
            <RegionName>Indonesia (Jakarta)</RegionName>
            <RegionEnName>Indonesia (Jakarta)</RegionEnName>
            <RegionId>ap-southeast-5</RegionId>
      </Regions>
      <Regions>
            <RegionName>US (Virginia)</RegionName>
            <RegionEnName>US (Virginia)</RegionEnName>
            <RegionId>us-east-1</RegionId>
      </Regions>
      <Regions>
            <RegionName>China (Hangzhou)</RegionName>
            <RegionEnName>China (Hangzhou)</RegionEnName>
            <RegionId>cn-hangzhou</RegionId>
      </Regions>
      <Code>200</Code>
      <Success>true</Success>
</DescribeRegionsResponse>
```

`JSON` format

```
{
    "RequestId": "F7CA8B4E-FB15-4336-A351-8DC29D66EA82",
    "Regions": [
        {
            "RegionName": "Russia (Moscow)",
            "RegionEnName": "Russia (Moscow)",
            "RegionId": "rus-west-1"
        },
        {
            "RegionName": "China (Beijing)",
            "RegionEnName": "China (Beijing)",
            "RegionId": "cn-beijing"
        },
        {
            "RegionName": "China (Ulanqab)",
            "RegionEnName": "China (Ulanqab)",
            "RegionId": "cn-wulanchabu"
        },
        {
            "RegionName": "India (Mumbai)",
            "RegionEnName": "India (Mumbai)",
            "RegionId": "ap-south-1"
        },
        {
            "RegionName": "China (Qingdao)",
            "RegionEnName": "China (Qingdao)",
            "RegionId": "cn-qingdao"
        },
        {
            "RegionName": "China (Shanghai)",
            "RegionEnName": "China (Shanghai)",
            "RegionId": "cn-shanghai"
        },
        {
            "RegionName": "China (Hong Kong)",
            "RegionEnName": "China (Hong Kong)",
            "RegionId": "cn-hongkong"
        },
        {
            "RegionName": "China (Heyuan)",
            "RegionEnName": "China (Heyuan)",
            "RegionId": "cn-heyuan"
        },
        {
            "RegionName": "Germany (Frankfurt)",
            "RegionEnName": "Germany (Frankfurt)",
            "RegionId": "eu-central-1"
        },
        {
            "RegionName": "China (Zhangjiakou)",
            "RegionEnName": "China (Zhangjiakou)",
            "RegionId": "cn-zhangjiakou"
        },
        {
            "RegionName": "US (Silicon Valley)",
            "RegionEnName": "US (Silicon Valley)",
            "RegionId": "us-west-1"
        },
        {
            "RegionName": "China (Shenzhen)",
            "RegionEnName": "China (Shenzhen)",
            "RegionId": "cn-shenzhen"
        },
        {
            "RegionName": "UK (London)",
            "RegionEnName": "UK (London)",
            "RegionId": "eu-west-1"
        },
        {
            "RegionName": "Japan (Tokyo)",
            "RegionEnName": "Japan (Tokyo)",
            "RegionId": "ap-northeast-1"
        },
        {
            "RegionName": "UAE (Dubai)",
            "RegionEnName": "UAE (Dubai)",
            "RegionId": "me-east-1"
        },
        {
            "RegionName": "China (Chengdu)",
            "RegionEnName": "China (Chengdu)",
            "RegionId": "cn-chengdu"
        },
        {
            "RegionName": "China (Guangzhou)",
            "RegionEnName": "China (Guangzhou)",
            "RegionId": "cn-guangzhou"
        },
        {
            "RegionName": "Singapore (Singapore)",
            "RegionEnName": "Singapore",
            "RegionId": "ap-southeast-1"
        },
        {
            "RegionName": "Australia (Sydney)",
            "RegionEnName": "Australia (Sydney)",
            "RegionId": "ap-southeast-2"
        },
        {
            "RegionName": "Malaysia (Kuala Lumpur)",
            "RegionEnName": "Malaysia (Kuala Lumpur)",
            "RegionId": "ap-southeast-3"
        },
        {
            "RegionName": "China (Hohhot)",
            "RegionEnName": "China (Hohhot)",
            "RegionId": "cn-huhehaote"
        },
        {
            "RegionName": "Indonesia (Jakarta)",
            "RegionEnName": "Indonesia (Jakarta)",
            "RegionId": "ap-southeast-5"
        },
        {
            "RegionName": "US (Virginia)",
            "RegionEnName": "US (Virginia)",
            "RegionId": "us-east-1"
        },
        {
            "RegionName": "China (Hangzhou)",
            "RegionEnName": "China (Hangzhou)",
            "RegionId": "cn-hangzhou"
        }
    ],
    "Code": "200",
    "Success": true
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/ddosbgp).

