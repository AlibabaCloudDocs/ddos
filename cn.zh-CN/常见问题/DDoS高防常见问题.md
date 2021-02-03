# DDoS高防常见问题

本文列举了DDoS高防（新BGP&国际）服务相关的常见问题。

-   [DDoS高防实例过期后会怎样？](#section_urg_0kt_c2b)
-   [DDoS高防业务带宽说明](#section_i7x_ce0_9a8)
-   [超过DDoS高防业务带宽会有什么影响？](#section_j32_xy6_kkn)
-   [DDoS高防被黑洞后，支持手动解封吗？](#section_p5r_kk3_ocs)
-   [DDoS高防的回源IP地址有哪些？](#section_woj_jo4_6di)
-   [DDoS高防是否会自动将DDoS高防的回源IP地址加入安全组？](#section_rob_5uy_808)
-   [DDoS高防服务中的源站IP可以填写内网IP吗？](#section_dej_vzv_e83)
-   [修改DDoS高防服务的源站IP是否有延迟？](#section_xrr_p7z_rki)
-   [DDoS高防实例配置了多个网站业务，被攻击后如何查看是哪个网站受到攻击？](#section_x1f_4c0_3zj)
-   [DDoS高防是否支持健康检查？](#section_dth_0eg_s56)
-   [DDoS高防配置多个源站时如何进行负载均衡？](#section_wel_rpm_7j6)
-   [DDoS高防服务是否支持会话保持？](#section_quj_81r_c1a)
-   [DDoS高防服务的会话保持是如何实现的？](#section_2l2_myz_dst)
-   [DDoS高防的四层TCP默认连接超时时间是多长？](#section_d4i_dvu_z2t)
-   [DDoS高防的HTTP或HTTPS默认连接超时时间是多久？](#section_w5s_6lw_8my)
-   [DDoS高防服务是否支持IPv6协议？](#section_rlz_9lo_tbd)
-   [DDoS高防服务是否支持Websocket协议？](#section_tip_66a_ulc)
-   [DDoS高防服务是否支持HTTPS双向认证？](#section_cfz_baq_wws)
-   [为什么老版本浏览器和安卓客户端无法正常访问HTTPS站点？](#section_l32_vr6_x4j)
-   [DDoS高防支持的SSL协议和加密套件有哪些？](#section_kkt_vxb_72v)
-   [DDoS高防支持的防护端口数和防护域名数有什么限制？](#section_jar_w1u_k7f)
-   [服务器的流量未达到清洗阈值，为何安全总览中会出现清洗流量？](#section_joj_hbi_7p8)
-   [DDoS高防服务是否支持接入采用NTLM协议认证的网站？](#section_wgn_qt3_mgb)

## DDoS高防实例过期后会怎样？

DDoS高防实例过期后无防御能力。

-   过期7天内转发规则配置正常生效，流量超限将触发流量限速，可能导致随机丢包。
-   过期7天后将停止业务流量转发。这种情况下，如果您的业务访问地址仍解析到DDoS高防实例，则业务将无法被访问到。

更多信息，请参见[实例到期说明](/cn.zh-CN/产品定价/DDoS高防（新BGP）计费方式.md)。

## DDoS高防业务带宽说明

DDoS高防实例的业务带宽指接入当前实例防护业务的正常业务流量，取入流量和出流量其中的较大值，单位：Mbps。

您可以在[DDoS高防控制台](https://yundun.console.aliyun.com/?p=ddoscoo)的**实例管理**页面对实例进行升级，增大当前实例的**业务带宽**。更多信息，请参见[升级DDoS高防实例规格](/cn.zh-CN/DDoS高防（新BGP&国际）用户指南/资产管理/升级DDoS高防实例规格.md)。

## 超过DDoS高防业务带宽会有什么影响？

如果您的业务流量超过购买的DDoS高防实例的业务带宽，将触发流量限速，可能导致随机丢包。

## DDoS高防被黑洞后，支持手动解封吗？

-   DDoS高防（新BGP）：支持。每个阿里云账号每天共拥有五次黑洞解封的机会，每天零点自动恢复成五次。更多信息，请参见[黑洞解封](/cn.zh-CN/DDoS高防（新BGP&国际）用户指南/防护设置/基础设施DDoS防护/黑洞解封.md)。
-   DDoS高防（国际）：暂不支持。

## DDoS高防的回源IP地址有哪些？

您可以在[DDoS高防控制台](https://yundun.console.aliyun.com/?p=ddoscoo)的**域名接入**页面查看DDoS高防的回源IP网段。更多信息，请参见[放行DDoS高防回源IP](/cn.zh-CN/DDoS高防（新BGP&国际）用户指南/接入DDoS高防/放行DDoS高防回源IP.md)。

![回源IP网段](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/3848909951/p130910.png)

## DDoS高防是否会自动将DDoS高防的回源IP地址加入安全组？

不会。如果您的源站部署了防火墙或第三方的主机安全防护软件，您需要将DDoS高防（新BGP）的回源IP网段添加至相应的白名单中。更多信息，请参见[放行DDoS高防回源IP](/cn.zh-CN/DDoS高防（新BGP&国际）用户指南/接入DDoS高防/放行DDoS高防回源IP.md)。

## DDoS高防服务中的源站IP可以填写内网IP吗？

不可以。DDoS高防通过公网进行回源，不支持直接填写内网IP。

## 修改DDoS高防服务的源站IP是否有延迟？

有延迟。修改DDoS高防服务已防护的源站IP后，需要大约五分钟生效，建议您在业务低峰期进行变更操作。更多信息，请参见[更换源站ECS公网IP](/cn.zh-CN/DDoS高防（新BGP&国际）用户指南/接入DDoS高防/更换源站ECS公网IP.md)。

## DDoS高防实例配置了多个网站业务，被攻击后如何查看是哪个网站受到攻击？

针对DDoS高防的大流量DDoS攻击行为，从数据包层面是无法分辨具体是哪个网站受到攻击。建议您使用多组DDoS高防实例，将您的网站分别部署在不同的DDoS高防实例上即可查看各个网站遭受攻击的情况。

## DDoS高防是否支持健康检查？

支持。

-   网站业务默认开启健康检查。
-   非网站业务默认不开启健康检查，但可以通过DDoS高防控制台开启，具体操作请参见[配置健康检查](/cn.zh-CN/DDoS高防（新BGP&国际）用户指南/接入DDoS高防/端口接入/配置健康检查.md)。

关于健康检查的更多信息，请参见[健康检查概述](/cn.zh-CN/传统型负载均衡CLB/用户指南/健康检查/健康检查概述.md)。

## DDoS高防配置多个源站时如何进行负载均衡？

-   网站业务通过源地址HASH方式进行负载均衡。
-   非网站业务可通过加权轮询的方式轮询转发。

## DDoS高防服务是否支持会话保持？

支持。非网站业务可以通过DDoS高防控制台开启会话保持，具体操作请参见[配置会话保持](/cn.zh-CN/DDoS高防（新BGP&国际）用户指南/接入DDoS高防/端口接入/配置会话保持.md)。

## DDoS高防服务的会话保持是如何实现的？

开启会话保持后，在会话保持的设定期间内，DDoS高防服务会把同一IP的请求持续发往源站中的一台服务器。但是，如果客户端的网络环境发生变化（例如从有线切成无线、4G网络切成无线等），由于IP变化会导致会话保持失效。

## DDoS高防的四层TCP默认连接超时时间是多长？

900秒。非网站业务可以通过DDoS高防控制台调整该设置，具体操作请参见[配置会话保持](/cn.zh-CN/DDoS高防（新BGP&国际）用户指南/接入DDoS高防/端口接入/配置会话保持.md)。

## DDoS高防的HTTP或HTTPS默认连接超时时间是多久？

120秒。

## DDoS高防服务是否支持IPv6协议？

暂不支持。

## DDoS高防服务是否支持Websocket协议？

支持。更多信息，请参见[DDoS高防WebSocket配置]()。

## DDoS高防服务是否支持HTTPS双向认证？

-   网站接入方式不支持HTTPS双向验证。
-   非网站接入且使用TCP转发方式时，支持HTTPS双向验证。

## 为什么老版本浏览器和安卓客户端无法正常访问HTTPS站点？

可能是因为客户端不支持SNI认证，请确认客户端是否支持SNI认证。关于SNI认证可能引发的问题，请参见[SNI可能引发的HTTPS访问异常]()。

## DDoS高防支持的SSL协议和加密套件有哪些？

支持的SSL协议包括：TLS 1.0、TLS 1.1、TLS 1.2、TLS 1.3。

支持的加密套件包括：

-   ECDHE-ECDSA-AES128-GCM-SHA256
-   ECDHE-ECDSA-AES256-GCM-SHA384
-   ECDHE-ECDSA-AES128-SHA256
-   ECDHE-ECDSA-AES256-SHA384
-   ECDHE-RSA-AES128-GCM-SHA256
-   ECDHE-RSA-AES256-GCM-SHA384
-   ECDHE-RSA-AES128-SHA256
-   ECDHE-RSA-AES256-SHA384
-   AES128-GCM-SHA256
-   AES256-GCM-SHA384
-   AES128-SHA256 AES256-SHA256
-   ECDHE-ECDSA-AES128-SHA
-   ECDHE-ECDSA-AES256-SHA
-   ECDHE-RSA-AES128-SHA
-   ECDHE-RSA-AES256-SHA
-   AES128-SHA AES256-SHA
-   DES-CBC3-SHA

更多信息，请参见[自定义TLS安全策略](/cn.zh-CN/DDoS高防（新BGP&国际）用户指南/接入DDoS高防/域名接入/自定义TLS安全策略.md)。

## DDoS高防支持的防护端口数和防护域名数有什么限制？

-   防护端口数：
    -   一个DDoS高防（新BGP）实例默认支持50个端口，支持扩展至400个。
    -   一个DDoS高防（国际）实例默认支持5个端口，支持扩展至400个。
-   支持域名数：
    -   一个DDoS高防（新BGP）实例默认支持50个域名配置，最大可扩展至200个。
    -   一个DDoS高防（国际）实例默认支持10个域名配置，最大可扩展至200个。

## 服务器的流量未达到清洗阈值，为何安全总览中会出现清洗流量？

对于已接入DDoS高防服务的业务，DDoS高防将自动过滤网络流量中存在的一些畸形包（例如SYN小包、SYN标志位异常等不符合TCP协议的数据包），使您的业务服务器无需浪费资源处理这些明显的畸形包。这类被过滤的畸形包也将被计入清洗流量中，因此即使您的服务器流量未达清洗阈值，仍可能出现清洗流量。

## DDoS高防服务是否支持接入采用NTLM协议认证的网站？

不支持。经DDoS高防转发的访问请求可能无法通过源站服务器的NTLM认证，客户端将反复出现认证提示。建议您的网站采用其他方式进行认证。

