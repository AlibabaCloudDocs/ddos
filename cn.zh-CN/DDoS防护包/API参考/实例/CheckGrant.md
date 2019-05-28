# CheckGrant {#reference_265078 .reference}

调用CheckGrant接口检查防护包服务的授权状态，即是否授权防护包查询您的ECS服务器信息。

**说明：** DDoS防护包的API接口目前仅对企业版DDoS防护包用户开放。

## 请求参数 {#section_0jj_pcr_rj0 .section}

|名称|类型|是否必选|描述|
|--|--|----|--|
|Action|String|是|要执行的操作，取值：CheckGrant。|

## 返回参数 {#section_1as_cc1_hc5 .section}

|名称|类型|描述|
|--|--|--|
|RequestId|String|本次请求的ID。|
|Status|Integer|授权状态，取值： -   1：已授权DDoS防护包查询您的ECS服务器信息
-   0：未授权DDoS防护包查询您的ECS服务器信息

 |

## 示例 {#section_b48_y6o_uop .section}

请求示例

``` {#codeblock_60x_v7t_oqo}
https://ddosbgp.aliyuncs.com/?Action=CheckGrant
&公共请求参数
```

正常返回示例

-   `XML`格式

    ``` {#codeblock_yok_0bb_bul}
    <?xml version='1.0' encoding='UTF-8'?>
    <CheckGrantResponse>
        <RequestId>C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E</RequestId>
        <Status>1</Status>
    </CheckGrantResponse>
    ```

-   `JSON`格式

    ``` {#codeblock_ftr_37u_bst}
    {
        "Status":1,
        "RequestId":"E76E316C-697F-42D8-883A-D99864D2E77F"
    }
    ```


