# DDoS高防（新BGP）计费方式

本文介绍了DDoS高防（新BGP）服务的计费方式。

## 计费概述

DDoS高防（新BGP）为您部署在中国内地地域的业务提供针对DDoS攻击的**基础防护**和**弹性防护**服务。基础防护和弹性防护的具体计费方式如下：

-   基础防护：包年包月（按月-预付费）

    创建DDoS高防（新BGP）实例时，根据业务需要选择实例规格和购买时长，付费后开通实例。已开通的DDoS高防（新BGP）实例，在服务有效期内，为所有接入防护的业务提供保底防护能力。

    例如，创建实例时选择的保底防护带宽是30 Gbps，则接入防护的业务受到的DDoS攻击流量不超过30 Gbps时，可以直接防御，且不产生额外费用。

-   弹性防护：按量付费（按天-后付费）

    根据业务需要选择是否开启。如需开启，您只要将DDoS高防（新BGP）实例的弹性防护带宽设置为大于保底防护带宽的值，则接入防护的业务受到的DDoS攻击流量超过保底防护带宽但小于弹性防护带宽时，也可以防御，且产生发生攻击当日的弹性防护费用。

    例如，DDoS高防（新BGP）实例的保底防护带宽是30 Gbps，弹性防护带宽是100 Gbps，当接入防护的业务受到的DDoS攻击流量不超过30 Gbps或者大于100 Gbps时，不产生弹性防护费用，DDoS攻击流量在30~100 Gbps范围时，产生弹性防护费用。


