# Use Anti-DDoS Origin Enterprise and Anti-DDoS Pro

This topic describes how to use Anti-DDoS Origin Enterprise and Anti-DDoS Pro. This solution provides effective protection for your services against distributed denial of service \(DDoS\) attacks without compromising service continuity. To use Anti-DDoS Origin Enterprise and Anti-DDoS Pro, you can create a scheduling rule for Sec-Traffic Manager of Anti-DDoS Pro to achieve tiered protection.

## Background information

Anti-DDoS Origin Enterprise provides protection against DDoS attacks for specific Alibaba Cloud resources. These resources include Elastic Compute Service \(ECS\) instances, Server Load Balancer \(SLB\) instances, elastic IP addresses \(EIPs\), and Web Application Firewall \(WAF\) instances. Anti-DDoS Origin Enterprise directly protects Alibaba Cloud resources. You do not need to change the IP addresses of resources that you want to protect. You also do not need to limit the number of Layer 4 ports and the number of Layer 7 domain names. Anti-DDoS Origin Enterprise provides out-of-the-box features and elastic protection. If your services encounter volumetric DDoS attacks, Anti-DDoS Origin Enterprise uses all resources that reside in a region to provide unlimited protection. Anti-DDoS Origin Enterprise provides unlimited protection, such as protection against DDoS attacks peaked up to hundreds of Gbit/s.

Anti-DDoS Pro provides a maximum of 1.5 Tbit/s bandwidth to implement BGP-based DDoS mitigation with a support for 8 lines. The BGP-based DDoS mitigation with a support for 8 lines can be implemented only in regions inside mainland China. Anti-DDoS Pro protects your services from volumetric DDoS attacks peaked up to Tbit/s. Anti-DDoS Pro forwards DDoS attack traffic to scrubbing centers based on DNS records. Anti-DDoS Pro provides high-quality BGP bandwidth resources for China Telecom, China Unicom, China Mobile, China Education and Research Network \(CERNET\), and other Internet service providers \(ISPs\) in mainland China. The average latency is about 20 ms.

To enable interaction between Anti-DDoS Origin Enterprise and Anti-DDoS Pro, you can create a scheduling rule for Sec-Traffic Manager of Anti-DDoS Pro. This rule allows you to use Anti-DDoS Origin Enterprise for daily protection against common DDoS attacks. This rule triggers a switchover from Anti-DDoS Origin Enterprise to Anti-DDoS Pro when volumetric DDoS attacks occur.

## Solution overview

This solution allows you to use both Anti-DDoS Origin Enterprise and Anti-DDoS Pro. This solution supports protection for all assets, transparent deployment without extra latencies, and protection against volumetric DDoS attacks. It also helps control costs.

If you want to use this solution, purchase an Anti-DDoS Origin Enterprise instance to protect a maximum of 255 IP addresses of a specific region and enable unlimited protection. Anti-DDoS Origin Enterprise provides a protection bandwidth that ranges from 100 Gbit/s to 300 Gbit/s based on regions.You must also purchase an Anti-DDoS Pro instance as a backup to defend against DDoS attacks of greater than 300 Gbit/s. After you create a scheduling rule, all cloud resources are added to Sec-Traffic Manager for centralized management. If blackhole filtering is triggered by Anti-DDoS Origin Enterprise, Sec-Traffic Manager automatically switches traffic over to Anti-DDoS Pro.

This solution provides the following features:

-   Anti-DDoS Origin Enterprise provides multi-region account-level protection without extra latencies. You do not need to change the IP addresses of cloud resources and business structures.
-   Anti-DDoS Origin Enterprise provides protection bandwidth that ranges from 100 Gbit/s to 300 Gbit/s based on regions. Anti-DDoS Pro is used to defend against DDoS attacks of greater than 300 Gbit/s.
-   If blackhole filtering is triggered, a switchover is automatically performed from Anti-DDoS Origin Enterprise to Anti-DDoS Pro based on DNS records. A switchover requires 1 to 3 minutes or 5 to 10 minutes to complete based on the deployment region of local DNS servers.
-   Express Connect circuits are provided for back-to-origin traffic. This eliminates the effect of blackhole filtering.

