# DDoS原生防护计费方式

DDoS原生防护提供基础版和企业版套餐。基础版默认开通，免费为您阿里云账号下的ECS、SLB、EIP、WAF实例提供不超过5 Gbps流量的DDoS攻击防御能力；企业版以包年方式计费，您必须通过预付费开通DDoS原生防护企业版实例，才能享受原生防护企业版提供的DDoS全力防护能力。

## DDoS原生防护企业版实例规格

DDoS原生防护企业版实例默认提供DDoS共享全力防护能力。全力防护指根据当前机房网络和整体水位，尽可能对攻击进行防护，并且随着阿里云网络能力的不断提升，全力防护也会提升防护能力，不需要您额外付出升级成本。

DDoS原生防护企业版实例仅支持按年开通服务，订购时长包括1年、2年、3年。在创建DDoS原生防护企业版实例时，单个实例的包年单价由您选择的业务规模和保护IP数量决定。您只需选择与自身业务规模匹配的实例规格并完成一次性预付费，即可享用DDoS原生防护企业版服务。

![业务规模](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/0048919951/p72060.png)

-   **业务规模**：指被防护业务的正常业务规模，以带宽来衡量，入方向或出方向流量按每月最大值95，可选规格：100 Mbps、300 Mbps、500 Mbps、800 Mbps、1 Gbps、1.5 Gbps、2 Gbps、2.5 Gbps、3 Gbps。 关于业务规模的估算方法，请参见[估算业务规模](#section_dno_ebc_uhi)。
-   **保护IP数量**：需要DDoS原生防护实例保护的所有IP的数量，默认是100个，可选数量：100~255。

## 企业版计费规则

如果您需要保护的IP数量为100个，DDoS原生防护企业版套费用（单个地域）=业务规模月单价\*12个月\*订购年限。

如果您需要保护的IP数量超过100个，DDoS原生防护企业版套费用（单个地域）=\{业务规模月单价+（保护的IP数量-100）\*200元/月\}\*12个月\*订购年限。

业务规模月单价请参见下表。

**说明：** DDoS原生防护企业版套餐默认支持保护单个地域下的100个IP，每增加一个IP，其单价增加200元/月。如果您需要保护多个地域下的IP，则需要开通多个实例，或者提交工单申请定制。

下表描述了不同业务规模的DDoS原生防护实例每月的单价。如果以下价格信息与DDoS原生防护购买页存在差异，以[DDoS原生防护购买页面](https://common-buy.aliyun.com/?commodityCode=ddosbgp#/buy)上展示的实际价格为准。

**说明：** 需要防护的IP协议无论是IPV4或IPV6，DDoS原生防护实例每月价格没有差异。

|业务规模|单价（元/月）|
|----|-------|
|100 Mbps|46,800|
|300 Mbps|60,200|
|500 Mbps|73,600|
|800 Mbps|93,700|
|1 Gbps|107,100|
|1.5 Gbps|140,600|
|2 Gbps|174,100|
|2.5 Gbps|207,600|
|3 Gbps|241,100|

**说明：** 默认100 Mbps业务规模起售，可选的最大业务规模为3 Gbps。如果您的业务规模超过3 Gbps，请提交[工单](https://selfservice.console.aliyun.com/ticket/category/ddos_basic/today)申请定制。

## 估算业务规模

您可以按照以下方式估算业务规模（业务带宽）：

以5分钟为粒度采样，采集入方向和出方向的流量并计算入方向和出方向在5分钟内的平均带宽值，取入方向和出方向中较大的值作为采样点的带宽值。月底将所有的采样点按峰值从高到低排序，去掉5%的最高峰值采样点，以第95%个最高峰作为95计费点带宽。

下图是计费点带宽的示意图，以一个月30天为例。

![带宽峰值计算](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/1048919951/p72404.png)

如果实际业务带宽超过已购买的原生防护企业版实例的业务规模，会有什么影响？

原生防护企业版允许业务流量短期峰值超过购买的业务规模规格，但是如果一个月累计36小时超过规格，则全力防护会失效，仅保留原生防护的基础防护能力，正常业务带宽不会受到限制。

## 不支持退款

DDoS原生防护企业版实例不支持五天无理由退款。

## 联系我们

您可以通过[工单](https://selfservice.console.aliyun.com/ticket/category/ddos_basic/today)或联系商务经理定制指定规格的DDoS原生防护企业版实例。

