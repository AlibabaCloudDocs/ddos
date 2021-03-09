# API概览

本文汇总了DDoS高防（新BGP）和DDoS高防（国际）服务所有可调用的API。

**说明：** 本文列举的接口适用于DDoS高防（新BGP）和DDoS高防（国际）服务。

在使用以下接口前，请确认您已经购买了DDoS高防（新BGP）或DDoS高防（国际）实例。具体操作，请参见[开通DDoS高防（新BGP&国际）](/cn.zh-CN/DDoS高防（新BGP&国际）用户指南/开通DDoS高防（新BGP&国际）.md)。

如无特殊说明，以下接口同时适用于DDoS高防（新BGP）和DDoS高防（国际），个别仅适用于DDoS高防（新BGP）或DDoS高防（国际）的接口，在相关接口文档中有说明。关于DDoS高防（新BGP）和DDoS高防（国际）的功能差异，请参见[DDoS高防（新BGP）和DDoS高防（国际）的功能差异](/cn.zh-CN/阿里云DDoS防护产品介绍/什么是DDoS高防（新BGP&国际）.md)。

更多API资源，请访问[OpenAPI开发者门户](https://next.api.aliyun.com/api/ddoscoo/2020-01-01)。

## 实例

|API|描述|
|---|--|
|[DescribeInstanceIds](/cn.zh-CN/API参考/DDoS高防新BGP&国际/实例/DescribeInstanceIds.md)|查询DDoS高防实例的ID信息。|
|[DescribeInstances](/cn.zh-CN/API参考/DDoS高防新BGP&国际/实例/DescribeInstances.md)|查询DDoS高防实例的详细信息，包含业务转发状态、到期状态、欠费状态等。|
|[DescribeInstanceStatus](/cn.zh-CN/API参考/DDoS高防新BGP&国际/实例/DescribeInstanceStatus.md)|查询指定的DDoS高防实例的状态，包含正常、过期、欠费、释放。|
|[DescribeInstanceDetails](/cn.zh-CN/API参考/DDoS高防新BGP&国际/实例/DescribeInstanceDetails.md)|查询指定的DDoS高防实例的IP和线路信息。|
|[DescribeInstanceSpecs](/cn.zh-CN/API参考/DDoS高防新BGP&国际/实例/DescribeInstanceSpecs.md)|查询指定的DDoS高防实例的规格信息。|
|[DescribeInstanceStatistics](/cn.zh-CN/API参考/DDoS高防新BGP&国际/实例/DescribeInstanceStatistics.md)|查询指定的DDoS高防实例的统计信息，例如已防护的域名、端口数量等。|
|[ModifyInstanceRemark](/cn.zh-CN/API参考/DDoS高防新BGP&国际/实例/ModifyInstanceRemark.md)|修改DDoS高防实例的备注。|
|[DescribeElasticBandwidthSpec](/cn.zh-CN/API参考/DDoS高防新BGP&国际/实例/DescribeElasticBandwidthSpec.md)|查询指定的DDoS高防（新BGP）实例的可选弹性防护带宽规格。|
|[ModifyElasticBandWidth](/cn.zh-CN/API参考/DDoS高防新BGP&国际/实例/ModifyElasticBandWidth.md)|修改DDoS高防（新BGP）实例的弹性防护带宽。|
|[DescribeDefenseCountStatistics](/cn.zh-CN/API参考/DDoS高防新BGP&国际/实例/DescribeDefenseCountStatistics.md)|查询DDoS高防（国际）服务的防护次数统计信息，例如可用和已用的高级防护次数。|
|[ReleaseInstance](/cn.zh-CN/API参考/DDoS高防新BGP&国际/实例/ReleaseInstance.md)|释放某个已经到期的DDoS高防实例。|

## 域名接入

|API|描述|
|---|--|
|[DescribeDomains](/cn.zh-CN/API参考/DDoS高防新BGP&国际/域名接入/DescribeDomains.md)|查询已接入DDoS高防进行防护的网站域名。|
|[DescribeWebRules](/cn.zh-CN/API参考/DDoS高防新BGP&国际/域名接入/DescribeWebRules.md)|查询网站业务转发规则。|
|[CreateWebRule](/cn.zh-CN/API参考/DDoS高防新BGP&国际/域名接入/CreateWebRule.md)|创建网站业务转发规则。|
|[ModifyWebRule](/cn.zh-CN/API参考/DDoS高防新BGP&国际/域名接入/ModifyWebRule.md)|修改网站业务转发规则。|
|[DeleteWebRule](/cn.zh-CN/API参考/DDoS高防新BGP&国际/域名接入/DeleteWebRule.md)|删除网站业务转发规则。|
|[DescribeWebInstanceRelations](/cn.zh-CN/API参考/DDoS高防新BGP&国际/域名接入/DescribeWebInstanceRelations.md)|查询网站业务关联的DDoS高防实例信息。|
|[AssociateWebCert](/cn.zh-CN/API参考/DDoS高防新BGP&国际/域名接入/AssociateWebCert.md)|为网站业务转发规则关联SSL证书。|
|[ModifyTlsConfig](/cn.zh-CN/API参考/DDoS高防新BGP&国际/域名接入/ModifyTlsConfig.md)|修改网站业务转发规则的TLS安全策略。|
|[DescribeWebCustomPorts](/cn.zh-CN/API参考/DDoS高防新BGP&国际/域名接入/DescribeWebCustomPorts.md)|查询DDoS高防支持的网站业务自定义端口范围。|
|[DescribeWebAccessMode](/cn.zh-CN/API参考/DDoS高防新BGP&国际/域名接入/DescribeWebAccessMode.md)|查询网站业务的接入模式。|
|[ModifyWebAccessMode](/cn.zh-CN/API参考/DDoS高防新BGP&国际/域名接入/ModifyWebAccessMode.md)|修改网站业务的接入模式。|
|[DescribeCerts](/cn.zh-CN/API参考/DDoS高防新BGP&国际/域名接入/DescribeCerts.md)|查询网站业务的证书信息。|
|[DescribeCnameReuses](/cn.zh-CN/API参考/DDoS高防新BGP&国际/域名接入/DescribeCnameReuses.md)|查询网站业务的CNAME复用信息。|
|[ModifyCnameReuse](/cn.zh-CN/API参考/DDoS高防新BGP&国际/域名接入/ModifyCnameReuse.md)|为网站业务开启或关闭CNAME复用。|
|[ModifyHttp2Enable](/cn.zh-CN/API参考/DDoS高防新BGP&国际/域名接入/ModifyHttp2Enable.md)|修改网站业务转发规则的HTTP 2.0开关状态。|
|[DescribeL7RsPolicy](/cn.zh-CN/API参考/DDoS高防新BGP&国际/域名接入/DescribeL7RsPolicy.md)|查询网站业务转发规则的回源策略。|
|[ConfigL7RsPolicy](/cn.zh-CN/API参考/DDoS高防新BGP&国际/域名接入/ConfigL7RsPolicy.md)|为网站业务转发规则设置回源策略。|

## 端口接入

|API|描述|
|---|--|
|[DescribeNetworkRules](/cn.zh-CN/API参考/DDoS高防新BGP&国际/端口接入/DescribeNetworkRules.md)|查询端口转发规则。|
|[CreateNetworkRules](/cn.zh-CN/API参考/DDoS高防新BGP&国际/端口接入/CreateNetworkRules.md)|创建端口转发规则。|
|[ConfigNetworkRules](/cn.zh-CN/API参考/DDoS高防新BGP&国际/端口接入/ConfigNetworkRules.md)|修改端口转发规则。|
|[DeleteNetworkRule](/cn.zh-CN/API参考/DDoS高防新BGP&国际/端口接入/DeleteNetworkRule.md)|删除端口转发规则。|
|[DescribeHealthCheckList](/cn.zh-CN/API参考/DDoS高防新BGP&国际/端口接入/DescribeHealthCheckList.md)|查询端口转发规则的（四层或七层）健康检查配置。|
|[ModifyHealthCheckConfig](/cn.zh-CN/API参考/DDoS高防新BGP&国际/端口接入/ModifyHealthCheckConfig.md)|修改端口转发规则的（四层或七层）健康检查配置。|
|[DescribeHealthCheckStatus](/cn.zh-CN/API参考/DDoS高防新BGP&国际/端口接入/DescribeHealthCheckStatus.md)|查询源站健康检查状态信息。|

## 流量调度器

|API|描述|
|---|--|
|[DescribeSchedulerRules](/cn.zh-CN/API参考/DDoS高防新BGP&国际/流量调度器/DescribeSchedulerRules.md)|查询流量调度器调度规则。|
|[CreateSchedulerRule](/cn.zh-CN/API参考/DDoS高防新BGP&国际/流量调度器/CreateSchedulerRule.md)|创建流量调度器调度规则。|
|[ModifySchedulerRule](/cn.zh-CN/API参考/DDoS高防新BGP&国际/流量调度器/ModifySchedulerRule.md)|修改流量调度器调度规则。|
|[DeleteSchedulerRule](/cn.zh-CN/API参考/DDoS高防新BGP&国际/流量调度器/DeleteSchedulerRule.md)|删除流量调度器调度规则。|

## 基础设施防护策略

|API|描述|
|---|--|
|[DescribeAutoCcListCount](/cn.zh-CN/API参考/DDoS高防新BGP&国际/基础设施防护策略/DescribeAutoCcListCount.md)|查询针对DDoS高防实例的黑名单和白名单IP的数量。|
|[DescribeAutoCcBlacklist](/cn.zh-CN/API参考/DDoS高防新BGP&国际/基础设施防护策略/DescribeAutoCcBlacklist.md)|查询针对DDoS高防实例的黑名单IP。|
|[AddAutoCcBlacklist](/cn.zh-CN/API参考/DDoS高防新BGP&国际/基础设施防护策略/AddAutoCcBlacklist.md)|添加针对DDoS高防实例的黑名单IP。|
|[DeleteAutoCcBlacklist](/cn.zh-CN/API参考/DDoS高防新BGP&国际/基础设施防护策略/DeleteAutoCcBlacklist.md)|删除针对DDoS高防实例的黑名单IP。|
|[EmptyAutoCcBlacklist](/cn.zh-CN/API参考/DDoS高防新BGP&国际/基础设施防护策略/EmptyAutoCcBlacklist.md)|清空针对DDoS高防实例的黑名单IP。|
|[DescribeAutoCcWhitelist](/cn.zh-CN/API参考/DDoS高防新BGP&国际/基础设施防护策略/DescribeAutoCcWhitelist.md)|查询针对DDoS高防实例的白名单IP。|
|[AddAutoCcWhitelist](/cn.zh-CN/API参考/DDoS高防新BGP&国际/基础设施防护策略/AddAutoCcWhitelist.md)|添加针对DDoS高防实例的白名单IP。|
|[DeleteAutoCcWhitelist](/cn.zh-CN/API参考/DDoS高防新BGP&国际/基础设施防护策略/DeleteAutoCcWhitelist.md)|删除针对DDoS高防实例的白名单IP。|
|[EmptyAutoCcWhitelist](/cn.zh-CN/API参考/DDoS高防新BGP&国际/基础设施防护策略/EmptyAutoCcWhitelist.md)|清空针对DDoS高防实例的白名单IP。|
|[DescribeUnBlackholeCount](/cn.zh-CN/API参考/DDoS高防新BGP&国际/基础设施防护策略/DescribeUnBlackholeCount.md)|查询黑洞解封次数。|
|[DescribeBlackholeStatus](/cn.zh-CN/API参考/DDoS高防新BGP&国际/基础设施防护策略/DescribeBlackholeStatus.md)|查询DDoS高防实例的黑洞状态。|
|[ModifyBlackholeStatus](/cn.zh-CN/API参考/DDoS高防新BGP&国际/基础设施防护策略/ModifyBlackholeStatus.md)|执行黑洞解封。|
|[DescribeNetworkRegionBlock](/cn.zh-CN/API参考/DDoS高防新BGP&国际/基础设施防护策略/DescribeNetworkRegionBlock.md)|查询针对DDoS高防实例的区域封禁配置。|
|[ConfigNetworkRegionBlock](/cn.zh-CN/API参考/DDoS高防新BGP&国际/基础设施防护策略/ConfigNetworkRegionBlock.md)|修改针对DDoS高防实例的区域封禁配置。|
|[DescribeBlockStatus](/cn.zh-CN/API参考/DDoS高防新BGP&国际/基础设施防护策略/DescribeBlockStatus.md)|查询DDoS高防（新BGP）实例的近源流量压制配置。|
|[ModifyBlockStatus](/cn.zh-CN/API参考/DDoS高防新BGP&国际/基础设施防护策略/ModifyBlockStatus.md)|修改DDoS高防（新BGP）实例的近源流量压制配置。|
|[DescribeUnBlockCount](/cn.zh-CN/API参考/DDoS高防新BGP&国际/基础设施防护策略/DescribeUnBlockCount.md)|查询阿里云账号可用的近源流量压制次数。|

## 网站业务防护策略

|API|描述|
|---|--|
|[DescribeWebCcProtectSwitch](/cn.zh-CN/API参考/DDoS高防新BGP&国际/网站业务防护策略/DescribeWebCcProtectSwitch.md)|查询网站业务各防护功能的开关状态。|
|[ModifyWebAIProtectSwitch](/cn.zh-CN/API参考/DDoS高防新BGP&国际/网站业务防护策略/ModifyWebAIProtectSwitch.md)|修改网站业务AI智能防护的开关状态。|
|[ModifyWebAIProtectMode](/cn.zh-CN/API参考/DDoS高防新BGP&国际/网站业务防护策略/ModifyWebAIProtectMode.md)|修改网站业务AI智能防护的模式。|
|[ModifyWebIpSetSwitch](/cn.zh-CN/API参考/DDoS高防新BGP&国际/网站业务防护策略/ModifyWebIpSetSwitch.md)|修改网站业务黑白名单（针对域名）的开关状态。|
|[ConfigWebIpSet](/cn.zh-CN/API参考/DDoS高防新BGP&国际/网站业务防护策略/ConfigWebIpSet.md)|修改针对网站业务的黑名单和白名单IP。|
|[EnableWebCC](/cn.zh-CN/API参考/DDoS高防新BGP&国际/网站业务防护策略/EnableWebCC.md)|开启网站业务频率控制防护（CC防护）的开关。|
|[DisableWebCC](/cn.zh-CN/API参考/DDoS高防新BGP&国际/网站业务防护策略/DisableWebCC.md)|关闭网站业务频率控制防护（CC防护）的开关。|
|[ConfigWebCCTemplate](/cn.zh-CN/API参考/DDoS高防新BGP&国际/网站业务防护策略/ConfigWebCCTemplate.md)|修改网站业务频率控制防护（CC防护）的防护模式。|
|[EnableWebCCRule](/cn.zh-CN/API参考/DDoS高防新BGP&国际/网站业务防护策略/EnableWebCCRule.md)|开启网站业务频率控制防护（CC防护）的自定义规则开关。|
|[DisableWebCCRule](/cn.zh-CN/API参考/DDoS高防新BGP&国际/网站业务防护策略/DisableWebCCRule.md)|关闭网站业务频率控制防护（CC防护）的自定义规则开关。|
|[DescribeWebCCRules](/cn.zh-CN/API参考/DDoS高防新BGP&国际/网站业务防护策略/DescribeWebCCRules.md)|查询网站业务频率控制防护（CC防护）的自定义规则。|
|[CreateWebCCRule](/cn.zh-CN/API参考/DDoS高防新BGP&国际/网站业务防护策略/CreateWebCCRule.md)|创建网站业务频率控制防护（CC防护）的自定义规则。|
|[ModifyWebCCRule](/cn.zh-CN/API参考/DDoS高防新BGP&国际/网站业务防护策略/ModifyWebCCRule.md)|修改网站业务频率控制防护（CC防护）的自定义规则。|
|[DeleteWebCCRule](/cn.zh-CN/API参考/DDoS高防新BGP&国际/网站业务防护策略/DeleteWebCCRule.md)|删除网站业务频率控制防护（CC防护）的自定义规则。|
|[ModifyWebPreciseAccessSwitch](/cn.zh-CN/API参考/DDoS高防新BGP&国际/网站业务防护策略/ModifyWebPreciseAccessSwitch.md)|修改网站业务精确访问控制的开关状态。|
|[DescribeWebPreciseAccessRule](/cn.zh-CN/API参考/DDoS高防新BGP&国际/网站业务防护策略/DescribeWebPreciseAccessRule.md)|查询网站业务精确访问控制规则。|
|[ModifyWebPreciseAccessRule](/cn.zh-CN/API参考/DDoS高防新BGP&国际/网站业务防护策略/ModifyWebPreciseAccessRule.md)|修改网站业务精确访问控制规则。|
|[DeleteWebPreciseAccessRule](/cn.zh-CN/API参考/DDoS高防新BGP&国际/网站业务防护策略/DeleteWebPreciseAccessRule.md)|删除网站业务精确访问控制规则。|
|[ModifyWebAreaBlockSwitch](/cn.zh-CN/API参考/DDoS高防新BGP&国际/网站业务防护策略/ModifyWebAreaBlockSwitch.md)|修改网站业务区域封禁（针对域名）的开关状态。|
|[DescribeWebAreaBlockConfigs](/cn.zh-CN/API参考/DDoS高防新BGP&国际/网站业务防护策略/DescribeWebAreaBlockConfigs.md)|查询网站业务区域封禁（针对域名）的配置信息。|
|[ModifyWebAreaBlock](/cn.zh-CN/API参考/DDoS高防新BGP&国际/网站业务防护策略/ModifyWebAreaBlock.md)|修改网站业务区域封禁（针对域名）的封禁地区。|

## 非网站业务防护策略

|API|描述|
|---|--|
|[DescribePortAutoCcStatus](/cn.zh-CN/API参考/DDoS高防新BGP&国际/非网站业务防护策略/DescribePortAutoCcStatus.md)|查询非网站业务AI智能防护的配置信息。|
|[ModifyPortAutoCcStatus](/cn.zh-CN/API参考/DDoS高防新BGP&国际/非网站业务防护策略/ModifyPortAutoCcStatus.md)|修改非网站业务AI智能防护的配置信息。|
|[DescribeNetworkRuleAttributes](/cn.zh-CN/API参考/DDoS高防新BGP&国际/非网站业务防护策略/DescribeNetworkRuleAttributes.md)|查询非网站业务端口转发规则的防护配置，包括会话保持和DDoS防护策略。|
|[ModifyNetworkRuleAttribute](/cn.zh-CN/API参考/DDoS高防新BGP&国际/非网站业务防护策略/ModifyNetworkRuleAttribute.md)|修改非网站业务端口转发规则的会话保持策略。|

## 定制场景策略

|API|描述|
|---|--|
|[DescribeSceneDefensePolicies](/cn.zh-CN/API参考/DDoS高防新BGP&国际/定制场景策略/DescribeSceneDefensePolicies.md)|查询定制场景策略的详细信息。|
|[CreateSceneDefensePolicy](/cn.zh-CN/API参考/DDoS高防新BGP&国际/定制场景策略/CreateSceneDefensePolicy.md)|创建定制场景策略。|
|[ModifySceneDefensePolicy](/cn.zh-CN/API参考/DDoS高防新BGP&国际/定制场景策略/ModifySceneDefensePolicy.md)|修改定制场景策略。|
|[DeleteSceneDefensePolicy](/cn.zh-CN/API参考/DDoS高防新BGP&国际/定制场景策略/DeleteSceneDefensePolicy.md)|删除定制场景策略。|
|[DescribeSceneDefenseObjects](/cn.zh-CN/API参考/DDoS高防新BGP&国际/定制场景策略/DescribeSceneDefenseObjects.md)|查询定制场景策略的防护对象。|
|[AttachSceneDefenseObject](/cn.zh-CN/API参考/DDoS高防新BGP&国际/定制场景策略/AttachSceneDefenseObject.md)|为定制场景策略添加防护对象。|
|[DetachSceneDefenseObject](/cn.zh-CN/API参考/DDoS高防新BGP&国际/定制场景策略/DetachSceneDefenseObject.md)|为定制场景策略移除防护对象。|
|[EnableSceneDefensePolicy](/cn.zh-CN/API参考/DDoS高防新BGP&国际/定制场景策略/EnableSceneDefensePolicy.md)|启用定制场景策略。|
|[DisableSceneDefensePolicy](/cn.zh-CN/API参考/DDoS高防新BGP&国际/定制场景策略/DisableSceneDefensePolicy.md)|禁用定制场景策略。|

## 攻击分析

|API|描述|
|---|--|
|[DescribeDDosEventMax](/cn.zh-CN/API参考/DDoS高防新BGP&国际/攻击分析/DescribeDDosEventMax.md)|查询指定时间范围内的流量型攻击峰值（bps）、连接型攻击峰值（cps）、Web资源耗尽型攻击峰值（qps）。|
|[DescribeDDosAllEventList](/cn.zh-CN/API参考/DDoS高防新BGP&国际/攻击分析/DescribeDDosAllEventList.md)|查询攻击事件列表。|
|[DescribeDDosEventArea](/cn.zh-CN/API参考/DDoS高防新BGP&国际/攻击分析/DescribeDDosEventArea.md)|查询某次流量型攻击的来源地域详情。|
|[DescribeDDosEventAttackType](/cn.zh-CN/API参考/DDoS高防新BGP&国际/攻击分析/DescribeDDosEventAttackType.md)|查询某次流量型攻击的攻击类型详情。|
|[DescribeDDosEventIsp](/cn.zh-CN/API参考/DDoS高防新BGP&国际/攻击分析/DescribeDDosEventIsp.md)|查询某次流量型攻击的攻击来源网络运营商（ISP）信息。|
|[DescribeDDosEventSrcIp](/cn.zh-CN/API参考/DDoS高防新BGP&国际/攻击分析/DescribeDDosEventSrcIp.md)|查询某次流量型攻击的攻击来源IP详情。|

## 监控报表

|API|描述|
|---|--|
|[DescribeDDoSEvents](/cn.zh-CN/API参考/DDoS高防新BGP&国际/监控报表/DescribeDDoSEvents.md)|查询针对DDoS高防实例的攻击事件。|
|[DescribePortFlowList](/cn.zh-CN/API参考/DDoS高防新BGP&国际/监控报表/DescribePortFlowList.md)|查询DDoS高防实例的流量数据列表。|
|[DescribePortConnsList](/cn.zh-CN/API参考/DDoS高防新BGP&国际/监控报表/DescribePortConnsList.md)|查询DDoS高防实例的端口连接数列表。|
|[DescribePortConnsCount](/cn.zh-CN/API参考/DDoS高防新BGP&国际/监控报表/DescribePortConnsCount.md)|查询DDoS高防实例的端口连接数统计信息。|
|[DescribePortMaxConns](/cn.zh-CN/API参考/DDoS高防新BGP&国际/监控报表/DescribePortMaxConns.md)|查询DDoS高防实例的端口连接峰值信息。|
|[DescribePortAttackMaxFlow](/cn.zh-CN/API参考/DDoS高防新BGP&国际/监控报表/DescribePortAttackMaxFlow.md)|查询指定时间段内DDoS高防实例受到的攻击带宽和包速峰值。|
|[DescribePortViewSourceCountries](/cn.zh-CN/API参考/DDoS高防新BGP&国际/监控报表/DescribePortViewSourceCountries.md)|查询指定时间段内DDoS高防实例的请求来源国家分布。|
|[DescribePortViewSourceProvinces](/cn.zh-CN/API参考/DDoS高防新BGP&国际/监控报表/DescribePortViewSourceProvinces.md)|查询指定时间段内DDoS高防实例的请求来源（中国）省份分布。|
|[DescribePortViewSourceIsps](/cn.zh-CN/API参考/DDoS高防新BGP&国际/监控报表/DescribePortViewSourceIsps.md)|查询指定时间段内DDoS高防实例的请求来源运营商分布。|
|[DescribeDomainAttackEvents](/cn.zh-CN/API参考/DDoS高防新BGP&国际/监控报表/DescribeDomainAttackEvents.md)|查询针对网站业务的攻击事件。|
|[DescribeDomainQPSList](/cn.zh-CN/API参考/DDoS高防新BGP&国际/监控报表/DescribeDomainQPSList.md)|查询网站业务的QPS统计信息。|
|[DescribeDomainQpsWithCache](/cn.zh-CN/API参考/DDoS高防新BGP&国际/监控报表/DescribeDomainQpsWithCache.md)|查询网站业务的QPS数据列表，例如总QPS、由不同防护功能阻断的QPS、缓存命中数等。|
|[DescribeDomainOverview](/cn.zh-CN/API参考/DDoS高防新BGP&国际/监控报表/DescribeDomainOverview.md)|查询网站业务攻击总览，包括HTTP攻击峰值、HTTPS攻击峰值。|
|[DescribeDomainStatusCodeList](/cn.zh-CN/API参考/DDoS高防新BGP&国际/监控报表/DescribeDomainStatusCodeList.md)|查询网站业务的各类响应状态码统计列表。|
|[DescribeDomainStatusCodeCount](/cn.zh-CN/API参考/DDoS高防新BGP&国际/监控报表/DescribeDomainStatusCodeCount.md)|查询指定时间段内网站业务的各类响应状态码的统计信息。|
|[DescribeDomainTopAttackList](/cn.zh-CN/API参考/DDoS高防新BGP&国际/监控报表/DescribeDomainTopAttackList.md)|查询指定时间段内网站业务的QPS峰值数据，包括攻击QPS、总QPS。|
|[DescribeDomainViewSourceCountries](/cn.zh-CN/API参考/DDoS高防新BGP&国际/监控报表/DescribeDomainViewSourceCountries.md)|查询指定时间段内网站业务的请求来源国家分布。|
|[DescribeDomainViewSourceProvinces](/cn.zh-CN/API参考/DDoS高防新BGP&国际/监控报表/DescribeDomainViewSourceProvinces.md)|查询指定时间段内网站业务的请求来源（中国）省份分布。|
|[DescribeDomainViewTopCostTime](/cn.zh-CN/API参考/DDoS高防新BGP&国际/监控报表/DescribeDomainViewTopCostTime.md)|查询指定时间段内网站业务的请求耗时最大的前N个URL。|
|[DescribeDomainViewTopUrl](/cn.zh-CN/API参考/DDoS高防新BGP&国际/监控报表/DescribeDomainViewTopUrl.md)|查询指定时间段内网站业务访问量最大的前N个URL。|

## 全量日志分析

|API|描述|
|---|--|
|[DescribeSlsOpenStatus](/cn.zh-CN/API参考/DDoS高防新BGP&国际/全量日志分析/DescribeSlsOpenStatus.md)|查询阿里云日志服务SLS（Log Service）的开通状态。|
|[DescribeSlsAuthStatus](/cn.zh-CN/API参考/DDoS高防新BGP&国际/全量日志分析/DescribeSlsAuthStatus.md)|查询DDoS高防全量日志分析服务的授权状态，即是否授权DDoS高防访问日志服务。|
|[DescribeLogStoreExistStatus](/cn.zh-CN/API参考/DDoS高防新BGP&国际/全量日志分析/DescribeLogStoreExistStatus.md)|查询是否已创建了DDoS高防的日志库。|
|[DescribeSlsLogstoreInfo](/cn.zh-CN/API参考/DDoS高防新BGP&国际/全量日志分析/DescribeSlsLogstoreInfo.md)|查询DDoS高防的日志库信息，例如日志存储容量、日志存储时长等。|
|[ModifyFullLogTtl](/cn.zh-CN/API参考/DDoS高防新BGP&国际/全量日志分析/ModifyFullLogTtl.md)|修改DDoS高防全量日志的存储时长。|
|[DescribeWebAccessLogDispatchStatus](/cn.zh-CN/API参考/DDoS高防新BGP&国际/全量日志分析/DescribeWebAccessLogDispatchStatus.md)|查询所有域名的全量日志开关状态。|
|[DescribeWebAccessLogStatus](/cn.zh-CN/API参考/DDoS高防新BGP&国际/全量日志分析/DescribeWebAccessLogStatus.md)|查询单个网站业务的全量日志服务信息，例如开关状态、对接的日志项目、日志库。|
|[EnableWebAccessLogConfig](/cn.zh-CN/API参考/DDoS高防新BGP&国际/全量日志分析/EnableWebAccessLogConfig.md)|为网站业务开启全量日志分析。|
|[DisableWebAccessLogConfig](/cn.zh-CN/API参考/DDoS高防新BGP&国际/全量日志分析/DisableWebAccessLogConfig.md)|为网站业务关闭全量日志分析。|
|[DescribeWebAccessLogEmptyCount](/cn.zh-CN/API参考/DDoS高防新BGP&国际/全量日志分析/DescribeWebAccessLogEmptyCount.md)|查询可用的清空日志库的次数。|
|[EmptySlsLogstore](/cn.zh-CN/API参考/DDoS高防新BGP&国际/全量日志分析/EmptySlsLogstore.md)|清空DDoS高防的日志库。|

## 标签

|API|描述|
|---|--|
|[DescribeTagKeys](/cn.zh-CN/API参考/DDoS高防新BGP&国际/标签/DescribeTagKeys.md)|查询所有标签键。|
|[DescribeTagResources](/cn.zh-CN/API参考/DDoS高防新BGP&国际/标签/DescribeTagResources.md)|查询资源关联的标签信息。|
|[CreateTagResources](/cn.zh-CN/API参考/DDoS高防新BGP&国际/标签/CreateTagResources.md)|为资源关联标签。|
|[DeleteTagResources](/cn.zh-CN/API参考/DDoS高防新BGP&国际/标签/DeleteTagResources.md)|为资源移除标签。|

## 静态页面缓存

|API|描述|
|---|--|
|[DescribeWebCacheConfigs](/cn.zh-CN/API参考/DDoS高防新BGP&国际/静态页面缓存/DescribeWebCacheConfigs.md)|查询网站业务静态页面缓存的配置。|
|[ModifyWebCacheSwitch](/cn.zh-CN/API参考/DDoS高防新BGP&国际/静态页面缓存/ModifyWebCacheSwitch.md)|修改网站业务静态页面缓存的开关状态。|
|[ModifyWebCacheMode](/cn.zh-CN/API参考/DDoS高防新BGP&国际/静态页面缓存/ModifyWebCacheMode.md)|修改网站业务静态页面缓存的缓存模式。|
|[ModifyWebCacheCustomRule](/cn.zh-CN/API参考/DDoS高防新BGP&国际/静态页面缓存/ModifyWebCacheCustomRule.md)|修改网站业务静态页面缓存的自定义规则。|
|[DeleteWebCacheCustomRule](/cn.zh-CN/API参考/DDoS高防新BGP&国际/静态页面缓存/DeleteWebCacheCustomRule.md)|删除网站业务静态页面缓存的自定义规则。|

## 系统配置与日志

|API|描述|
|---|--|
|[DescribeStsGrantStatus](/cn.zh-CN/API参考/DDoS高防新BGP&国际/系统配置与日志/DescribeStsGrantStatus.md)|查询阿里云账号是否授权了DDoS高防服务访问其他云产品。|
|[DescribeBackSourceCidr](/cn.zh-CN/API参考/DDoS高防新BGP&国际/系统配置与日志/DescribeBackSourceCidr.md)|查询DDoS高防的回源IP网段。|
|[DescribeOpEntities](/cn.zh-CN/API参考/DDoS高防新BGP&国际/系统配置与日志/DescribeOpEntities.md)|查询DDoS高防（新BGP）的操作日志。|
|[DescribeDefenseRecords](/cn.zh-CN/API参考/DDoS高防新BGP&国际/系统配置与日志/DescribeDefenseRecords.md)|查询DDoS高防（国际）的高级防护日志。|
|[DescribeAsyncTasks](/cn.zh-CN/API参考/DDoS高防新BGP&国际/系统配置与日志/DescribeAsyncTasks.md)|查询异步导出任务的详细信息，例如任务ID、任务开始和结束时间、任务状态、任务参数、任务结果等。|
|[CreateAsyncTask](/cn.zh-CN/API参考/DDoS高防新BGP&国际/系统配置与日志/CreateAsyncTask.md)|创建异步导出任务，例如导出网站业务转发规则、端口转发规则、会话保持和健康检查配置、DDoS防护策略、IP黑白名单。|
|[DeleteAsyncTask](/cn.zh-CN/API参考/DDoS高防新BGP&国际/系统配置与日志/DeleteAsyncTask.md)|删除异步导出任务。|

