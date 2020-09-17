# Pre-sales FAQ

This topic lists the frequently asked questions about pre-sales of Anti-DDoS services provided by Alibaba Cloud.

-   [Does Alibaba Cloud provide free Anti-DDoS services?](#section_efp_mmn_jqy)
-   [Can Anti-DDoS Pro and Anti-DDoS Premium be billed only when they are triggered to mitigate DDoS attacks?](#section_m8s_gd5_eg9)
-   [Do Anti-DDoS services have trial mitigation plans?](#section_wg7_bnp_3df)
-   [Can Anti-DDoS services protect external servers?](#section_1u2_dn0_g9w)
-   [Can Anti-DDoS Pro and Anti-DDoS Premium protect external servers that serve a domain name registered with Alibaba Cloud?](#section_q4x_2ok_6lj)
-   [Is Internet Content Provider \(ICP\) filing required for domain names that require the protection of Alibaba Cloud Anti-DDoS services?](#section_9bx_18t_onl)
-   [What are the regions supported by Anti-DDoS services?](#section_9u1_jw0_9uk)
-   [Do Anti-DDoS Pro and Anti-DDoS Premium have limits on the number of protected domain names?](#section_l5k_aap_dp6)
-   [Do Anti-DDoS instances support wildcard domains?](#section_e1z_5d2_lpq)
-   [What are the prerequisites for setting up protection with Anti-DDoS Premium?](#section_7z8_jpd_yww)
-   [Does the basic protection bandwidth provided by an Anti-DDoS Pro instance indicate the maximum mitigation capacity?](#section_6ij_iny_4zm)

## Does Alibaba Cloud provide free Anti-DDoS services?

Yes. Alibaba Cloud automatically activates Anti-DDoS Origin Basic for Alibaba Cloud users. This service can mitigate DDoS attacks of up to 5 Gbit/s. Anti-DDoS Origin Basic is free of charge. You do not need to purchase, activate, or configure this service. For more information, see [What is Anti-DDoS Origin](/intl.en-US/Product Introduction on Alibaba DDoS Protection/Anti-DDoS Origin/What is Anti-DDoS Origin?.md).

Alibaba Cloud does not provide unlimited mitigation free of charge. Bandwidth resources are essential to DDoS attack mitigation. Bandwidth usage takes the highest proportion in mitigation service billing. Alibaba Cloud pays for bandwidth resources provided by Internet Service Providers \(ISPs\), such as China Telecom, China Unicom, and China Mobile. The bandwidth costs include bandwidth usage caused by mitigating DDoS attacks. Alibaba Cloud Security helps users mitigate DDoS attacks of up to 5 Gbit/s free of charge. When the size of the DDoS attacks exceeds 5 Gbit/s, Alibaba Cloud Security automatically blocks all network traffic sent to the attacked domain name in case a large number of mitigation fees are incurred.

## Can Anti-DDoS Pro and Anti-DDoS Premium be billed only when they are triggered to mitigate DDoS attacks?

No. Anti-DDoS Pro and Anti-DDoS Premium are billed on a subscription basis. You must purchase Anti-DDoS instances and complete the payment before you can use the instances to mitigate DDoS attacks within the subscription duration.

## Do Anti-DDoS services have trial mitigation plans?

-   Anti-DDoS Origin: Anti-DDoS Origin Basic is a free migration plan that is used to mitigate DDoS attacks of up to 5 Gbit/s for public IP addresses of Alibaba Cloud. Anti-DDoS Origin Enterprise is a charged mitigation plan and no free trial is available.

    **Note:** We recommend that you use Anti-DDoS Origin Basic to test your network and then upgrade your service to Anti-DDoS Origin Enterprise. The upgrading process is completely transparent and does not add any changes to the network and connections.

-   Anti-DDoS Pro/Premium: Anti-DDoS Pro and Anti-DDoS Premium work with scrubbing centers built on Anti-DDoS-exclusive servers to mitigate volumetric DDoS attacks. The mitigation cost is high. No free trial service is provided.

## Can Anti-DDoS services protect external servers?

Yes. Anti-DDoS Pro and Anti-DDoS Premium can protect Alibaba Cloud Elastic Compute Service \(ECS\) instances and external servers against DDoS attacks. Anti-DDoS Pro and Anti-DDoS Premium instances redirect requests to origin servers over the Internet. Therefore, Anti-DDoS instances can protect servers that can be accessed over the Internet, such as external servers, servers deployed on Alibaba Cloud, and on-premises servers. For more information, see [What are Anti-DDoS Pro and Anti-DDoS Premium](/intl.en-US/Product Introduction on Alibaba DDoS Protection/What are Anti-DDoS Pro and Anti-DDoS Premium?.md).

## Can Anti-DDoS Pro and Anti-DDoS Premium protect external servers that serve a domain name registered with Alibaba Cloud?

Yes. Anti-DDoS Pro and Anti-DDoS Premium can protect Alibaba Cloud ECS instances and external servers that serve domain names registered with Alibaba Cloud or third-party domain name service providers.

## Is Internet Content Provider \(ICP\) filing required for domain names that require the protection of Alibaba Cloud Anti-DDoS services?

You must complete ICP filing for domain names that require the protection of Anti-DDoS Pro. ICP filing is not required when you use Anti-DDoS Premium to protect domain names. For more information, see [ICP filing application overview]().

## What are the regions supported by Anti-DDoS services?

-   Anti-DDoS Pro: protects workloads deployed in mainland China.
-   Anti-DDoS Premium: protects workloads deployed outside mainland China, including China \(Hong Kong\).

## Do Anti-DDoS Pro and Anti-DDoS Premium have limits on the number of protected domain names?

Yes.

-   By default, each Anti-DDoS Pro instance can protect up to 50 domain names, including subdomains and wildcard domains. The subdomains and wildcard domains must not belong to more than five top-level domains.
-   By default, each Anti-DDoS Premium instance can protect up to 10 domain names, including subdomains and wildcard domains. The subdomains and wildcard domains must not belong to more than one top-level domain.

**Note:** You can increase domain name quota when you purchase an Anti-DDoS instance. Each Anti-DDoS Pro or Anti-DDoS Premium instance can protect a maximum of 200 domain names. For more information, see [Purchase mitigation plans for Anti-DDoS Pro and Anti-DDoS Premium](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Purchase mitigation plans for Anti-DDoS Pro and Anti-DDoS Premium.md).

## Do Anti-DDoS instances support wildcard domains?

Yes. You can add wildcard domains on the **Website Config** page. For more information, see [Add a website](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Use domains/Add a website.md).

A wildcard DNS record is specified by using an asterisk \(\*\) as the leftmost part of a domain name. The record points all matching subdomains to the domain name. For example, a wildcard DNS record specified by using \*.taobao.com points all subdomains that match \*.taobao.com to www.taobao.com.

## What are the prerequisites for setting up protection with Anti-DDoS Premium?

If you want to use Anti-DDoS Premium to protect a website, you must add the domain name of the website to Anti-DDoS Premium. If you want to use Anti-DDoS Premium to protect a non-website service, you only need to connect the service port to your Anti-DDoS Premium instance.

## Does the basic protection bandwidth provided by an Anti-DDoS Pro instance indicate the maximum mitigation capacity?

The basic protection bandwidth provided by an Anti-DDoS Pro instance is the guaranteed bandwidth for handling both normal and malicious traffic of the workloads protected by the Anti-DDoS Pro instance. All network traffic from the public network must first pass through the Anti-DDoS traffic scrubbing centers. Malicious traffic is filtered out, and only normal traffic is forwarded to the origin server.

