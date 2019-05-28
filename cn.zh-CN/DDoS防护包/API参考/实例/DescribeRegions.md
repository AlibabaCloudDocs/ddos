# DescribeRegions {#reference_265090 .reference}

调用DescribeRegions接口查看支持DDoS防护包服务的地域信息。

**说明：** DDoS防护包的API接口目前仅对企业版DDoS防护包用户开放。

## 请求参数 {#section_0jj_pcr_rj0 .section}

|名称|类型|是否必选|描述|
|--|--|----|--|
|Action|String|是|要执行的操作，取值：DescribeRegions。|

## 返回参数 {#section_1as_cc1_hc5 .section}

|名称|类型|描述|
|--|--|--|
|RequestId|String|本次请求的ID。|
|Code|Integer|响应状态码。|
|Success|Boolean|是否成功调用请求。|
|Regions|Array|防护包支持的地域信息。|
|└RegionEnName|String|地域英文名称。|
|└RegionId|String|地域ID。|
|└RegionName|String|地域中文名称。|

## 示例 {#section_b48_y6o_uop .section}

请求示例

``` {#codeblock_60x_v7t_oqo}
https://ddosbgp.aliyuncs.com/?Action=DescribeRegions
&公共请求参数
```

正常返回示例

-   `XML`格式

    ``` {#codeblock_yok_0bb_bul}
    <?xml version='1.0' encoding='UTF-8'?>
    <DescribeRegionsResponse>
       <RequestId>C3D66E07-41BF-41B7-A4BF-83A9E08E1C09</RequestId>
       <Regions>
           <Region>
               <RegionId>cn-shenzhen</RegionId>
           </Region>
           <Region>
               <RegionId>cn-qingdao</RegionId>
           </Region>
           <Region>
               <RegionId>cn-beijing</RegionId>
           </Region>
           <Region>
               <RegionId>cn-shanghai</RegionId>
           </Region>
           <Region>
               <RegionId>cn-hongkong</RegionId>
           </Region>
           <Region>
               <RegionId>cn-huhehaote</RegionId>
           </Region>
           <Region>
               <RegionId>cn-zhangjiakou</RegionId>
           </Region>
           <Region>
               <RegionId>us-west-1</RegionId>
           </Region>
           <Region>
               <RegionId>cn-hangzhou</RegionId>
           </Region>
       </Regions>
       <Success>true</Success>
       <Code>200</Code>
    </DescribeRegionsResponse>
    ```

-   `JSON`格式

    ``` {#codeblock_ftr_37u_bst}
    {
        "RequestId": "9C48E43E-58A6-4A08-A858-4C9BB9631870",
        "Regions": [
        {
            "RegionId": "cn-shenzhen"
        },
        {
            "RegionId": "cn-qingdao"
        },
        {
            "RegionId": "cn-beijing"
        },
        {
            "RegionId": "cn-shanghai"
        },
        {
            "RegionId": "cn-hongkong"
        },
        {
            "RegionId": "cn-huhehaote"
        },
        {
            "RegionId": "cn-zhangjiakou"
        },
        {
            "RegionId": "us-west-1"
        },
        {
            "RegionId": "cn-hangzhou"
        }
        ],
        "Success": true,
        "Code": "200"
    }
    ```


