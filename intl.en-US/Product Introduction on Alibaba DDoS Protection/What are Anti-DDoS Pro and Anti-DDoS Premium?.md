# What are Anti-DDoS Pro and Anti-DDoS Premium?

Anti-DDoS Pro and Anti-DDoS Premium are proxy-based mitigation services provided by Alibaba Cloud to mitigate DDoS attacks. These services can be used to protect network servers against volumetric DDoS attacks. To protect servers against volumetric and resource exhaustion DDoS attacks, Anti-DDoS Pro and Anti-DDoS Premium forward traffic to the Alibaba Cloud anti-DDoS network by using DNS resolution.

## How Anti-DDoS Pro and Anti-DDoS Premium work

You can connect your services to Anti-DDoS Pro or Anti-DDoS Premium by using domain names or ports. The domain names or service IP addresses are mapped to the IP or CNAME addresses of Anti-DDoS Pro or Anti-DDoS Premium instances based on the forwarding rules that you configured. This way, traffic is rerouted to the instances.

Inbound traffic passes through the anti-DDoS data center. In the traffic scrubbing center, malicious network traffic is filtered out, and normal network traffic is forwarded back to the origin server by using forwarding ports. This ensures stable access to the origin servers.

## Anti-DDoS Pro and Anti-DDoS Premium

Alibaba Cloud provides the following two services based on the region where your servers are deployed:

-   [Anti-DDoS Pro](): applies to scenarios in which your servers are deployed in **mainland China**. It uses eight Border Gateway Protocol \(BGP\) lines at the Tbit/s level to protect servers against volumetric DDoS attacks.
-   [Anti-DDoS Premium](): applies to scenarios in which your servers are deployed **outside mainland China**. Backed by the world-leading distributed near-origin traffic scrubbing capabilities, Anti-DDoS Premium mitigates unlimited DDoS attacks.

