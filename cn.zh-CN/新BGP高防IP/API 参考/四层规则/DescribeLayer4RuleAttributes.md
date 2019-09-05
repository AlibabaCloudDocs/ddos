# DescribeLayer4RuleAttributes {#doc_api_ddoscoo_DescribeLayer4RuleAttributes .reference}

调用DescribeLayer4RuleAttributes查询四层转发属性，包括会话保持和DDoS防护策略。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=ddoscoo&api=DescribeLayer4RuleAttributes&type=RPC&version=2017-12-28)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeLayer4RuleAttributes|系统规定参数。取值：**DescribeLayer4RuleAttributes**。

 |
|Listeners|String|是|\[\{"InstanceId":"ddoscoo-cn-XXXXX","Protocol":"tcp","FrontendPort":80\}\]|传入要查询的Listener数组JSON串，每个Listener的具体结构描述如下：

 -   **InstanceId**，String类型，必选，实例ID。
-   **Protocol**，String类型，必选，协议类型。
-   **FrontendPort**，Integer类型，必选，前端使用的端口，取值范围：0-65535。
-   **BackendPort**，Integer类型，可选，后端使用的端口，取值范围：0-65535。
-   **RealServers**，Json数组类型，可选，源站IP地址。
-   **IsAutoCreate**，Boolean类型，可选，是否自动创建。如果是，则不允许删除和修改。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Listeners| | |Listener数组JSON串。

 |
|Config| | |TCP配置。

 |
|NodataConn|String|on|DDoS防护策略的空连接，取值：**off**、**on**。

 |
|PayloadLen| | |包过滤配置。

 |
|Max|Integer|2|DDoS防护策略/包长度过滤，包长度的最大值。

 |
|Min|Integer|1|DDoS防护策略/包长度过滤，包长度的最小值。

 |
|PersistenceTimeout|Integer|0|会话保持的超时时间，单位为秒。默认为**0**，表示关闭。

 |
|Sla| | |目的限制配置。

 |
|Cps|Integer|100|DDoS防护策略/源新建连接限速，取值范围：100~100,000。

 |
|CpsEnable|Integer|0|是否启用Cps，取值：

 -   **0**：禁用cps
-   **1**：启用cps（默认）

 |
|Maxconn|Integer|1000|DDoS防护策略/源并发连接限速，取值范围：1,000~1,000,000。

 |
|MaxconnEnable|Integer|0|是否启用Maxconnection，取值：

 -   **0**：禁用maxconn
-   **1**：启用maxconn（默认）

 |
|Slimit| | |源限制配置。

 |
|Cps|Integer|100|DDoS防护策略/源新建连接限速，取值范围：100~100,000。

 |
|CpsEnable|Integer|0|是否启用Cps，取值：

 -   **0**：禁用cps
-   **1**：启用cps（默认）

 |
|CpsMode|Integer|2|源新建连接限速，取值：

 -   **1**：手动
-   **2**：自动

 |
|Maxconn|Integer|1000|DDoS防护策略/源并发连接限速，取值范围：1,000~1,000,000。

 |
|MaxconnEnable|Integer|0|是否启用Maxconnection，取值：

 -   **0**：禁用maxconn
-   **1**：启用maxconn（默认）

 |
|Synproxy|String|on|DDoS防护策略的虚假源，取值：**off**、**on**。

 |
|FrontendPort|Integer|233|前端使用的端口，范围：0-65535。

 |
|InstanceId|String|ddoscoo-cn-XXXXX|实例ID。

 |
|Protocol|String|tcp|协议类型。

 |
|RequestId|String|CF33B4C3-196E-4015-AADD-5CAD00057B80|本次请求的ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeLayer4RuleAttributes
&Listeners=[{"InstanceId":"ddoscoo-cn-XXXXX","Protocol":"tcp","FrontendPort":80}]
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeLayer4RuleAttributesResponse>
     <Listeners>
          <element>
               <Config>
                    <NodataConn>on</NodataConn>
                    <PayloadLen>
                         <Max>2</Max>
                         <Min>1</Min>
                    </PayloadLen>
                    <PersistenceTimeout>80</PersistenceTimeout>
                    <Sla>
                         <Cps>10</Cps>
                         <CpsEnable>1</CpsEnable>
                         <Maxconn>10</Maxconn>
                         <MaxconnEnable>1</MaxconnEnable>
                    </Sla>
                    <Slimit>
                         <Cps>10</Cps>
                         <CpsEnable>1</CpsEnable>
                         <Maxconn>10</Maxconn>
                         <MaxconnEnable>1</MaxconnEnable>
                    </Slimit>
                    <Synproxy>off</Synproxy>
               </Config>
               <FrontendPort>80</FrontendPort>
               <InstanceId>0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc</InstanceId>
               <Protocol>tcp</Protocol>
          </element>
     </Listeners>
     <RequestId>0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc</RequestId>
</DescribeLayer4RuleAttributesResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Listeners":[
		{
			"Config":{
				"Synproxy":"off",
				"NodataConn":"on",
				"PayloadLen":{
					"Max":2,
					"Min":1
				},
				"Sla":{
					"MaxconnEnable":1,
					"Maxconn":10,
					"Cps":10,
					"CpsEnable":1
				},
				"Slimit":{
					"MaxconnEnable":1,
					"Maxconn":10,
					"Cps":10,
					"CpsEnable":1
				},
				"PersistenceTimeout":80
			},
			"FrontendPort":80,
			"InstanceId":"0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc",
			"Protocol":"tcp"
		}
	],
	"RequestId":"0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/ddoscoo)查看更多错误码。