After you use Anti-DDoS Origin Enterprise and Anti-DDoS Pro, SLB, ECS, or WAF instances are under the protection of Anti-DDoS Origin Enterprise without extra latencies. If volumetric attacks occur, blackhole filtering is triggered by Anti-DDoS Origin Enterprise. In this case, Sec-Traffic Manager switches traffic from Anti-DDoS Origin Enterprise to Anti-DDoS Pro, which forwards inbound traffic to a scrubbing center but has a latency of about 20 ms. If the attack stops, inbound traffic is forwarded back to SLB, ECS, or WAF instances, and Anti-DDoS Origin Enterprise starts to provide protection.

-   If the local DNS servers are deployed in mainland China, the switchover requires 5 to 10 minutes.

    **Note:** If the local DNS servers are deployed outside mainland China, the switchover requires 1 to 3 minutes.

-   If protection is switched over to Anti-DDoS Pro, the blackhole filtering threshold is limited to the maximum protection bandwidth of Anti-DDoS Pro. Anti-DDoS Pro provides basic protection of up to 30 Gbit/s and elastic protection of up to 300 Gbit/s. You can also submit a [submit a ticket](https://workorder-intl.console.aliyun.com/?#/ticket/add/?productId=80) to upgrade the protection bandwidth to 1 Tbit/s or higher.
-   After the attack stops, Anti-DDoS Pro is not immediately switched back to Anti-DDoS Origin Enterprise. You can configure the intervals at which Sec-Traffic Manager performs switchovers. The default interval is 120 minutes \(two hours\). This configuration allows you to avoid frequent switchovers due to continuous attacks and ensures service continuity.

## Activate and configure Anti-DDoS Origin Enterprise

Create an Anti-DDoS Origin Enterprise instance and add Alibaba Cloud resources to the instance for protection. Make sure that these resources and the instance are located in the same region. These resources include ECS, SLB, and WAF instances, and EIPs.

**Note:**

-   If the public IP addresses of resources are used to provide services, make sure that the network specifications and specified scrubbing threshold that is related to each resource meet your business requirements. You can view the scrubbing threshold for each resource in the [Anti-DDoS Origin console](https://yundun.console.aliyun.com/?p=ddos).
-   Before sales promotions, you must estimate the peak bandwidth and inform Alibaba Cloud technical support. This allows you to avoid traffic scrubbing or throttling by mistake and reduces the impact on your business.

1.  Create an Anti-DDoS Origin Enterprise instance.

    For more information, see [Purchase an Anti-DDoS Origin Enterprise instance](/intl.en-US/Anti-DDoS Origin User Guide/Purchase an Anti-DDoS Origin Enterprise instance.md).

2.  Add the IP address of your origin server to the Anti-DDoS Origin Enterprise instance for protection.

    For more information, see [Add a cloud service to Anti-DDoS Origin Enterprise for protection](/intl.en-US/Anti-DDoS Origin User Guide/Instances/Add a cloud service to Anti-DDoS Origin Enterprise for protection.md).


## Configure Anti-DDoS Pro and Sec-Traffic Manager

Create an Anti-DDoS Pro instance of the Professional plan, add a forwarding rule, and create a scheduling rule for Sec-Traffic Manager. After the configuration is complete, inbound traffic is forwarded to the address pointed by the Canonical Name \(CNAME\) record of Sec-Traffic Manager.

1.  Create an Anti-DDoS Pro instance of the Professional plan.

    For more information, see [Purchase an Anti-DDoS Pro instance](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Purchase mitigation plans for Anti-DDoS Pro and Anti-DDoS Premium.md).

2.  Add a domain to the Anti-DDoS Pro instance of the Professional plan.

    For more information, see [Add a website](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Use domains/Add a website.md).

    **Note:** After you add the forwarding rule for a domain, you do not need to modify the DNS record.

3.  Create a scheduling rule for Sec-Traffic Manager to achieve **tiered protection**.

    For more information, see [Create a tiered protection rule](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Sec-Traffic Manager/Create a tiered protection rule.md).

    After you create the rule, you can obtain a CNAME record of Sec-Traffic Manager in the **General** rule list.

4.  Update the DNS record of your domain. Visit the website of your DNS provider to change the DNS record so that traffic is forwarded to the CNAME record of Sec-Traffic Manager.