更多关于DDoS高防（新BGP）的定价信息，请参见[DDoS高防产品定价页](https://www.aliyun.com/price/product#/ddos/detail)。

## 基础防护（按月-预付费）

下表描述了默认规格下，不同DDoS防护能力（保底防护带宽）的DDoS高防（新BGP）实例的定价信息。根据实例支持的防护功能不同，DDoS高防（新BGP）实例分为标准功能和增强功能，两者的费用也有差别。关于标准功能和增强功能的更多信息，请参见[DDoS高防（新BGP&国际）功能套餐](/cn.zh-CN/产品定价/DDoS高防（新BGP&国际）功能套餐.md)。

**说明：** 如果下表描述的DDoS防护能力不能满足您的业务需求，您需要更高的DDoS防护能力，请提交[工单](https://selfservice.console.aliyun.com/ticket/category/ddos/today)联系我们。

|DDoS防护能力|线路|标准功能费用|增强功能费用|
|--------|--|------|------|
|30 Gbps|八线BGP|20,800元/月|28,800元/月|
|60 Gbps|46,800元/月|54,800元/月|
|100 Gbps|328,000元/年（包年优惠价）|424,000元/年（包年优惠价）|
|300 Gbps|528,000元/年（包年优惠价）|624,000元/年（包年优惠价）|
|400 Gbps|968,000元/年（包年优惠价）|1,064,000元/年（包年优惠价）|
|500 Gbps|3,753,600元/年（包年优惠价）|3,849,600元/年（包年优惠价）|
|600 Gbps|4,467,600元/年（包年优惠价）|4,563,600元/年（包年优惠价）|

下表描述了DDoS高防（新BGP）实例的默认规格以及规格的扩展费用。如果您的实际业务需要超出实例的默认规格，您可以升级实例或在购买实例时对相应规格进行扩展。

|名称|说明|默认情况|扩展单价|
|--|--|----|----|
|防护端口数|实例支持添加的TCP和UDP端口数量|50个|每5个端口：250元/月|
|防护域名数|实例支持添加的HTTP和HTTPS域名数量|50个 **说明：** 所有域名所属的一级域名总数不超过5个。

|-   标准功能套餐：每10个域名300元/月
-   增强功能套餐：每10个域名500元/月

**说明：** 每增加10个域名可增加一个一级域名。 |
|业务带宽|实例支持处理的无攻击情况下最大业务流量|100 Mbps|每Mbps：100元/月**说明：** 当实例的总业务带宽规格超出600Mbps时，超出部分的扩展业务带宽可享受优惠价（每Mbps：75元/月）。 |
|业务QPS|实例支持处理的无攻击情况下最大HTTP和HTTPS业务的并发请求速率|3,000 QPS|每100QPS：1,000元/月|

## 弹性防护（按天-后付费）

DDoS高防（新BGP）实例的弹性防护费用按照前一日实际发生的超出保底防护带宽的攻击流量部分的峰值（即选取当日内所遭受的DDoS攻击中的最大值后，扣除该实例的保底防护带宽值，得到超出部分的流量峰值）所对应的计费区间进行计算，生成后付费账单。

**说明：** 如果您将DDoS高防（新BGP）实例的弹性防护带宽设置为与保底防护带宽一致，则不会产生任何后付费账单，但您的DDoS高防（新BGP）实例也将不具备弹性防护能力。

计费说明：

-   如果当日实际发生的DDoS攻击峰值不大于所购买的保底DDoS防护能力，则不会产生任何后付费。
-   当日实际发生的DDoS攻击峰值超过所设置的弹性防护带宽，则不会产生后付费账单。即如果当日实际遭受的DDoS攻击导致所防护的IP被黑洞，则不收取弹性防护费用。
-   当日的弹性防护费用账单一般在第二天上午八点至九点生成。

例如，您的DDoS高防（新BGP）实例的保底防护带宽规格是30 Gbps，弹性防护带宽规格是100 Gbps。当日该实例遭受两次DDoS攻击，其中一次攻击的峰值为80 Gbps，另一次攻击的峰值为40 Gbps，两次攻击均超过保底防护带宽。系统将选取当日所遭受的最大攻击峰值80 Gbps，并扣除实例的保底防护带宽30 Gbps，得到50 Gbps，按照“40 Gbps<攻击峰值≤50 Gbps”的计费区间计算当日所产生的弹性防护费用，即6,400元。

下表描述了不同计费区间的弹性防护费用。

|计费区间|弹性防护费用（单位：元/天）|
|----|--------------|
|0 Gbps<攻击峰值≤5 Gbps|800|
|5 Gbps<攻击峰值≤10 Gbps|1,200|
|10 Gbps<攻击峰值≤20 Gbps|2,200|
|20 Gbps<攻击峰值≤30 Gbps|3,600|
|30 Gbps<攻击峰值≤40 Gbps|4,880|
|40 Gbps<攻击峰值≤50 Gbps|6,400|
|50 Gbps<攻击峰值≤60 Gbps|7,800|
|60 Gbps<攻击峰值≤70 Gbps|9,200|
|70 Gbps<攻击峰值≤80 Gbps|10,600|
|80 Gbps<攻击峰值≤100 Gbps|11,800|
|100 Gbps<攻击峰值≤150 Gbps|14,600|
|150 Gbps<攻击峰值≤200 Gbps|21,600|
|200 Gbps<攻击峰值≤300 Gbps|28,000|
|300 Gbps<攻击峰值≤400 Gbps|40,000|
|400 Gbps<攻击峰值≤500 Gbps|50,000|
|500 Gbps<攻击峰值≤600 Gbps|60,000|
|600 Gbps<攻击峰值≤700 Gbps|70,000|
|700 Gbps<攻击峰值≤800 Gbps|80,000|
|800 Gbps<攻击峰值≤900 Gbps|90,000|
|900 Gbps<攻击峰值≤1000 Gbps|100,000|
|1000 Gbps<攻击峰值≤1100 Gbps|110,000|
|1100 Gbps<攻击峰值≤1200 Gbps|120,000|
|1200 Gbps<攻击峰值≤1300 Gbps|130,000|
|1300 Gbps<攻击峰值≤1400 Gbps|140,000|
|1400 Gbps<攻击峰值≤1500 Gbps|150,000|

## 实例到期说明

|实例到期状态|说明|
|------|--|
|到期前|距离DDoS高防（新BGP）实例到期前的第7天、3天和1天，阿里云将会通过短信、邮件、站内信的形式提醒您实例即将到期，并提示您续费。|
|到期后7天内|-   对防护能力的影响：

如果DDoS高防（新BGP）实例在到期前没有续费，则实例到期后将停止提供DDoS防护服务，已接入防护的资产的DDoS防护能力会恢复到默认的免费防护能力（5 Gbps）且不再拥有弹性防护能力，但是实例仍可以维持业务流量转发。

-   通知：

实例到期后，阿里云将会通知您实例已到期且可用状态会保留7天，并提示您续费。 |
|到期7天后|-   对业务流量转发的影响：

DDoS高防（新BGP）实例到期7天后，将自动停止业务流量转发。如果这时正常续费，则业务流量转发自动恢复，您可以继续正常使用DDoS高防（新BGP）服务。

**说明：** 建议您随时关注DDoS高防（新BGP）控制台上的已经到期的高防实例信息提示，并及时续费或设置自动续费，避免因停止业务流量转发影响业务。

![到期通知](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/7884238951/p76372.png)

-   对实例配置的影响：

阿里云将定期进行资源回收。如果DDoS高防（新BGP）实例到期超过7天且未及时续费，则实例可能自动释放，原有实例配置也将释放。

-   通知：

实例到期7天后，阿里云将会通知您实例已经停止业务流量转发。 |

## 不支持退款

DDoS高防（新BGP）包年包月服务不支持提前退订，也不适用五天无理由退款。如果您已经完成创建DDoS高防（新BGP）实例，则一概不支持退款。

## 相关文档

-   [创建DDoS高防（新BGP）实例](/cn.zh-CN/DDoS高防（新BGP&国际）用户指南/开通DDoS高防（新BGP&国际）.md)
-   [升级DDoS高防实例规格](/cn.zh-CN/DDoS高防（新BGP&国际）用户指南/资产管理/升级DDoS高防实例规格.md)

