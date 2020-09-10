# Overview

Alibaba Cloud provides you with various anti-DDoS solutions. You can select an appropriate solution as required. This topic describes the anti-DDoS solutions and application scenarios.

The anti-DDoS solutions include Anti-DDoS Origin Basic, Anti-DDoS Origin Enterprise, Anti-DDoS Pro, Anti-DDoS Premium, and GameShield. Anti-DDoS Origin Basic is provided free of charge. The following table describes the solutions.

**Note:** To obtain a tailored security solution, contact Alibaba Cloud pre-sales customer service by telephone.

|Solution|Description|Scenario|Defense against DDoS attacks|
|--------|-----------|--------|----------------------------|
|Anti-DDoS Origin Basic|Anti-DDoS Origin Basic is provided with a anti-DDoS capacity of up to 5 Gbit/s free of charge based on the Alibaba Cloud services, such as Elastic Compute Service \(ECS\), Server Load Balancer \(SLB\), Web Application Firewall \(WAF\), and Elastic IP Address \(EIP\), that you purchase.|Services that have basic requirements on security. You can use Anti-DDoS Origin Basic after you purchase an Alibaba Cloud service. We recommend that you use other security solutions for additional protection if your services require high security.|Up to 5 Gbit/s|
|[Anti-DDoS Origin Enterprise](/intl.en-US/Product Introduction on Alibaba DDoS Protection/Anti-DDoS Origin/What is Anti-DDoS Origin?.md)|Anti-DDoS Origin Enterprise is designed to improve the anti-DDoS protection capabilities of Alibaba Cloud services. The services include ECS, SLB, WAF, and EIP.You can perform simple configurations to load the security capabilities provided by Anti-DDoS Origin Enterprise to Alibaba Cloud services.

|-   Services that are latency-sensitive, such as online videos and live Q&A.
-   Services that use a large number of ports, domain names, and IP addresses.

|The unlimited mitigation feature is supported. For more information, see [Unlimited protection](/intl.en-US/DDoS Protection Guide/Traffic scrubbing and black hole.md).|
|[Anti-DDoS Pro and Anti-DDoS Premium](/intl.en-US/Product Introduction on Alibaba DDoS Protection/What are Anti-DDoS Pro and Anti-DDoS Premium?.md)|Anti-DDoS Pro and Anti-DDoS Premium are provided to protect Internet-based servers against volumetric distributed denial-of-service \(DDoS\) attacks. Servers that are not on Alibaba Cloud can also be protected.After configurations, you can forward your business traffic to Anti-DDoS Pro or Anti-DDoS Premium for scrubbing. Only normal traffic is forwarded to the origin server. This ensures the stability and reliability of the origin server.

|-   Financial, e-commerce, and portal websites.
-   Internet egresses of government departments, portals, and open platforms.
-   Important live streaming and sales promotions.
-   Scenarios when your services encounter attacks and blackmailing from competitors.
-   Scenarios when mobile apps encounter spam user registration, empty box scams, and fraud traffic.

|-   Burstable protection is provided by Anti-DDoS Pro. For more information, see [Burstable protection](/intl.en-US/DDoS Protection Guide/Traffic scrubbing and black hole.md).
-   Advanced protection is provided by Anti-DDoS Premium. For more information, see [Advanced mitigation](/intl.en-US/DDoS Protection Guide/Traffic scrubbing and black hole.md). |
|[GameShield](/intl.en-US/Product Introduction/What is Game Shield.md)|GameShield is provided to protect against DDoS and HTTP flood attacks in the gaming industry.GameShield can effectively defend against volumetric DDoS attacks that involve terabytes of traffic and that can be prevented by using Anti-DDoS Pro or Anti-DDoS Premium. It can also defend against the TCP-based HTTP flood attacks specific to the gaming industry.

|-   Scenarios when gaming services encounter heavy-traffic bandwidth suppression.
-   Scenarios when gaming services encounter attacks from a large number of zombies over a long period of time.

|The capability of mitigating DDoS attacks at Tbit/s level is provided.|

