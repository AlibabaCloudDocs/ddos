# Terms

Anti-DDoS Origin Basic provides basic protection against DDoS attacks. By default, Anti-DDoS Origin Basic is enabled for Alibaba Cloud resources that support Internet access, such as Elastic Compute Service \(ECS\) instances, Server Load Balancer \(SLB\) instances, and elastic IP addresses \(EIPs\), regardless of whether they are deployed in the classic network or virtual private clouds \(VPCs\). If the volume of Internet traffic destined for an IP address exceeds the specified scrubbing threshold, Anti-DDoS starts to scrub the traffic to ensure the availability of your service. If the traffic volume exceeds the maximum protection threshold, blackhole filtering is triggered. All Internet traffic to the IP address is temporarily blocked.

## traffic scrubbing

Anti-DDoS redirects traffic to a scrubbing device. The scrubbing device checks whether the traffic from specific IP addresses is normal and denies abnormal traffic. In addition, Anti-DDoS limits the volume of traffic destined for your server to mitigate damages. However, this may bring adverse impacts on normal traffic.

## blackhole filtering

If an ECS instance suffers from volumetric attacks and the traffic exceeds the maximum protection threshold of Anti-DDoS Origin Basic, blackhole filtering is triggered. When blackhole filtering is triggered for an ECS instance, all Internet traffic to the instance is blocked for a specific period of time. This period varies based on the attack status. The maximum protection threshold varies based on the region and vCPU configuration of the ECS instance. For more information, see [View black hole triggering thresholds in Anit-DDoS Origin Basic](/intl.en-US/DDoS Protection Guide/Product Introduction/View black hole triggering thresholds in Anit-DDoS Origin Basic.md). The following content describes basic information about blackhole filtering:

-   Condition to trigger blackhole filtering: The attack traffic on an ECS instance exceeds the maximum protection threshold of Anti-DDoS Origin Basic.
-   Duration: 30 minutes to 24 hours. The duration varies based on the attack status and the region where the protected resource resides.

    **Note:** The blackhole filtering duration and blackhole triggering threshold are automatically adjusted based on the security credibility level of your Alibaba Cloud account. A higher security credibility level indicates a shorter blackhole filtering duration and a higher blackhole triggering threshold.


After blackhole filtering stops, Anti-DDoS automatically starts traffic scrubbing to check whether the attacks still continue. If yes, blackhole filtering is triggered again. If no, the Internet access is restored. If the traffic of attacks is overwhelmingly large, it may affect the network stability of Alibaba Cloud data centers. Blackhole filtering cannot be manually stopped in Anti-DDoS Origin Basic.

If you want to immediately restore the Internet access, we recommend that you purchase an [Anti-DDoS Pro or Anti-DDoS Premium instance](https://www.alibabacloud.com/product/ddos).

Anti-DDoS Pro and Anti-DDoS Premium are value-added security services. They protect resources on Alibaba Cloud against volumetric DDoS attacks. You can redirect attack traffic to the IP address that you purchase for Anti-DDoS Pro or Anti-DDoS Premium. This ensures stability and reliability of your origin server.

## unlimited protection

Unlimited protection is provided by Anti-DDoS Origin Enterprise. The feature provides best-effort protection against DDoS attacks based on the network configuration and resource usage of the local anti-DDoS scrubbing center. The capability of unlimited protection is upgraded as the overall network capacity of Alibaba Cloud increases. You do not need to pay additional fees. For more information, see [Billing methods of Anti-DDoS Origin](/intl.en-US/Pricing/Billing methods of Anti-DDoS Origin.md).

## burstable protection

Burstable protection is provided by Anti-DDoS Pro of the Professional plan. You can configure the burstable protection bandwidth to defend against extra attack traffic that exceeds the basic protection bandwidth. If the volume of DDoS attacks exceeds the basic protection bandwidth but is smaller than the burstable protection bandwidth, burstable protection is triggered. You are charged additional fees on the day when burstable protection is triggered. For more information, see [Anti-DDoS Pro billing methods](/intl.en-US/Pricing/Anti-DDoS Pro billing methods.md).

## advanced mitigation

Advanced mitigation is provided by Anti-DDoS Premium of the Insurance or Unlimited mitigation plan. Advanced mitigation leverages anti-DDoS scrubbing centers of Alibaba Cloud outside mainland China to protect your resources against DDoS attacks. For more information, see [Billing methods of Insurance Plan and Unlimited Plan](/intl.en-US/Pricing/Anti-DDoS premium billing methods/Billing methods of Insurance Plan and Unlimited Plan.md).

## anycast

Anti-DDoS Premium uses the anycast method to forward DDoS attack traffic to the nearest anti-DDoS scrubbing centers of Alibaba Cloud around the world.

Anycast is a network addressing and routing method. Packets that are destined for an anycast IP address can be routed to a specific group of hosts identified by the anycast IP address.

Anti-DDoS Premium uses the anycast method to route access traffic to the nearest anti-DDoS scrubbing center that has protection capabilities. This way, Anti-DDoS Premium can provide efficient traffic scrubbing and burstable protection even if requests are highly concurrent and the network is congested.

![Anycast](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/2075021061/p38704.png)

Traffic that reaches the anycast IP address can be routed to multiple data centers. When access traffic arrives at the anycast IP address, the traffic is forwarded to different data centers based on configured traffic forwarding rules. In most cases, the access traffic is forwarded to the data center nearest to the traffic source.

Assume that the anycast IP address of an Anti-DDoS Premium instance is 170.x.x.x. All anti-DDoS scrubbing centers of Alibaba Cloud outside China advertise routes to this IP address. When data packets are sent to this IP address, the data packets are forwarded to the anti-DDoS scrubbing center through a route with the least hops. When a server in an anti-DDoS scrubbing center becomes unavailable, all scrubbing centers immediately advertise that this IP address is unavailable, and data packets are routed to the nearest anti-DDoS scrubbing center excluding this one.

By default, traffic from Hong Kong \(China\) is routed to the anti-DDoS scrubbing center of Alibaba Cloud in Hong Kong \(China\).

