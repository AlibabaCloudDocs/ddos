# DescribeTraffic {#reference_265083 .reference}

调用DescribeTraffic接口查看指定防护包上的流量情况。

**说明：** DDoS防护包的API接口目前仅对企业版DDoS防护包用户开放。

## 请求参数 {#section_0jj_pcr_rj0 .section}

|名称|类型|是否必选|描述|
|--|--|----|--|
|Action|String|是|要执行的操作，取值：DescribeTraffic。|
|EndTime|Integer|是|查询结束时间，秒级时间戳。|
|InstanceId|String|是|要查询的防护包实例ID。|
|Interval|Integer|是|流量统计的时间间隔区间（单位：秒）。|
|StartTime|Integer|是|查询开始时间，秒级时间戳。|
|Ip|String|否|要查询的防护对象IP。|

## 返回参数 {#section_1as_cc1_hc5 .section}

|名称|类型|描述|
|--|--|--|
|RequestId|String|本次请求的ID。|
|FlowList|Array|流量信息。|
|└FlowType|String|显示流量类型： -   avg：区间平均值
-   max：区间峰值

 |
|└Kbps|Integer|流量大小（单位：Kbps）。|
|└Name|Integer|流量信息记录ID。|
|└Pps|Integer|数据包数（单位：pps）。|
|└Time|Integer|流量信息时间戳。|

## 示例 {#section_b48_y6o_uop .section}

请求示例

``` {#codeblock_60x_v7t_oqo}
https://ddosbgp.aliyuncs.com/?Action=DescribeTraffic
&EndTime=1563445054
&InstanceId=ddosbgp-cn-*****
&Interval=1000
&RegionId=cn-hangzhou
&StartTime=1560853054
&公共请求参数
```

正常返回示例

-   `XML`格式

    ``` {#codeblock_yok_0bb_bul}
    <?xml version='1.0' encoding='UTF-8'?>
    <DescribeTraffic>
    	<RequestId>6A507DC8-F657-4C13-84E2-D1D1B9400753</RequestId>
    	<FlowList>
    		<Name>73765106-54e7-11e9-aab0-d89d67182200</Name>
    		<Pps>25</Pps>
    		<Time>1560855000</Time>
    		<FlowType>max</FlowType>
    		<Kbps>17</Kbps>
    	</FlowList>
    	<FlowList>
    		<Name>73765106-54e7-11e9-aab0-d89d67182200</Name>
    		<Pps>9</Pps>
    		<Time>1560857000</Time>
    		<FlowType>max</FlowType>
    		<Kbps>8</Kbps>
    	</FlowList>
    </DescribeTraffic>
    ```

-   `JSON`格式

    ``` {#codeblock_ftr_37u_bst}
    {
     "RequestId": "6A507DC8-F657-4C13-84E2-D1D1B9400753",
     "FlowList": [
            {
                "Name": "73765106-54e7-11e9-aab0-d89d67182200",
                "Pps": 25,
                "Time": 1560855000,
                "FlowType": "max",
                "Kbps": 17
            },
            {
                "Name": "73765106-54e7-11e9-aab0-d89d67182200",
                "Pps": 9,
                "Time": 1560857000,
                "FlowType": "max",
                "Kbps": 8
            }
     ]
    }
    ```


