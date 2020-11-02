# DescribeDomainQpsWithCache

调用DescribeDomainQpsWithCache查询网站业务的QPS数据列表，例如总QPS、由不同防护功能阻断的QPS、缓存命中数等。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=ddoscoo&api=DescribeDomainQpsWithCache&type=RPC&version=2020-01-01)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeDomainQpsWithCache|要执行的操作。取值：**DescribeDomainQpsWithCache**。 |
|EndTime|Long|是|1583683200|查询结束时间。时间戳格式，单位：秒。

 **说明：** 必须为整点分钟。 |
|StartTime|Long|是|1582992000|查询开始时间。时间戳格式，单位：秒。

 **说明：** 必须为整点分钟。 |
|RegionId|String|否|cn-hangzhou|DDoS高防服务的地域ID。取值：

 -   **cn-hangzhou**：表示DDoS高防（新BGP）服务。
-   **ap-southeast-1**：表示DDoS高防（国际）服务。 |
|ResourceGroupId|String|否|default|DDoS高防实例在资源管理产品中所属的资源组ID。默认为空，即属于默认资源组。 |
|Domain|String|否|www.aliyun.com|网站业务的域名。

 **说明：** 域名必须已配置网站业务转发规则。您可以调用[DescribeDomains](~~91724~~)查询所有域名。 |

调用API时，除了本文中该API的请求参数，还需加入阿里云API公共请求参数。公共请求参数的详细介绍，请参见[公共参数](~~157269~~)。

调用API的请求格式，请参见本文**示例**中的请求示例。

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|Blocks|List|\[20,30,20\]|攻击QPS。 |
|CacheHits|List|\[0.3,0.4,0.5\]|缓存命中率。使用小数表示，例如0.5表示缓存命中率是50%。 |
|CcBlockQps|List|\[1,0,0\]|由频率控制阻断的QPS。 |
|CcJsQps|List|\[1,0,0\]|由频率控制触发人机识别的QPS。 |
|Interval|Integer|20384|返回数据的步长，单位为秒，即相邻两个数据的时间差。 |
|IpBlockQps|List|\[1,0,0\]|由黑名单（针对域名）阻断的QPS。 |
|PreciseBlocks|List|\[1,0,0\]|由精确访问控制阻断的QPS。 |
|PreciseJsQps|List|\[1,0,0\]|由精确访问控制触发挑战的QPS。 |
|RegionBlocks|List|\[1,0,0\]|由区域封禁阻断的QPS。 |
|RequestId|String|0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc|本次请求的ID。 |
|StartTime|Long|1582992000|开始时间。时间戳格式，单位：秒。 |
|Totals|List|\[100,400,200\]|总QPS。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=DescribeDomainQpsWithCache
&EndTime=1583683200
&StartTime=1582992000
&<公共请求参数>
```

正常返回示例

`XML` 格式

```
<DescribeDomainQpsWithCacheResponse>
	  <Interval>20384</Interval>
	  <StartTime>1582992000</StartTime>
	  <Totals>100</Totals>
	  <Totals>400</Totals>
	  <Totals>200</Totals>
	  <Blocks>20</Blocks>
	  <Blocks>30</Blocks>
	  <Blocks>20</Blocks>
	  <CacheHits>0.3</CacheHits>
	  <CacheHits>0.4</CacheHits>
	  <CacheHits>0.5</CacheHits>
	  <CcBlockQps>1</CcBlockQps>
	  <CcBlockQps>0</CcBlockQps>
	  <CcBlockQps>0</CcBlockQps>
	  <CcJsQps>1</CcJsQps>
	  <CcJsQps>0</CcJsQps>
	  <CcJsQps>0</CcJsQps>
	  <IpBlockQps>1</IpBlockQps>
	  <IpBlockQps>0</IpBlockQps>
	  <IpBlockQps>0</IpBlockQps>
	  <PreciseBlocks>1</PreciseBlocks>
	  <PreciseBlocks>0</PreciseBlocks>
	  <PreciseBlocks>0</PreciseBlocks>
	  <PreciseJsQps>1</PreciseJsQps>
	  <PreciseJsQps>0</PreciseJsQps>
	  <PreciseJsQps>0</PreciseJsQps>
	  <RegionBlocks>1</RegionBlocks>
	  <RegionBlocks>0</RegionBlocks>
	  <RegionBlocks>0</RegionBlocks>
	  <RequestId>0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc</RequestId>
</DescribeDomainQpsWithCacheResponse>
```

`JSON` 格式

```
{
    "Interval": 20384,
    "StartTime": 1582992000,
    "Totals": [
        100,
        400,
        200
    ],
    "Blocks": [
        20,
        30,
        20
    ],
    "CacheHits": [
        0.3,
        0.4,
        0.5
    ],
    "CcBlockQps": [
        1,
        0,
        0
    ],
    "CcJsQps": [
        1,
        0,
        0
    ],
    "IpBlockQps": [
        1,
        0,
        0
    ],
    "PreciseBlocks": [
        1,
        0,
        0
    ],
    "PreciseJsQps": [
        1,
        0,
        0
    ],
    "RegionBlocks": [
        1,
        0,
        0
    ],
    "RequestId": "0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc"
}
```

## 错误码

访问[错误中心](https://error-center.alibabacloud.com/status/product/ddoscoo)查看更多错误码。

