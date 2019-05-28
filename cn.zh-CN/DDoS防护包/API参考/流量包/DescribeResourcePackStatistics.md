# DescribeResourcePackStatistics {#reference_265093 .reference}

调用DescribeResourcePackStatistics接口查询抗D流量包的统计信息。

**说明：** DDoS防护包的API接口目前仅对企业版DDoS防护包用户开放。

## 请求参数 {#section_0jj_pcr_rj0 .section}

|名称|类型|是否必选|描述|
|--|--|----|--|
|Action|String|是|要执行的操作，取值：DescribeResourcePackStatistics。|
|InstanceId|String|否|要查询的防护包实例ID。|

## 返回参数 {#section_1as_cc1_hc5 .section}

|名称|类型|描述|
|--|--|--|
|RequestId|String|本次请求的ID。|
|AvailablePackNum|Integer|可用流量包数量。|
|TotalCurrCapacity|Long|总可用防护流量，单位为Byte。|
|TotalInitCapacity|Long|总初始防护流量，单位为Byte。|
|TotalUsedCapacity|Long|总消耗防护流量，单位为Byte。|

## 示例 {#section_b48_y6o_uop .section}

请求示例

``` {#codeblock_60x_v7t_oqo}
https://ddosbgp.aliyuncs.com/?Action=DescribeResourcePackStatistics
&InstanceId=ddosbgp-cn-x1
&公共请求参数
```

正常返回示例

-   `XML`格式

    ``` {#codeblock_yok_0bb_bul}
    <?xml version='1.0' encoding='UTF-8'?>
    <DescribeResourcePackStatisticsResponse>
       <TotalInitCapacity>427000000000000</TotalInitCapacity>
       <TotalUsedCapacity>5285439000000</TotalUsedCapacity>
       <TotalCurrCapacity>20831250000000</TotalCurrCapacity>
       <RequestId>B347DC57-F746-44B5-A2A1-B331A6655E96</RequestId>
       <AvailablePackNum>8</AvailablePackNum>
    </DescribeResourcePackStatisticsResponse>
    ```

-   `JSON`格式

    ``` {#codeblock_ftr_37u_bst}
    {
     "TotalInitCapacity": 427000000000000,
     "TotalUsedCapacity": 5285439000000,
     "TotalCurrCapacity": 20831250000000,
     "RequestId": "A2D6D5FB-FA07-41A8-B093-A2B7B26E72F2",
     "AvailablePackNum": 8
    }
    ```


