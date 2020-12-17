# ModifyWebAreaBlock

调用ModifyWebAreaBlock设置网站业务区域封禁（针对域名）的封禁地区。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=ddoscoo&api=ModifyWebAreaBlock&type=RPC&version=2020-01-01)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|ModifyWebAreaBlock|要执行的操作。取值：**ModifyWebAreaBlock**。 |
|Domain|String|是|www.aliyun.com|网站业务的域名。

 **说明：** 域名必须已配置网站业务转发规则。您可以调用[DescribeDomains](~~91724~~)查询所有域名。 |
|RegionId|String|否|cn-hangzhou|DDoS高防服务的地域ID。取值：

 -   **cn-hangzhou**：表示DDoS高防（新BGP）服务。
-   **ap-southeast-1**：表示DDoS高防（国际）服务。 |
|ResourceGroupId|String|否|default|DDoS高防实例在资源管理产品中所属的资源组ID。默认为空，即属于默认资源组。 |
|Regions.N|RepeatList|否|CN-SHANGHAI|要封禁的区域列表。不传入表示取消区域封禁（针对域名）。取值：

 中国地区

 -   **CN-SHANGHAI**：上海市
-   **CN-YUNNAN**：云南省
-   **CN-INNERMONGOLIA**：内蒙古自治区
-   **CN-BEIJING**：北京市
-   **CN-TAIWAN**：中国台湾
-   **CN-JILIN**：吉林省
-   **CN-SICHUAN**：四川省
-   **CN-TIANJIN**：天津省
-   **CN-NINGXIA**：宁夏回族自制区
-   **CN-ANHUI**：安徽省
-   **CN-SHANDONG**：山东省
-   **CN-SHAANXI**：陕西省
-   **CN-SHANXI**：山西省
-   **CN-GUANGDONG**：广东省
-   **CN-GUANGXI**：广西壮族自治区
-   **CN-JIANGSU**：江苏省
-   **CN-JIANGXI**：江西省
-   **CN-HEBEI**：河北省
-   **CN-HENAN**：河南省
-   **CN-ZHEJIANG**：浙江省
-   **CN-HAINAN**：海南省
-   **CN-HUBEI**：湖北省
-   **CN-HUNAN**：湖南省
-   **CN-MACAU**：中国澳门
-   **CN-GANSU**：甘肃省
-   **CN-FUJIAN**：福建省
-   **CN-GUIZHOU**：贵州省
-   **CN-LIAONING**：辽宁省
-   **CN-CHONGQING**：重庆市
-   **CN-QINGHAI**：青海省
-   **CN-HONGKONG**：中国香港
-   **CN-HEILONGJIANG**：黑龙江省

 海外地区

 -   **OVERSEAS-ASIA**：亚洲（中国除外）
-   **OVERSEAS-EUROPE**：欧洲
-   **OVERSEAS-NAMERICA**：北美洲
-   **OVERSEAS-SAMERICA**：南美洲
-   **OVERSEAS-AFRICA**：非洲
-   **OVERSEAS-OCEANIA**：大洋洲
-   **OVERSEAS-ANTARCTICA**：南极洲 |

调用API时，除了本文中该API的请求参数，还需加入阿里云API公共请求参数。公共请求参数的详细介绍，请参见[公共参数](~~157269~~)。

调用API的请求格式，请参见本文**示例**中的请求示例。

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc|本次请求的ID。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=ModifyWebAreaBlock
&Domain=www.aliyun.com
&Regions.1=CN-SHANGHAI
&<公共请求参数>
```

正常返回示例

`XML` 格式

```
<ModifyWebAreaBlockResponse>
        <RequestId>0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc</RequestId>
</ModifyWebAreaBlockResponse>
```

`JSON` 格式

```
{
    "RequestId": "0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc"
}
```

## 错误码

访问[错误中心](https://error-center.alibabacloud.com/status/product/ddoscoo)查看更多错误码。

