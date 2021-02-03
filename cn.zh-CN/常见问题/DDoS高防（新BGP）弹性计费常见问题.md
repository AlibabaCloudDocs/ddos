# DDoS高防（新BGP）弹性计费常见问题

本文列举关于DDoS高防（新BGP）服务弹性计费的常见问题。

-   [如果开启了弹性防护，一个月都没有攻击，是否会产生弹性防护费用？](#section_b4l_uo0_8gz)
-   [我购买了20 Gbps的保底防护、50 Gbps的弹性防护，最终我的防护能力是多大？](#section_e1g_n3h_ttq)
-   [攻击流量超过弹性防护能力上限会怎样？](#section_reb_bc3_r9v)
-   [保底防护带宽30 Gbps，弹性防护带宽50 Gbps，实际攻击流量只有45 Gbps，如何收费？](#section_uew_cwl_895)
-   [当前选择的弹性防护带宽是100 Gbps，发现不够用，可以改成200 Gbps吗？](#section_tbb_9xh_h9r)
-   [已购买30 Gbps保底防护带宽的DDoS高防（新BGP）实例，仍不够用，能否随时升级到更高的防护能力？](#section_ok3_fp4_0o5)
-   [一个IP一天内被攻击多次，费用该怎么计算？](#section_f54_1kp_jy3)
-   [购买了DDoS高防（新BGP）实例，如何停止使用弹性防护能力，避免产生弹性防护的后付费费用？](#section_nvf_ylt_5rd)

## 如果开启了弹性防护，一个月都没有攻击，是否会产生弹性防护费用？

不会。这种情况下，仅需要支付保底防护带宽的包月费用，不产生其他额外的费用。

## 我购买了20 Gbps的保底防护、50 Gbps的弹性防护，最终我的防护能力是多大？

最终实际防护能力是50 Gbps，以弹性防护能力为准。假如您选择20 Gbps的弹性防护能力，则最多只能提供20 Gbps的防护能力，相当于没有弹性防护功能。

## 攻击流量超过弹性防护能力上限会怎样？

如果攻击流量超过弹性防护能力，则受到攻击的DDoS高防（新BGP）IP会强制进入黑洞，阻断全部流量。

## 保底防护带宽30 Gbps，弹性防护带宽50 Gbps，实际攻击流量只有45 Gbps，如何收费？

攻击流量小于30 Gbps（保底防护）的部分不会额外计费，只按照攻击峰值超出保底防护带宽的部分，即15 Gbps（45 Gbps-30 Gbps），收取弹性防护的费用。

您可以在[DDoS防护产品定价页](https://www.aliyun.com/price/product?#/ddos/detail)查询弹性后付费价格。例如，超出保底防护能力的攻击带宽为15 Gbps，对应的价格为2,200元/天。

![云产品定价-cn](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/7741488951/p130906.png)

## 当前选择的弹性防护带宽是100 Gbps，发现不够用，可以改成200 Gbps吗？

可以。

您可以在[DDoS高防控制台](https://yundun.console.aliyun.com/?p=ddoscoo)（选择**中国内地**地域）的**实例管理**页面，调整DDoS高防（新BGP）实例的**防护带宽**。

![调整防护带宽](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/8741488951/p130908.png)

**说明：** 当日发生的攻击已经计费，修改后次日将以最新的弹性带宽进行计费。

## 已购买30 Gbps保底防护带宽的DDoS高防（新BGP）实例，仍不够用，能否随时升级到更高的防护能力？

可以。您可以选择升级当前实例的保底防护带宽，或者增大其弹性防护带宽。

-   升级保底防护带宽

    您可以在[DDoS高防控制台](https://yundun.console.aliyun.com/?p=ddoscoo)（选择**中国内地**地域）的**实例管理**页面对实例进行升级，增大当前实例的**保底防护带宽**，并完成付费。更多信息，请参见[升级DDoS高防实例规格](/cn.zh-CN/DDoS高防（新BGP&国际）用户指南/资产管理/升级DDoS高防实例规格.md)。

    ![升级实例](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/7741488951/p130909.png)

-   增大弹性防护带宽

    您可以在[DDoS高防控制台](https://yundun.console.aliyun.com/?p=ddoscoo)（选择**中国内地**地域）的**实例管理**页面，调整DDoS高防（新BGP）实例的**防护带宽**，增大其弹性防护带宽。开启弹性防护无需您预付费，但会根据DDoS攻击的流量大小生成后付费账单。更多信息，请参见[弹性防护（按天-后付费）](/cn.zh-CN/产品定价/DDoS高防（新BGP）计费方式.md)。

    ![调整防护带宽](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/8741488951/p130908.png)


## 一个IP一天内被攻击多次，费用该怎么计算？

以当天（0:00~24:00）攻击的峰值为准，只产生一次弹性后付费账单。例如某个DDoS防护（新BGP）IP一天内分别遭到50 Gbps、100 Gbps、200 Gbps共三次攻击，则当天的弹性防护付费账单按照200 Gbps攻击的弹性计费标准收取。

## 购买了DDoS高防（新BGP）实例，如何停止使用弹性防护能力，避免产生弹性防护的后付费费用？

您可以将您购买的DDoS高防（新BGP）实例的弹性防护带宽设置为与保底防护带宽一致，在遭受到超出保底防护带宽流量的攻击时，将不会启用弹性防护带宽进行防护。

您可以在[DDoS高防控制台](https://yundun.console.aliyun.com/?p=ddoscoo)（选择**中国内地**地域）的**实例管理**页面，调整DDoS高防（新BGP）实例的**防护带宽**。

![调整防护带宽](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/8741488951/p130908.png)

