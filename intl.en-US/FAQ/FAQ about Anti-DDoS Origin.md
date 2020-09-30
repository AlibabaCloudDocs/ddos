# FAQ about Anti-DDoS Origin

This topic provides answers to some commonly asked questions about Anti-DDoS Origin Basic and Enterprise.

**Basic**

-   [Can Anti-DDoS Origin Basic provide protection against SYN flood attacks?](#section_ko2_ey0_bp5)
-   [Why does Anti-DDoS Origin Basic not protect my Elastic Compute Service \(ECS\) instance against an attack of 20 Mbit/s?](#section_q3a_mpd_o57)
-   [Why cannot I manually deactivate blackhole filtering for an Anti-DDoS Origin Basic instance?](#section_zrm_w6y_hu9)
-   [Why the traffic data in the Anti-DDoS Origin console differs from that in Cloud Monitor and other cloud services?](#section_vyh_xyv_alf)

**Enterprise**

-   [What is the billing difference between unlimited protection of Anti-DDoS Origin Enterprise and burstable protection of Anti-DDoS Pro?](#section_v2d_krt_2gb)
-   [What do I do if blackhole filtering is activated for an IP address that is protected by Anti-DDoS Origin Enterprise?](#section_4ul_k1i_wku)
-   [What do I do if I deployed an Anti-DDoS Origin Enterprise instance in the wrong region?](#section_avc_evz_qrm)
-   [When I add the IP address of a service, the system prompts that the number of IP addresses reaches the upper limit. What do I do?](#section_7i7_fh1_hj8)
-   [What do I do if the error message "The IP address does not belong to your account" is displayed when I add an IP address to Anti-DDoS Origin?](#section_cn4_rwu_ya6)

## Can Anti-DDoS Origin Basic provide protection against SYN flood attacks?

Yes, Anti-DDoS Origin Basic can provide protection against SYN flood attacks.

## Why does Anti-DDoS Origin Basic not protect my Elastic Compute Service \(ECS\) instance against an attack of 20 Mbit/s?

If the size of attacks is lower than 100 Mbit/s, Anti-DDoS Origin Basic is free of charge. Anti-DDoS Origin Basic does not provide protection. We recommend that you optimize your server or install a host-based firewall, such as Yunsuo, to protect against attacks lower than 100 Mbit/s.

## Why cannot I manually deactivate blackhole filtering for an Anti-DDoS Origin Basic instance?

In most cases, blackhole filtering lasts 30 minutes to 24 hours. If your services are under frequent volumetric DDoS attacks, Alibaba Cloud may extend the blackhole filtering duration.

Alibaba Cloud purchases blackhole filtering from Internet Service Providers \(ISPs\), who preset the duration of blackhole filtering. You cannot manually deactivate blackhole filtering for Anti-DDoS Origin Basic before the duration ends. if you want to deactivate blackhole filtering, we recommend that you purchase Anti-DDoS Origin Enterprise, Anti-DDoS Pro, or Anti-DDoS Premium instances. For more information, see [What is Anti-DDoS Origin](/intl.en-US/Product Introduction on Alibaba DDoS Protection/Anti-DDoS Origin/What is Anti-DDoS Origin.md) and [What are Anti-DDoS Pro and Anti-DDoS Premium?](/intl.en-US/Product Introduction on Alibaba DDoS Protection/What are Anti-DDoS Pro and Anti-DDoS Premium?.md).

## Why the traffic data in the Anti-DDoS Origin console differs from that in Cloud Monitor and other cloud services?

In most cases, the traffic in the Anti-DDoS Origin console is higher than that in Cloud Monitor and other cloud services.

Assume that your ECS instance is under DDoS attacks, which triggers traffic scrubbing when the traffic reaches 2.5 Gbit/s. Alibaba Cloud notifies you that the traffic scrubbing provided by Anti-DDoS Origin Basic instance is triggered. However, the Cloud Monitor console shows that the inbound bandwidth of the elastic IP address \(EIP\) associated with your ECS instance is 1.2 Gbit/s during the traffic scrubbing.

The reasons for this difference include:

-   Anti-DDoS Origin collects traffic data before traffic scrubbing is triggered, whereas Cloud Monitor collects traffic data after traffic scrubbing is triggered.
-   Anti-DDoS Origin monitors all network traffic destined for your ECS instance, including malicious traffic, whereas Cloud Monitor monitors only normal traffic.
-   Anti-DDoS Origin and Cloud Monitor collect traffic data at different intervals. Anti-DDoS Origin collects traffic data at intervals of seconds so that DDoS attacks can be detected at the earliest opportunity. Cloud Monitor collects the traffic data of EIPs at intervals of minutes and displays the data in charts in the Cloud Monitor console.
-   Anti-DDoS Origin and Cloud Monitor collect traffic data from different sources. Anti-DDoS Origin collects the traffic data of EIPs from the border gateway devices between Alibaba Cloud and the Internet, whereas Cloud Monitor collects the traffic data of EIPs from the devices that forward traffic.

**Note:** The difference in traffic data can happen to Alibaba Cloud services, such as ECS, Server Load Balancer \(SLB\), EIP, and NAT Gateway, that are Infrastructure as a Service \(IaaS\) and support Internet access.

## What is the billing difference between unlimited protection of Anti-DDoS Origin Enterprise and burstable protection of Anti-DDoS Pro?

-   Anti-DDoS Origin Enterprise provides the [Unlimited protection](/intl.en-US/DDoS Protection Guide/Traffic scrubbing and black hole.md) capability. If DDoS attacks are detected, the Anti-DDoS Origin Enterprise instance uses all the protection capacity for the region where it resides to defend against the DDoS attacks. Unlimited protection is included in the Anti-DDoS Origin Enterprise instance that you have purchased. No additional fee is charged for unlimited protection.
-   Burstable protection of Anti-DDoS Pro is charged based on the peak value of the burstable protection bandwidth on the current day. For more information, see [Burstable protection \(pay-as-you-go on a daily basis\)](/intl.en-US/Pricing/Anti-DDoS Pro billing methods.md).

## What do I do if blackhole filtering is activated for an IP address that is protected by Anti-DDoS Origin Enterprise?

You can manually deactivate blackhole filtering.

-   For more information about how to manually deactivate blackhole filtering for a protected IP address, see [Deactivate a black hole](/intl.en-US/Anti-DDoS Origin User Guide/Black hole policies/Deactivate a black hole.md).
-   You can also configure automated response to and deactivation of blackhole filtering. For more information, see [Best practices for automatic deactivation of black holes](/intl.en-US/Anti-DDoS Origin User Guide/Best Practices/Best practices for automatic deactivation of black holes.md).

## What do I do if I deployed an Anti-DDoS Origin Enterprise instance in the wrong region?

If the IP address that you want to protect is not in the same region as the purchased Anti-DDoS Origin Enterprise instance, submit a [submit a ticket](https://workorder-intl.console.aliyun.com/?#/ticket/add/?productId=80) to apply for a refund. After you receive the refund, you can purchase a new instance to protect the IP address.

## When I add the IP address of a service, the system prompts that the number of IP addresses reaches the upper limit. What do I do?

If the number of protected IP addresses reaches the value of **Protected IP Addresses** that you specify on the Anti-DDoS Origin Enterprise buy page, increase the value of **Protected IP Addresses** or purchase a new Anti-DDoS Origin Enterprise instance. For more information, see [Upgrade instance types](/intl.en-US/Anti-DDoS Origin User Guide/Instances/Upgrade instance types.md) and [Purchase an Anti-DDoS Origin Enterprise instance](/intl.en-US/Anti-DDoS Origin User Guide/Purchase an Anti-DDoS Origin Enterprise instance.md).

## What do I do if the error message "The IP address does not belong to your account" is displayed when I add an IP address to Anti-DDoS Origin?

If you receive the error message **The IP address does not belong to your account** when you add an IP address in the Anti-DDoS Origin console, perform the following steps to troubleshoot the error:

1.  Verify that you have entered the correct IP address.
2.  Verify that the IP address is located in the same region as the purchased Anti-DDoS Origin Enterprise instance.
3.  If you want to protect the IP address of a WAF instance, verify that Anti-DDoS Origin Enterprise is available in the region of the WAF instance. For more information about regions where you can activate Anti-DDoS Origin Enterprise, see [Limits](/intl.en-US/Product Introduction on Alibaba DDoS Protection/Anti-DDoS Origin/What is Anti-DDoS Origin.mdsection_kgh_eoe_rkh).

