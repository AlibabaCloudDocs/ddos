# Scenario-specific anti-DDoS solutions

Alibaba Cloud integrates advanced security technologies and years of experience in DDoS mitigation into a variety of commercial anti-DDoS solutions. You can select an anti-DDoS solution based on your service requirements. This topic describes how to select anti-DDoS solutions for different scenarios.

## Scenarios

|Scenario|Applicable scope|Description|Mitigation plan|
|--------|----------------|-----------|---------------|
|High-risk DDoS attacks \([Anti-DDoS Pro or Anti-DDoS Premium](/intl.en-US/Product Introduction on Alibaba DDoS Protection/What are Anti-DDoS Pro and Anti-DDoS Premium?.md) is recommended.\)|-   DDoS attacks occur on websites, Internet egresses of government networks, portals and open platforms, important live streaming activities, and sales promotions. These websites refer to financial, e-commerce, and portal websites.
-   Ransom-driven DDoS attacks occur.
-   DDoS attacks freeze your services and you want to recover your services at the earliest opportunity.
-   DDoS attacks frequently occur. Continuous protection against DDoS attacks is required to ensure service stability.
-   Mobile applications encounter spam user registration, brushing, and fraudulent traffic.

|Anti-DDoS Pro and Anti-DDoS Premium can protect Alibaba Cloud Elastic Compute Service \(ECS\) instances and servers that are not deployed on Alibaba Cloud from volumetric DDoS attacks. They can route network traffic to the Alibaba Cloud global anti-DDoS network by using DNS resolution, scrub volumetric and resource exhaustion attack traffic, and hide the IP addresses of origin servers.|Select a mitigation plan for Anti-DDoS Pro or Anti-DDoS Premium based on the following descriptions:-   [Anti-DDoS Pro Profession](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Purchase mitigation plans for Anti-DDoS Pro and Anti-DDoS Premium.md): applies to scenarios in which your servers are deployed **in mainland China** and your services are provided to users who are located **in mainland China**.
-   [Anti-DDoS Premium Insurance or Unlimited](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Purchase mitigation plans for Anti-DDoS Pro and Anti-DDoS Premium.md): applies to scenarios in which your servers are deployed **outside mainland China** and your services are provided to users who are located **outside mainland China**.
-   [Anti-DDoS Premium MCA](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Configure Anti-DDoS Premium MCA.md) or [Anti-DDoS Premium Sec-MCA](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Configure Anti-DDoS Premium Sec-MCA.md): applies to scenarios in which your servers are deployed **outside mainland China** and your services are provided to users who are located **in mainland China**. |
|Low-risk DDoS attacks on large-scale services \([Anti-DDoS Origin is recommended](/intl.en-US/Product Introduction on Alibaba DDoS Protection/Anti-DDoS Origin/What is Anti-DDoS Origin?.md).\)|-   Service resources are deployed on Alibaba Cloud.
-   Large-scale services are running. For example, the clean bandwidth is greater than 1 Gbit/s, and the queries per second \(QPS\) over HTTP and HTTPS is greater than 5,000.
-   A large number of public IP addresses need to be protected.
-   DDoS attacks occasionally occur.
-   IPv6-based inbound requests exist.

|Anti-DDoS Origin improves the DDoS mitigation capabilities of Alibaba Cloud services. These services include ECS, Server Load Balancer \(SLB\), Web Application Firewall \(WAF\), and Elastic IP Address \(EIP\). Anti-DDoS Origin uses the native protection network of Alibaba Cloud to mitigate volumetric DDoS attacks without changing the IP addresses of origin servers.|Select a mitigation plan for Anti-DDoS Origin based on the following descriptions:

-   Anti-DDoS Origin Basic is activated by default.
-   Anti-DDoS Origin Basic mitigates DDoS attacks of up to 5 Gbit/s. If this mitigation capability is insufficient to meet your service requirements, we recommend that you use [Anti-DDoS Origin Enterprise](/intl.en-US/Anti-DDoS Origin User Guide/Purchase an Anti-DDoS Origin Enterprise instance.md).
    -   [Anti-DDoS Origin Enterprise and SLB](/intl.en-US/Anti-DDoS Origin User Guide/Best Practices/Use Anti-DDoS Origin and SLB.md): applies to scenarios in which you want to mitigate only DDoS attacks. In these scenarios, you can use SLB to discard traffic whose protocol and port are not specified in the SLB listener to improve protection capabilities.
    -   [Anti-DDoS Origin Enterprise and WAF](/intl.en-US/Anti-DDoS Origin User Guide/Best Practices/Use Anti-DDoS Origin and WAF.md): applies to scenarios in which you want to mitigate DDoS attacks, web attacks, and HTTP flood attacks. In these scenarios, you can use WAF to mitigate HTTP flood attacks and Anti-DDoS Origin Enterprise to mitigate volumetric DDoS attacks to improve protection capabilities. |
|DDoS attacks on mobile applications \([GameShield](/intl.en-US/Product Introduction/What is Game Shield.md) is recommended.\)|-   Mobile gaming services are the main scenarios.
-   Services can integrate Alibaba Cloud SDKs.
-   Services require fine-grained protection for real-time data that is transmitted over custom transport protocols.
-   Services require accelerated network transmission.
-   Services require encrypted network transmission.
-   The sources of DDoS attacks need to be traced.

|GameShield can mitigate volumetric DDoS attacks and HTTP flood attacks in the gaming industry. GameShield integrates the lightweight Alibaba Cloud Security SDKs to eliminate DDoS attacks, HTTP flood attacks, and TCP flood attacks that are specific to the gaming industry faced by mobile applications.|None.|

## Service types

|Service type|Anti-DDoS Pro and Anti-DDoS Premium|Anti-DDoS Origin|GameShield|
|------------|-----------------------------------|----------------|----------|
|Websites|√|√|×|
|UDP-based services|√|×|√|
|Applications|√|√|×|
|Games|√|×|√ \(Recommended\)|

## DDoS attack types

Symbol description:

-   √: indicates that mitigation is supported
-   x: indicates that mitigation is not supported

|Attack type|Anti-DDoS Pro and Anti-DDoS Premium|Anti-DDoS Origin|GameShield|
|-----------|-----------------------------------|----------------|----------|
|Malformed packet attacks|√|√|√|
|Transport layer DDoS attacks|√|√Anti-DDoS Origin can mitigate SYN flood attacks \(packet fragment attacks\), but the mitigation capability is limited. In this case, we recommend that you use Anti-DDoS Pro or Anti-DDoS Premium.

|√|
|DNS DDoS attacks|√|×We recommend that you use [WAF and Anti-DDoS Origin Enterprise](/intl.en-US/Anti-DDoS Origin User Guide/Best Practices/Use Anti-DDoS Origin and WAF.md).

|×|
|Connection-based DDoS attacks|√|×We recommend that you use [WAF and Anti-DDoS Origin Enterprise](/intl.en-US/Anti-DDoS Origin User Guide/Best Practices/Use Anti-DDoS Origin and WAF.md).

|√|
|Application-layer attacks|√|×We recommend that you use [WAF and Anti-DDoS Origin Enterprise](/intl.en-US/Anti-DDoS Origin User Guide/Best Practices/Use Anti-DDoS Origin and WAF.md).

|×|

