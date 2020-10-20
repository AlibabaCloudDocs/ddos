# Pre-sales FAQ

This topic provides answers to some commonly asked questions about pre-sales of Alibaba Cloud Anti-DDoS.

-   [Does Alibaba Cloud Anti-DDoS provide free services?](#section_efp_mmn_jqy)
-   [Can Anti-DDoS Pro and Anti-DDoS Premium be billed only when they mitigate DDoS attacks?](#section_m8s_gd5_eg9)
-   [Does Anti-DDoS have trial mitigation plans?](#section_wg7_bnp_3df)
-   [Can Anti-DDoS Pro and Anti-DDoS Premium protect servers that are not deployed on Alibaba Cloud?](#section_1u2_dn0_g9w)
-   [Can Anti-DDoS Pro and Anti-DDoS Premium protect servers that are not deployed on Alibaba Cloud but have domains registered with Alibaba Cloud?](#section_q4x_2ok_6lj)
-   [Do I need to complete ICP filing for a domain before I can use Anti-DDoS Pro or Anti-DDoS Premium?](#section_9bx_18t_onl)
-   [What are the regions supported by Anti-DDoS Pro and Anti-DDoS Premium?](#section_9u1_jw0_9uk)
-   [Do Anti-DDoS Pro and Anti-DDoS Premium have limits on the number of protected domains?](#section_l5k_aap_dp6)
-   [Do Anti-DDoS Pro and Anti-DDoS Premium support wildcard domains?](#section_e1z_5d2_lpq)
-   [What are the prerequisites for activating Anti-DDoS Premium?](#section_7z8_jpd_yww)
-   [Does the basic protection bandwidth provided by Anti-DDoS Pro apply to all traffic or only attack traffic?](#section_6ij_iny_4zm)

## Does Alibaba Cloud Anti-DDoS provide free services?

Yes, Alibaba Cloud Anti-DDoS provides free services. Anti-DDoS Origin Basic is activated for every Alibaba Cloud user. Anti-DDoS Origin Basic mitigates DDoS attacks of up to 5 Gbit/s free of charge. You do not need to purchase, activate, or configure this service. For more information, see [What is Anti-DDoS Origin?](/intl.en-US/Product Introduction on Alibaba DDoS Protection/Anti-DDoS Origin/What is Anti-DDoS Origin?.md).

Alibaba Cloud does not provide unlimited protection free of charge. Bandwidth resources are essential to DDoS attack mitigation. Bandwidth usage takes the highest proportion in mitigation service billing. Alibaba Cloud pays for bandwidth resources provided by Internet Service Providers \(ISPs\), such as China Telecom, China Unicom, and China Mobile. The bandwidth costs include bandwidth charges incurred from mitigating DDoS attacks. Anti-DDoS Origin Basic mitigates DDoS attacks of up to 5 Gbit/s free of charge. When the volume of the DDoS attacks exceeds 5 Gbit/s, Anti-DDoS Origin Basic blocks all traffic to the victim to avoid additional mitigation fees.

## Can Anti-DDoS Pro and Anti-DDoS Premium be billed only when they mitigate DDoS attacks?

No, Anti-DDoS Pro and Anti-DDoS Premium are still billed when they are not working. Anti-DDoS Pro and Anti-DDoS Premium are billed on a subscription basis. You must purchase Anti-DDoS Pro or Anti-DDoS Premium instances and complete the payment before you can use the instances to mitigate DDoS attacks. The protection takes effect for the duration of your subscription.

## Does Anti-DDoS have trial mitigation plans?

-   Anti-DDoS Origin: Anti-DDoS Origin Basic is a free mitigation plan and provides up to 5 Gbit/s protection for public IP addresses of Alibaba Cloud resources. Anti-DDoS Origin Enterprise is a paid mitigation plan and no free trial is provided.

    **Note:** We recommend that you use Anti-DDoS Origin Basic to test the mitigation capability of Anti-DDoS Origin and then upgrade your service to Anti-DDoS Origin Enterprise. The upgrade process is completely transparent and does not affect your network and connections.

-   Anti-DDoS Pro and Anti-DDoS Premium: Anti-DDoS Pro and Anti-DDoS Premium rely on dedicated data centers to provide traffic scrubbing services. This incurs high costs. No free trial is provided.

## Can Anti-DDoS Pro and Anti-DDoS Premium protect servers that are not deployed on Alibaba Cloud?

Yes, Anti-DDoS Pro and Anti-DDoS Premium can protect servers that are not deployed on Alibaba Cloud and Alibaba Cloud Elastic Compute Service \(ECS\) instances from DDoS attacks. Anti-DDoS Pro and Anti-DDoS Premium instances redirect requests to origin servers over the Internet. Therefore, Anti-DDoS Pro and Anti-DDoS Premium instances can protect servers that are accessible over the Internet, such as servers deployed on Alibaba Cloud, servers that are deployed on third-party cloud platforms, and on-premises servers. For more information, see [What are Anti-DDoS Pro and Anti-DDoS Premium?](/intl.en-US/Product Introduction on Alibaba DDoS Protection/What are Anti-DDoS Pro and Anti-DDoS Premium?.md).

## Can Anti-DDoS Pro and Anti-DDoS Premium protect servers that are not deployed on Alibaba Cloud but have domains registered with Alibaba Cloud?

Yes, Anti-DDoS Pro and Anti-DDoS Premium can protect servers that are not deployed on Alibaba Cloud but have domains registered with Alibaba Cloud. Both Anti-DDoS Pro and Anti-DDoS Premium provide DDoS mitigation for Alibaba Cloud ECS instances or servers that are not deployed on Alibaba Cloud. Anti-DDoS Pro and Anti-DDoS Premium also provide DDoS mitigation for domains that are registered by using Alibaba Cloud Domains or a third-party domain service.

## Do I need to complete ICP filing for a domain before I can use Anti-DDoS Pro or Anti-DDoS Premium?

If you use Anti-DDoS Pro, you must complete Internet Content Provider \(ICP\) filing for the domain. If you use Anti-DDoS Premium, ICP filing is not required.

## What are the regions supported by Anti-DDoS Pro and Anti-DDoS Premium?

-   Anti-DDoS Pro: protects servers deployed in mainland China.
-   Anti-DDoS Premium: protects servers deployed outside mainland China, including China \(Hong Kong\).

## Do Anti-DDoS Pro and Anti-DDoS Premium have limits on the number of protected domains?

Yes, Anti-DDoS Pro and Anti-DDoS Premium have limits on the number of protected domains.

-   By default, each Anti-DDoS Pro instance supports a maximum of 50 domains, only 5 of which can be second-level domains.
-   By default, each Anti-DDoS Premium instance supports a maximum of 10 domains, only 1 of which can be second-level domains.

**Note:** You can increase the number of domains when you purchase an Anti-DDoS Pro or Anti-DDoS Premium instance. Each Anti-DDoS Pro or Anti-DDoS Premium instance supports a maximum of 200 domains. For more information, see [Purchase mitigation plans for Anti-DDoS Pro and Anti-DDoS Premium](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Purchase mitigation plans for Anti-DDoS Pro and Anti-DDoS Premium.md).

## Do Anti-DDoS Pro and Anti-DDoS Premium support wildcard domains?

Yes, Anti-DDoS Pro and Anti-DDoS Premium support wildcard domains. You can add wildcard domains on the **Website Config** page. For more information, see [Add a website](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Use domains/Add a website.md).

A wildcard DNS record is specified by using an asterisk \(\*\) as the leftmost part of a domain name. The record resolves all matching subdomains to the domain. For example, when you specify \*.taobao.com as a DNS record, all subdomains that match \*.taobao.com are resolved to www.taobao.com.

## What are the prerequisites for activating Anti-DDoS Premium?

If you want to use Anti-DDoS Premium to protect a website, you must add the domain of the website to Anti-DDoS Premium. If you want to use Anti-DDoS Premium to protect a non-website service, you only need to add the service port to your Anti-DDoS Premium instance.

## Does the basic protection bandwidth provided by Anti-DDoS Pro apply to all traffic or only attack traffic?

The basic protection bandwidth provided by an Anti-DDoS Pro instance is the guaranteed bandwidth for handling both normal and attack traffic of the workloads protected by the instance. All traffic must first pass through the Anti-DDoS traffic scrubbing centers. Attack traffic is filtered out, and only normal traffic is forwarded to the origin server.

