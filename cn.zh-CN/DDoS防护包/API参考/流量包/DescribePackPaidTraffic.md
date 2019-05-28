# DescribePackPaidTraffic {#reference_265089 .reference}

调用DescribePackPaidTraffic接口查询付费流量明细。

**说明：** DDoS防护包的API接口目前仅对企业版DDoS防护包用户开放。

## 请求参数 {#section_0jj_pcr_rj0 .section}

|名称|类型|是否必选|描述|
|--|--|----|--|
|Action|String|是|要执行的操作，取值：DescribePackPaidTraffic。|
|CurrentPage|Integer|是|列表的页码，默认值为1。|
|PageSize|Integer|是|分页查询时每页的行数，最大值为50，默认值为10。|
|StartTime|Long|是|查询开始时间，秒级时间戳。所设置的查询时间区间不能超过30天。|
|EndTime|Long|是|查询结束时间，秒级时间戳。所设置的查询时间区间不能超过30天。|
|InstanceId|String|否|要查询的防护包实例ID。|

## 返回参数 {#section_1as_cc1_hc5 .section}

|名称|类型|描述|
|--|--|--|
|RequestId|String|本次请求的ID。|
|TotalCount|Integer|返回结果的数量。|
|PackPaidTraffics|Array|付费流量明细。|
|└BaseBandwidth|Integer|基础防护带宽，单位为Gb。|
|└ElasticBandwidth|Integer|弹性防护带宽，单位为Gb。|
|└InstanceId|String|防护包实例ID。|
|└MaxAttack|Float|攻击流量峰值，单位为Gbps。|
|└PaidCapacity|Float|付费流量大小，单位为Gb。|
|└StartTime|Long|统计时间。|
|└TotalCapacity|Float|总防护流量，单位为Gb。|

## 示例 {#section_b48_y6o_uop .section}

请求示例

``` {#codeblock_60x_v7t_oqo}
https://ddosbgp.aliyuncs.com/?Action=DescribePackPaidTraffic
&InstanceId=ddosbgp-cn-x1
&CurrentPage=1
&PageSize=10
&StartTime=1557303537870
EndTime=1557908337870
&公共请求参数
```

正常返回示例

-   `XML`格式

    ``` {#codeblock_yok_0bb_bul}
    <?xml version='1.0' encoding='UTF-8'?>
    <DescribePackPaidTrafficResponse>
       <TotalCount>1</TotalCount>
       <RequestId>9E0574A3-DB50-4A4D-B9A2-C5DA61987C5F</RequestId>
       <PackPaidTraffics>
           <PackPaidTraffic>
               <PaidCapacity>615.166</PaidCapacity>
               <MaxAttack>49.998</MaxAttack>
               <InstanceId>ddosbgp-cn-x1</InstanceId>
               <TotalCapacity>1302.666</TotalCapacity>
               <ElasticBandwidth>100</ElasticBandwidth>
               <BaseBandwidth>20</BaseBandwidth>
               <StartTime>1557809400000</StartTime>
           </PackPaidTraffic>
       </PackPaidTraffics>
    </DescribePackPaidTrafficResponse>
    ```

-   `JSON`格式

    ``` {#codeblock_ftr_37u_bst}
    {
     "TotalCount": 1,
     "RequestId": "070363B7-BB66-43B8-9A2C-9E4B83284FC5",
     "PackPaidTraffics": [
       {
         "PaidCapacity": 615.166,
         "MaxAttack": 49.998,
         "InstanceId": "ddosbgp-cn-x1",
         "TotalCapacity": 1302.666,
         "ElasticBandwidth": 100,
         "BaseBandwidth": 20,
         "StartTime": 1557809400000
       }
     ]
    }
    ```


