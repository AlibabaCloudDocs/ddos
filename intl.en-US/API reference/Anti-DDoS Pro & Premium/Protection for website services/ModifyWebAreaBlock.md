# ModifyWebAreaBlock

Modifies the blocked regions that are configured in the Blocked Regions \(Domain Names\) policy for a website.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer automatically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=ddoscoo&api=ModifyWebAreaBlock&type=RPC&version=2020-01-01)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|ModifyWebAreaBlock|The operation that you want to perform. Set the value to **ModifyWebAreaBlock**. |
|Domain|String|Yes|www.aliyun.com|The domain name.

**Note:** A forwarding rule must be configured for the domain name. You can call the [DescribeDomains](~~91724~~) operation to query all domain names. |
|RegionId|String|No|cn-hangzhou|The region ID of the Anti-DDos Pro or Anti-DDos Premium instance. Valid values:

-   **cn-hangzhou**: mainland China, which indicates an Anti-DDoS Pro instance
-   **ap-southeast-1**: outside mainland China, which indicates an Anti-DDoS Premium instance |
|ResourceGroupId|String|No|default|The ID of the resource group to which the instance belongs in Resource Management. This parameter is empty by default, which indicates that the instance belongs to the default resource group. |
|Regions.N|RepeatList|No|CN-SHANGHAI|The name of region N to block. If you do not specify this parameter, the Blocked Regions \(Domain Names\) policy is disabled. Valid values:

China

-   **CN-SHANGHAI**: Shanghai
-   **CN-YUNNAN**: Yunnan
-   **CN-INNERMONGOLIA**: Nei Mongol
-   **CN-BEIJING**: Beijing
-   **CN-TAIWAN**: Taiwan
-   **CN-JILIN**: Jilin
-   **CN-SICHUAN**: Sichuan
-   **CN-TIANJIN**: Tianjin
-   **CN-NINGXIA**: Ningxia
-   **CN-ANHUI**: Anhui
-   **CN-SHANDONG**: Shandong
-   **CN-SHAANXI**: Shaanxi
-   **CN-SHANXI**: Shanxi
-   **CN-GUANGDONG**: Guangdong
-   **CN-GUANGXI**: Guangxi
-   **CN-JIANGSU**: Jiangsu
-   **CN-JIANGXI**: Jiangxi
-   **CN-HEBEI**: Hebei
-   **CN-HENAN**: Henan
-   **CN-ZHEJIANG**: Zhejiang
-   **CN-HAINAN**: Hainan
-   **CN-HUBEI**: Hubei
-   **CN-HUNAN**: Hunan
-   **CN-MACAU**: Macao
-   **CN-GANSU**: Gansu
-   **CN-FUJIAN**: Fujian
-   **CN-GUIZHOU**: Guizhou
-   **CN-LIAONING**: Liaoning
-   **CN-CHONGQING**: Chongqing
-   **CN-QINGHAI**: Qinghai
-   **CN-HONGKONG**: Hong Kong S.A.R
-   **CN-HEILONGJIANG**: Heilong Jiang

Outside China

-   **OVERSEAS-ASIA**: Asia \(except China\)
-   **OVERSEAS-EUROPE**: Europe
-   **OVERSEAS-NAMERICA**: North America
-   **OVERSEAS-SAMERICA**: South America
-   **OVERSEAS-AFRICA**: Africa
-   **OVERSEAS-OCEANIA**: Oceania
-   **OVERSEAS-ANTARCTICA**: Antarctica |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc|The ID of the request. |

## Examples

Sample request

```
http(s)://[Endpoint]/?Action=ModifyWebAreaBlock
&Domain=www.aliyun.com
&Regions.1=CN-SHANGHAI
&<Common request parameters>
```

Sample success responses

`XML` format

```
<ModifyWebAreaBlockResponse>
        <RequestId>0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc</RequestId>
</ModifyWebAreaBlockResponse>
```

`JSON` format

```
{
    "RequestId": "0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc"
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/ddoscoo).

