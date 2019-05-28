# DescribeInstanceSpecs {#reference_265086 .reference}

调用DescribeInstanceSpecs接口查询防护包的规格信息。

**说明：** DDoS防护包的API接口目前仅对企业版DDoS防护包用户开放。

## 请求参数 {#section_0jj_pcr_rj0 .section}

|名称|类型|是否必选|描述|
|--|--|----|--|
|Action|String|是|要执行的操作，取值：DescribeInstanceSpecs。|
|InstanceIdList|String|是|要查询的防护包实例ID，多个ID间以逗号分隔。以JSON字符串格式传入，例如，\["ddosbgp-cn-x1","ddosbgp-cn-x2"\]。|

## 返回参数 {#section_1as_cc1_hc5 .section}

|名称|类型|描述|
|--|--|--|
|RequestId|String|本次请求的ID。|
|InstanceSpecs|Array|防护包实例的规格信息。|
|└AvailableDeleteBlackholeCount|String|可用的解除黑洞次数。|
|└InstanceId|String|防护包实例ID。|
|└Region|String|防护包实例的区域。|
|└PackConfig|Struct|防护包实例的配置信息。|
|└BindIpCount|Integer|已添加的防护IP数量。|
|└IpAdvanceThre|Integer|被防护IP的弹性防护阈值，单位为Gb。|
|└IpBasicThre|Integer|被防护IP的基础防护阈值，单位为Gb。|
|└IpSpec|Integer|可添加IP的数量。|
|└PackAdvThre|Integer|防护包的弹性防护带宽，单位为Gb。|
|└PackBasicThre|Integer|防护包的基础防护带宽，单位为Gb。|

## 示例 {#section_b48_y6o_uop .section}

请求示例

``` {#codeblock_60x_v7t_oqo}
https://ddosbgp.aliyuncs.com/?Action=DescribeInstanceSpecs
&InstanceIdList=["ddosbgp-cn-o4013qftb006","ddosbgp-cn-78v13ot7u001"]
&公共请求参数
```

正常返回示例

-   `XML`格式

    ``` {#codeblock_yok_0bb_bul}
    <?xml version='1.0' encoding='UTF-8'?>
    <DescribeInstanceSpecsResponse>
       <InstanceSpecs>
           <InstanceSpec>
               <Region>cn-hangzhou</Region>
               <InstanceId>ddosbgp-cn-x1</InstanceId>
               <AvailableDeleteBlackholeCount>100</AvailableDeleteBlackholeCount>
               <PackConfig>
                   <IpBasicThre>20</IpBasicThre>
                   <BindIpCount>0</BindIpCount>
                   <PackBasicThre>20</PackBasicThre>
                   <IpAdvanceThre>101</IpAdvanceThre>
                   <IpSpec>100</IpSpec>
                   <PackAdvThre>101</PackAdvThre>
               </PackConfig>
           </InstanceSpec>
       </InstanceSpecs>
       <RequestId>CEB7F4F5-1DA8-41ED-A9C4-E0F0033E9E1F</RequestId>
    </DescribeInstanceSpecsResponse>
    ```

-   `JSON`格式

    ``` {#codeblock_ftr_37u_bst}
    {
     "InstanceSpecs": [
       {
         "Region": "cn-hangzhou",
         "InstanceId": "ddosbgp-cn-x1",
         "AvailableDeleteBlackholeCount": 100,
         "PackConfig": {
           "IpBasicThre": 20,
           "BindIpCount": 0,
           "PackBasicThre": 20,
           "IpAdvanceThre": 100,
           "IpSpec": 100,
           "PackAdvThre": 101
         }
       }
     ],
     "RequestId": "D8D786F2-2008-4280-B9AB-8E6C4E8C2A16"
    }
    ```


