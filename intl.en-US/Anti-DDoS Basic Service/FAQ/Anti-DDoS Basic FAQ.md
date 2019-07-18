# Anti-DDoS Basic FAQ {#concept_40049_zh .concept}

Currently, every ECS instance has Anti-DDoS Basic enabled by default. When the web traffic of an ECS instance exceeds the specified DDoS threshold, the Anti-DDoS cleansing device starts to clean the traffic.

-   [Does Anti-DDoS Basic defend against SYN flood attacks?](#)
-   [Can I select a time period for viewing the Anti-DDoS protection results?](#)
-   [Why did not Alibaba Cloud Security Anti-DDoS Basic defend against the 20 MB attack that my ECS server suffered?](#)
-   [Why can not a black hole be canceled immediately?](#)

## Does Anti-DDoS Basic defend against SYN flood attacks? {#2 .section}

Yes, Anti-DDoS Basic can defend against SYN flood attacks.

## Can I select a time period for viewing the Anti-DDoS protection results? {#3 .section}

Yes. Alibaba Cloud Security Anti-DDoS Basic console supports queries of DDoS attack events in the last 24 hours.

## Why did not Alibaba Cloud Security Anti-DDoS Basic defend against the 20 MB attack that my ECS server suffered? {#4 .section}

Alibaba Cloud Security Anti-DDoS Basic is a public anti-DDoS service. It won’t block low-traffic attacks \(lower than 100 MB\). We recommend that you optimize your server performance or install Cloud Lock or other host firewalls to handle the attacks of the traffic lower than 100 MB.

## Why can not a black hole be canceled immediately? {#6 .section}

Black holes last for 30 minutes to 24 hours for a vast majority of users. If a user is under frequent attacks, Alibaba Cloud may impose penalties by increasing black hole frequency.

Black hole is a service that Alibaba Cloud purchases from operators who have explicit restrictions on black hole removal time. That is why black hole cannot typically be canceled immediately.