For more information, see [Differences between the features of Anti-DDoS Pro and Anti-DDoS Premium](#section_kxj_agd_elk).

## Benefits

Anti-DDoS Pro and Anti-DDoS Premium are more stable and easier to deploy than traditional DDoS mitigation solutions. These services rely on high-quality BGP networks and intelligent protection technologies to provide strong and precise protection with high availability.

-   Easy deployment

    You can connect your services to Anti-DDoS Pro or Anti-DDoS Premium by using domain names or ports. The process requires up to five minutes. You do not need to install hardware or software or configure routers.

-   Massive protection bandwidth

    Anti-DDoS Pro and Anti-DDoS Premium each can mitigate a minimum of 8 Tbit/s of DDoS attacks in mainland China, and a minimum of 2 Tbit/s outside mainland China. These services protect servers against DDoS attacks at the network layer, transport layer, and application layer.

-   Precise protection

    Anti-DDoS Pro and Anti-DDoS Premium provide precise protection against various attacks on transactions, encryption, Layer 7 applications, smart terminals, and online services.

-   Intelligent protection

    Anti-DDoS Pro and Anti-DDoS Premium automatically optimize protection algorithms and learn service traffic baselines from the protection analysis of volumetric and resource exhaustion DDoS attacks. This enables the services to identify malicious IP addresses, and then scrub and filter out attack traffic.

-   Burstable protection

    Anti-DDoS Pro and Anti-DDoS Premium support burstable protection. You can configure this feature in the Anti-DDoS Pro or Anti-DDoS Premium console. The settings take effect within seconds, and you do not need to install additional devices. Your services are not interrupted during the process. Therefore, you do not need to make any adjustments to your services.

-   Origin server security ensured

    Anti-DDoS Pro and Anti-DDoS Premium hide the IP addresses of origin servers. This way, attackers cannot identify the address of your origin server. This increases the security of your origin server.

-   Protection against volumetric DDoS attacks

    Volumetric DDoS attacks at the transport layer congest networks, leave data centers unavailable, and interrupt or paralyze your services. Based on technologies such as proxy, detection, rebound, authentication, blacklist and whitelist, and packet compliance, Anti-DDoS Pro and Anti-DDoS Premium employ IP reputation investigation, near-origin traffic scrubbing, and in-depth packet analysis of network fingerprints, user behavior, and content characteristics. These technologies block and filter out threats based on custom rules. This enables the protected services to provide external services even under sustained attacks.

-   Protection against resource exhaustion DDoS attacks \(HTTP flood attacks\)

    Anti-DDoS Pro and Anti-DDoS Premium integrate intelligent protection engines to protect against resource exhaustion DDoS attacks when application-layer services are interrupted under attacks. These services also support URL-level threat filtering at custom frequencies to improve the protection success rate, protection efficiency, and work efficiency of O&M personnel. Intelligent protection engines provide effective protection by:

    -   Learning your traffic to obtain traffic characteristics.
    -   Dynamically generating normal service baselines.
    -   Quickly discovering exceptions of traffic and characteristics.
    -   Automatically participating in the analysis of attack characteristics.
    -   Automatically generating a combination of multi-dimensional policies.
    -   Dynamically executing or canceling protection policy instructions.
-   Stability and high availability
    -   Anti-DDoS Pro and Anti-DDoS Premium use high-availability network protection clusters to prevent single-point failure and redundancy. The processing capabilities of Anti-DDoS Pro and Anti-DDoS Premium can be scaled up. They also offer automated detection and attack policy matching to provide real-time protection and a scrubbing service availability of up to 99.99%.
    -   Anti-DDoS Pro and Anti-DDoS Premium monitor the CPU and memory resources of all servers and the inbound traffic that is forwarded to the traffic scrubbing center. This ensures the availability of the data center. They also monitor the availability of server engines and have automatic offline and recovery mechanisms.
    -   Anti-DDoS Pro and Anti-DDoS Premium monitor the availability of back-to-origin links and automatically switch to secondary links when primary links are unstable, which ensures link availability.
    -   Anti-DDoS Pro and Anti-DDoS Premium perform health checks on protected origin servers. If an origin server is not running at optimal capacity, the service traffic is forwarded to another origin server. They also monitor the HTTP status codes of origin servers and initiate back-to-origin or switchover operations when errors are detected.
-   Traffic rerouting

    Anti-DDoS Pro and Anti-DDoS Premium forward traffic based on cloud service-specific security events and DNS resolution. They enable DDoS mitigation for vulnerable cloud services by connecting these cloud services to themselves and disable DDoS mitigation for secure cloud services. You can customize the forwarding templates of Anti-DDoS Pro and Anti-DDoS Premium to automatically schedule DDoS mitigation based on the status of cloud services.


## Scenarios

Anti-DDoS Pro and Anti-DDoS Premium are suitable for finance websites, e-commerce websites, portal websites, Internet egresses of government networks, portals, and open platforms. They provide DDoS mitigation for important live streaming and sales promotions. Anti-DDoS Pro and Anti-DDoS Premium protect against malicious attacks and ransom-driven attacks, and prevent mobile applications from spam user registration, brushing, and fraudulent traffic.

We recommend that you use Anti-DDoS Pro and Anti-DDoS Premium in the following scenarios when security risks occur in the preceding industries:

-   Ransom-driven DDoS attacks occur.
-   DDoS attacks make your services inaccessible, and urgent protection is required to recover your services.
-   DDoS attacks frequently occur. Continuous protection against DDoS attacks is required to ensure service stability.

## Differences between the features of Anti-DDoS Pro and Anti-DDoS Premium

The following table describes the features that are supported by Anti-DDoS Pro and Anti-DDoS Premium. The features that are not listed in the table are supported by both Anti-DDoS Pro and Anti-DDoS Premium.

**Note:** The table allows you to distinguish between Anti-DDoS Pro and Anti-DDoS Premium. We recommend that you choose Anti-DDoS Pro for servers deployed in **mainland China** and Anti-DDoS Premium for servers deployed **outside mainland China**.

A check sign \(√\) indicates that the feature is supported and a cross sign \(×\) indicates that the feature is not supported.

|Feature|Description|Anti-DDoS Pro|Anti-DDoS Premium|References|
|-------|-----------|-------------|-----------------|----------|
|Instances - Mainland China Acceleration \(MCA\)

|MCA must be used with Anti-DDoS Premium Insurance or Unlimited Plan. If your server is deployed outside mainland China, you can purchase an MCA instance to accelerate your services for users in mainland China.|×|√|[Mainland China Acceleration billing methods](/intl.en-US/Pricing/Anti-DDoS premium billing methods/Mainland China Acceleration billing methods.md)[Configure Anti-DDoS Premium MCA](t79672.md#) |
|Instances -Secured Mainland China Acceleration \(Sec-MCA\)

|Anti-DDoS Premium supports Sec-MCA. This allows you to accelerate access from users in mainland China to services in regions outside mainland China.|×|√|[Sec-MCA billing methods](/intl.en-US/Pricing/Anti-DDoS premium billing methods/Sec-MCA billing methods.md)[Configure Anti-DDoS Premium Sec-MCA](t1909936.md#) |
|Instances - Global Advanced Mitigation

|Global advanced mitigation must be used with Anti-DDoS Premium Insurance Plan that provides two advanced mitigation sessions. If the two advanced mitigation sessions are exhausted, you can purchase more global advanced mitigation sessions.|×|√|[Billing methods for global advanced mitigation](/intl.en-US/Pricing/Anti-DDoS premium billing methods/Billing methods for global advanced mitigation.md)[Purchase global advanced mitigation](t1893702.md#) |
|Website Config - Enable HTTP/2

|In the **Enter Site Information** step, you can add a domain name and turn on **Enable HTTP/2**.|√|×|[Add a website](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Use domains/Add a website.md)|
|Website Config - Cname Reuse

|In the **Enter Site Information** step, you can turn on **CNAME Reuse**.|×|√|[CNAME reuse](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Use domains/CNAME reuse.md)|
|Sec-traffic manager - Network Acceleration

|You can select **Network Acceleration** when you add a rule on the **General** tab in the console.|×|√|[Overview](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Sec-Traffic Manager/Overview.md)|
|Sec-Traffic Manager - Sec-MCA

|You can select **Sec-MCA** when you add a rule on the **General** tab in the console.|×|√|[Overview](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Sec-Traffic Manager/Overview.md)|
|Protection for Infrastructure - Diversion from Origin Server

|The Diversion from Origin Server policy blocks network traffic transmitted from regions outside mainland China over China Telecom or China Unicom lines.|√|×|[Configure diversion from the origin server](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Protection settings/Protection for infrastructure/Configure diversion from the origin server.md)|
|Protection for infrastructure - Deactivate Blackhole Status

|You can manually deactivate blackhole filtering in the console to recover services.|√|×|[Deactivate a black hole](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Protection settings/Protection for infrastructure/Deactivate a black hole.md)|
|Investigation - Operation Logs

|You can view the logs of the last 30 days on the Operation Logs page.|√|×|[t586627.md\#](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Query and analysis/Operation logs.md)|
|Investigation - Adv. Mitigation Logs

|You can view the logs of the last 30 days on the Adv. Mitigation Logs page.|×|√|[Query advanced mitigation logs](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Query and analysis/Query advanced mitigation logs.md)|

## DDoS cost protection

Anti-DDoS Pro and Anti-DDoS Premium support **DDoS cost protection**. These services safeguard against costs incurred due to the usage spikes on the protected Elastic Compute Service \(ECS\) or Server Load Balancer \(SLB\) instances caused by DDoS attacks. If the costs of any protected resources increase due to DDoS attacks, you can submit a[ticket](https://workorder-intl.console.aliyun.com/?#/ticket/add/?productId=80) to obtain a voucher.

