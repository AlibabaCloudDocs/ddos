# DescribeOnDemandInstance

调用DescribeOnDemandInstance查询代播实例的详细信息。

**说明：** 代播实例可以防护海外云下IDC服务器或在云上按照网段去实现DDoS防护，目前仅支持联系销售人员购买。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=ddosbgp&api=DescribeOnDemandInstance&type=RPC&version=2017-11-20)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeOnDemandInstance|要执行的操作。取值：**DescribeOnDemandInstance**。 |
|PageNo|Integer|是|1|列表的页码，默认值为**1**。 |
|PageSize|Integer|是|10|分页查询时每页的行数，最大值为**50**，默认值为**10**。 |
|RegionId|String|否|cn-zhangjiakou|代播实例的地域ID。

 **说明：** 您可以调用[DescribeRegions](~~118703~~)查询DDoS原生防护支持的所有地域信息。 |

调用API时，除了本文中该API的请求参数，还需加入阿里云API公共请求参数。公共请求参数的详细介绍，请参见[公共参数](~~152121~~)。

调用API的请求格式，请参见本文**示例**中的请求示例。

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|Instances|Array of Instance| |代播实例的详情。 |
|DefenseStatus|String|Defense|代播实例的防护状态。取值：

 -   **Defense**：代播防护已开启，代播IP为资产流量提供牵引和防护。
-   **UnDefense**：代播防护已关闭。 |
|InstanceId|String|ddosbgp-cn-z2q1qzxb\*\*\*\*|代播实例的ID。 |
|Ipnet|List|47.\*\*\*.\*\*\*.0/24|代播实例的IP网段。 |
|RegionId|String|cn-zhangjiakou|代播实例的地域ID。 |
|Remark|String|123|代播实例的备注信息。 |
|RequestId|String|CF33B4C3-196E-4015-AADD-5CAD00057B80|本次请求的ID。 |
|Total|String|1|代播实例的总数。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=DescribeOnDemandInstance
&PageNo=1
&PageSize=10
&<公共请求参数>
```

正常返回示例

`XML` 格式

```
<DescribeOnDemandInstanceResponse>
	  <RequestId>CF33B4C3-196E-4015-AADD-5CAD00057B80</RequestId>
	  <Total>1</Total>
	  <Instances>
		    <InstanceId>ddosbgp-cn-z2q1qzxb****</InstanceId>
		    <Ipnet>47.***.***.0/24</Ipnet>
		    <Remark>123</Remark>
		    <RegionId>cn-zhangjiakou</RegionId>
		    <DefenseStatus>Defense</DefenseStatus>
	  </Instances>
</DescribeOnDemandInstanceResponse>
```

`JSON` 格式

```
{
    "RequestId": "CF33B4C3-196E-4015-AADD-5CAD00057B80",
    "Total": "1",
    "Instances": [
        {
            "InstanceId": "ddosbgp-cn-z2q1qzxb****",
            "Ipnet": [
                "47.***.***.0/24"
            ],
            "Remark": "123",
            "RegionId": "cn-zhangjiakou",
            "DefenseStatus": "Defense"
        }
    ]
}
```

## 错误码

访问[错误中心](https://error-center.aliyun.com/status/product/ddosbgp)查看更多错误码。

