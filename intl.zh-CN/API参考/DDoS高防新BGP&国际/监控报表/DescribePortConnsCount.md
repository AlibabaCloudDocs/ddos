# DescribePortConnsCount

调用DescribePortConnsCount查询DDoS高防实例的端口连接数统计信息。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=ddoscoo&api=DescribePortConnsCount&type=RPC&version=2020-01-01)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribePortConnsCount|要执行的操作。取值：**DescribePortConnsCount**。 |
|EndTime|Long|是|1583683200|查询结束时间。时间戳格式，单位：秒。

 **说明：** 必须为整点分钟。 |
|InstanceIds.N|RepeatList|是|ddoscoo-cn-mp91j1ao\*\*\*\*|DDoS高防实例的ID。

 **说明：** 您可以调用[DescribeInstanceIds](~~157459~~)查询所有DDoS高防实例的ID信息。 |
|StartTime|Long|是|1582992000|查询开始时间。时间戳格式，单位：秒。

 **说明：** 必须为整点分钟。 |
|RegionId|String|否|cn-hangzhou|DDoS高防服务的地域ID。取值：

 -   **cn-hangzhou**：表示DDoS高防（新BGP）服务。
-   **ap-southeast-1**：表示DDoS高防（国际）服务。 |
|ResourceGroupId|String|否|default|DDoS高防实例在资源管理产品中所属的资源组ID。默认为空，即属于默认资源组。 |
|Port|String|否|80|要查询的端口号。不传入该参数表示查询所有端口号。 |

调用API时，除了本文中该API的请求参数，还需加入阿里云API公共请求参数。公共请求参数的详细介绍，请参见[公共参数](~~157269~~)。

调用API的请求格式，请参见本文**示例**中的请求示例。

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|ActConns|Long|159|活跃的连接数量。 |
|Conns|Long|46340|并发连接数量。 |
|Cps|Long|0|新建连接数量。 |
|InActConns|Long|121|不活跃的连接数量。 |
|RequestId|String|48859E14-A9FB-4100-99FF-AAB75CA46776|本次请求的ID。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=DescribePortConnsCount
&EndTime=1583683200
&InstanceIds.1=ddoscoo-cn-mp91j1ao****
&StartTime=1582992000
&<公共请求参数>
```

正常返回示例

`XML` 格式

```
<DescribePortConnsCountResponse>
	  <Conns>46340</Conns>
	  <RequestId>48859E14-A9FB-4100-99FF-AAB75CA46776</RequestId>
	  <Cps>0</Cps>
	  <ActConns>159</ActConns>
	  <InActConns>121</InActConns>
</DescribePortConnsCountResponse>
```

`JSON` 格式

```
{
	"Conns": 46340,
	"RequestId": "48859E14-A9FB-4100-99FF-AAB75CA46776",
	"Cps": 0,
	"ActConns": 159,
	"InActConns": 121
}
```

## 错误码

访问[错误中心](https://error-center.alibabacloud.com/status/product/ddoscoo)查看更多错误码。

