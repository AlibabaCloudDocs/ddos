# DescribeInstanceStatus

调用DescribeInstanceStatus查询指定的DDoS高防实例的状态。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=ddoscoo&api=DescribeInstanceStatus&type=RPC&version=2020-01-01)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeInstanceStatus|要执行的操作。取值：**DescribeInstanceStatus**。 |
|InstanceId|String|是|ddoscoo-cn-6ja1y6p5\*\*\*\*|要查询的DDoS高防实例的ID。

 **说明：** 您可以调用[DescribeInstanceIds](~~157459~~)查询所有DDoS高防（新BGP）或DDoS高防（国际）实例的ID。 |
|ProductType|Integer|是|1|要查询的DDoS高防实例的类型。取值：

 -   **1**：表示DDoS高防（新BGP）实例。
-   **2**：表示DDoS高防（国际）实例。 |

调用API时，除了本文中该API的请求参数，还需加入阿里云API公共请求参数。公共请求参数的详细介绍，请参见[公共参数](~~157269~~)。

调用API的请求格式，请参见本文**示例**中的请求示例。

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|InstanceId|String|ddoscoo-cn-6ja1y6p5\*\*\*\*|DDoS高防实例的ID。 |
|InstanceStatus|Integer|1|DDoS高防实例的状态。取值：

 -   **1**：表示正常。
-   **2**：表示已过期。
-   **3**：表示存在欠费。
-   **4**：表示已释放。 |
|RequestId|String|112777CC-2AD6-46FC-A263-00B931406FCD|本次请求的ID。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=DescribeInstanceStatus
&InstanceId=ddoscoo-cn-6ja1y6p5****
&ProductType=1
&<公共请求参数>
```

正常返回示例

`XML` 格式

```
<DescribeInstanceStatusResponse>
	  <RequestId>112777CC-2AD6-46FC-A263-00B931406FCD</RequestId>
	  <InstanceId>ddoscoo-cn-6ja1y6p5****</InstanceId>
	  <InstanceStatus>1</InstanceStatus>
</DescribeInstanceStatusResponse>
```

`JSON` 格式

```
{
    "RequestId": "112777CC-2AD6-46FC-A263-00B931406FCD",
    "InstanceId": "ddoscoo-cn-6ja1y6p5****",
    "InstanceStatus": 1
}
```

## 错误码

访问[错误中心](https://error-center.aliyun.com/status/product/ddoscoo)查看更多错误码。

