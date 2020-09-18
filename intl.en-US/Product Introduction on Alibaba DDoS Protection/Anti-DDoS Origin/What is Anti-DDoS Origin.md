# What is Anti-DDoS Origin

Anti-DDoS Origin is a protection service that improves protection capacity against distributed denial of service \(DDoS\) attacks for resources. These resources include Elastic Compute Service \(ECS\) instances, Server Load Balancer \(SLB\) instances, elastic IP addresses \(EIPs\), and Web Application Firewall \(WAF\) instances. Anti-DDoS Origin directly protects cloud services and imposes no limits, which is different from Anti-DDoS Pro and Anti-DDoS Premium. You do not need to change the IP addresses of the resources that you want to protect. You do not need to consider the limits on the number of Layer-4 ports and the number of Layer-7 domain names. Anti-DDoS Origin is easy to deploy. You need to only bind the IP address of a resource that you want to protect with Anti-DDoS Origin. The protection for the resource only requires a few minutes to take effect.

## How Anti-DDoS Origin works

Anti-DDoS Origin protects the public IP addresses of Alibaba Cloud resources against common DDoS attacks. These resources include ECS instances, SLB instances, WAF instances, and EIPs. Common DDoS attacks include but are not limited to SYN flood attacks, ACK flood attacks, UDP flood attacks, ICMP flood attacks, and amplification attacks \(such as SSDP, NTP, and Memcached amplification attacks\). For SYN flood attacks, Anti-DDoS Origin can effectively mitigate large packet attacks but is less effective in mitigating small packet attacks.

Anti-DDoS Origin adopts passive scrubbing as a major protection strategy and active blocking as an auxiliary strategy to mitigate DDoS attacks. It employs conventional technologies such as reverse detection, blacklist and whitelist, and packet compliance. These technologies allow protected resources to work normally under continuous attacks. Anti-DDoS Origin deploys a DDoS attack detection and scrubbing system at the egress of an Alibaba Cloud data center. This system is deployed in bypass mode. The following figure shows the network topology of Anti-DDoS Origin.

![Network topology](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79444/154503671934069_en-US.png)

## Editions

Anti-DDoS Origin is offered in two editions: Anti-DDoS Origin Basic and Anti-DDoS Origin Enterprise.

-   Anti-DDoS Origin Basic provides basic protection against DDoS attacks for public IP addresses of Alibaba Cloud resources free of charge. Anti-DDoS Origin Basic provides protection capacity of no more than 5 Gbit/s. For more information, see [View black hole triggering thresholds in Anit-DDoS Origin Basic](/intl.en-US/Anti-DDoS Origin User Guide/Black hole policies/View black hole triggering thresholds in Anit-DDoS Origin Basic.md).
-   Anti-DDoS Origin Enterprise provides shared and unlimited protection for public IP addresses of Alibaba Cloud resources after you purchase an instance. Unlimited protection provides defense against DDoS attacks. The unlimited protection capacity is based on the total number of resources that reside in an anti-DDoS cluster. The unlimited protection capacity increases with the increase of the overall network capacity of Alibaba Cloud. The increased protection capacity is free of charge.

    -   After you purchase an Anti-DDoS Origin Enterprise instance, the instance protects the public IP addresses of Alibaba Cloud resources. These resources include ECS instances, SLB instances, EIPs, and WAF instances.
    -   Anti-DDoS Origin Enterprise mitigates DDoS attacks for servers in on-premises data centers outside China and cloud assets based on CIDR blocks. It also provides on-demand Anti-DDoS Origin instances. You can contact sales personnel to purchase on-demand instances.
    For more information about the billing methods of Anti-DDoS Origin, see [Billing methods of Anti-DDoS Origin](/intl.en-US/Pricing/Billing methods of Anti-DDoS Origin.md).


## Benefits

Anti-DDoS Origin provides the following benefits:

-   Allows you to immediately use the service after you purchase an instance. Supports quick deployment within one minute. Anti-DDoS Origin directly protects your cloud services. This eliminates the need to deploy mitigation plans and switch IP addresses.
-   Provides scalable protection capacity. When your assets experience large-scale DDoS attacks, Anti-DDoS Origin uses all resources that reside in a region to provide unlimited protection.
-   Adopts Alibaba Cloud Border Gateway Protocol \(BGP\) bandwidth resources across different Internet Service Providers \(ISPs\). These ISPs include China Telecom, China Unicom, China Mobile, CERNET, and Great Wall Broadband. You can obtain fast access to the networks of these ISPs by using only one IP address.
-   Provides protection bandwidth as required. This can ensure business continuity and security for big promotions, event releases, and important services.
-   Supports protection capacity sharing among multiple IP addresses. This enhances protection capacity for multiple IP addresses.
-   Protects IPv6 networks in multiple regions. For more information, see [View black hole triggering thresholds in Anit-DDoS Origin Basic](/intl.en-US/Anti-DDoS Origin User Guide/Black hole policies/View black hole triggering thresholds in Anit-DDoS Origin Basic.md).

## Limits

Anti-DDoS Origin Enterprise instances are available only in mainland China. If you want to purchase an Anti-DDoS Origin Enterprise instance outside mainland China, you must submit a [submit a ticket](https://workorder-intl.console.aliyun.com/?#/ticket/add/?productId=80) or contact sales personnel. After the request is approved, you can purchase an Anti-DDoS Origin Enterprise instance.

For more information about regions where Anti-DDoS Origin is available, see [Regions and zones](/intl.en-US/Product Introduction/Regions and zones.md).

