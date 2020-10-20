# What is Anti-DDoS Origin?

Anti-DDoS Origin is a protection service that improves protection capacity against DDoS attacks for resources. These resources include Elastic Compute Service \(ECS\) instances, Server Load Balancer \(SLB\) instances, elastic IP addresses \(EIPs\), and Web Application Firewall \(WAF\) instances. Anti-DDoS Origin directly protects cloud services and imposes no limits, which is different from Anti-DDoS Pro and Anti-DDoS Premium. You do not need to change the IP addresses of the resources that you want to protect. You do not need to consider the limits on the number of Layer-4 ports and the number of Layer-7 domain names. Anti-DDoS Origin is easy to deploy. You only need to bind the IP address of a resource that you want to protect with Anti-DDoS Origin. The protection for the resource only requires a few minutes to take effect.

## Limits

Anti-DDoS Origin Enterprise instances are available only in mainland China. If you want to purchase an Anti-DDoS Origin Enterprise instance outside mainland China, you must submit a [submit a ticket](https://workorder-intl.console.aliyun.com/?#/ticket/add/?productId=80) or contact sales personnel. After the request is approved, you can purchase an Anti-DDoS Origin Enterprise instance.

## How Anti-DDoS Origin works

Anti-DDoS Origin protects the public IP addresses of Alibaba Cloud resources against Layer 3 and Layer 4 volumetric attacks. These resources include ECS instances, SLB instances, WAF instances, and EIPs. When the traffic exceeds the default scrubbing threshold that is predefined in Anti-DDoS Origin, traffic scrubbing is automatically triggered to mitigate DDoS attacks.

Anti-DDoS Origin adopts passive scrubbing as a major protection policy and active blocking as an auxiliary policy to mitigate DDoS attacks. It employs conventional technologies such as reverse detection, blacklist and whitelist, and packet compliance. These technologies allow protected resources to work normally under continuous attacks. Anti-DDoS Origin deploys a DDoS attack detection and scrubbing system at the egress of an Alibaba Cloud data center. This system is deployed in bypass mode.

## Scenarios

Anti-DDoS Origin is suitable for applications that are deployed on Alibaba Cloud. It meets the requirements for you when your service scale is large and you are sensitive to network quality. You have low possibility of exposure to DDoS attacks. However, you may suffer significant economic losses if interruption or compromised response time of services occurs due to DDoS attacks. Anti-DDoS Origin allows you to improve protection capacity against DDoS attacks at a minimum cost. It also reduces the potential risk of DDoS attacks that target your services.

Anti-DDoS Origin is suitable for the following resources:

-   Resources that resides on Alibaba Cloud.
-   A large number of public IP addresses.
-   Services that require high clean bandwidth or queries per second \(QPS\).
-   IPv6-based inbound requests.

## Editions

Anti-DDoS Origin provides two editions: Anti-DDoS Origin Basic and Anti-DDoS Origin Enterprise.

-   Anti-DDoS Origin Basic provides basic protection against DDoS attacks for public IP addresses of Alibaba Cloud resources free of charge. Anti-DDoS Origin Basic provides protection capacity of no more than 5 Gbit/s. For more information, see [View black hole triggering thresholds in Anit-DDoS Origin Basic](/intl.en-US/DDoS Protection Guide/Product Introduction/View black hole triggering thresholds in Anit-DDoS Origin Basic.md).
-   Anti-DDoS Origin Enterprise provides shared and unlimited protection for public IP addresses of Alibaba Cloud resources after you purchase an instance. Unlimited protection provides defense against DDoS attacks. The unlimited protection capacity is based on the total number of resources that reside in an anti-DDoS cluster. The unlimited protection capacity increases with the increase of the overall network capacity of Alibaba Cloud. The increased protection capacity is free of charge.

    -   After you purchase an Anti-DDoS Origin Enterprise instance, the instance protects the public IP addresses of Alibaba Cloud resources. These resources include ECS instances, SLB instances, EIPs, and WAF instances.
    -   Anti-DDoS Origin Enterprise mitigates DDoS attacks for servers in on-premises data centers outside China and cloud assets based on Classless Inter-Domain Routing \(CIDR\) blocks. It also provides on-demand Anti-DDoS Origin instances. You can contact sales personnel to purchase on-demand instances.
    For more information about the billing methods of Anti-DDoS Origin, see [Billing methods of Anti-DDoS Origin](/intl.en-US/Pricing/Billing methods of Anti-DDoS Origin.md).


## Benefits

Anti-DDoS Origin provides the following benefits:

-   Allows you to immediately use the service after you purchase an instance. Supports quick deployment within one minute. Anti-DDoS Origin directly protects your cloud services. This eliminates the need to deploy mitigation plans and switch IP addresses.
-   Provides burstable protection capacity. When your assets experience volumetric DDoS attacks, Anti-DDoS Origin uses all resources that reside in a region to provide unlimited protection.
-   Adopts Alibaba Cloud Border Gateway Protocol \(BGP\) bandwidth resources across different Internet Service Providers \(ISPs\). These ISPs include China Telecom, China Unicom, China Mobile, CERNET, and Great Wall Broadband. You can obtain fast access to the networks of these ISPs by using only one IP address.
-   Provides protection bandwidth as required. This can ensure service continuity and security for big promotions, event releases, and important services.
-   Supports protection capacity sharing among multiple IP addresses. This enhances protection capacity for multiple IP addresses.
-   Protects IPv6 networks in multiple regions. For more information, see [View black hole triggering thresholds in Anit-DDoS Origin Basic](/intl.en-US/DDoS Protection Guide/Product Introduction/View black hole triggering thresholds in Anit-DDoS Origin Basic.md).

