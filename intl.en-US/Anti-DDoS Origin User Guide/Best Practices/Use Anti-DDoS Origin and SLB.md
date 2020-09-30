---
keyword: [Anti-DDoS Origin, Enterprise edition, SLB]
---

# Use Anti-DDoS Origin and SLB

This topic describes how to configure Server Load Balancer \(SLB\) and Anti-DDoS Origin to protect a website that is hosted on an Elastic Compute Service \(ECS\) instance. This combination provides better protection than Anti-DDoS Origin Enterprise alone.

-   An ECS instance is created and has web applications installed. For more information, see [Overview](/intl.en-US/Quick Start/Overview.md).
-   An Anti-DDoS Origin Enterprise instance is purchased. For more information, see [Purchase an Anti-DDoS Origin Enterprise instance](/intl.en-US/Anti-DDoS Origin User Guide/Purchase an Anti-DDoS Origin Enterprise instance.md).

To use Anti-DDoS Origin Enterprise to protect your website, we recommend that you deploy an SLB instance for the ECS instance where your website is hosted. Then, add the IP address of the SLB instance to Anti-DDoS Origin Enterprise for protection. The SLB instance can discard traffic whose protocol and port are not specified in the SLB listener. This helps mitigate distributed denial of service \(DDoS\) attacks. The preceding solution defends against different types of DDoS attacks, such as reflection attacks, User Datagram Protocol \(UDP\) flood attacks, and SYN flood attacks \(large packets\). The reflection attacks include Simple Service Discovery Protocol \(SSDP\), Network Time Protocol \(NTP\), and Memcached attacks.

The following procedure describes how to implement this combination solution.

**Note:** If your origin server is deployed with SLB, you only need to add the IP address of the SLB instance to Anti-DDoS Origin Enterprise for protection. For more information, see [Add a cloud service to Anti-DDoS Origin Enterprise for protection](/intl.en-US/Anti-DDoS Origin User Guide/Instances/Add a cloud service to Anti-DDoS Origin Enterprise for protection.md).

## Procedure

1.  Create an Internet-facing SLB instance.

    For more information, see [Create an SLB instance](/intl.en-US/User Guide/Instance/Create an SLB instance.md).

    When you create an Internet-facing SLB instance, note the following points:

    -   SLB does not support cross-region deployment. Make sure that the ECS instance and the SLB instance are in the same region.
    -   Anti-DDoS Origin provides protection only for Alibaba Cloud services that have public IP addresses. Therefore, you must create an Internet-facing SLB instance.
    For more information, see [Before you begin](/intl.en-US/Quick Start (New Console)/Before you begin.md).

    After an Internet-facing SLB instance is created, you can obtain the **IP Address** of the SLB instance on the **Instances** page in the [SLB console](https://slb.console.aliyun.com/slb).

2.  Configure the Internet-facing SLB instance.

    For more information, see [Configure an SLB instance](/intl.en-US/Quick Start (New Console)/Configure an SLB instance.md).

    When you configure the Internet-facing SLB instance, note the following points:

    -   In the **Protocol and Listener** step, specify only the listening protocol and ports that are required. You can select **TCP**, **UDP**, **HTTP**, or **HTTPS**. Traffic whose protocol and port are not specified in the SLB listener is discarded and not forwarded to the backend ECS instance.
    -   In the **Backend Servers** step, select the instance where your website is hosted.
    **Note:** The Internet-facing SLB instance communicates with the backend ECS instance over the internal network. Therefore, we recommend that you disable Internet access to the backend ECS instance after you configure the SLB instance. Make sure that the SLB instance functions properly.

    After the SLB instance is configured, the SLB instance forwards requests from a client to the backend ECS instance based on the existing configurations.

3.  Change the DNS settings.

    -   If your website is accessed by using its IP address, you can add the IP address of the Internet-facing SLB instance obtained in Step 1 as the IP address of your website. In this case, you do not need to change the DNS settings.
    -   If your website is accessed by using its domain name, you must resolve the domain name to the IP address of the SLB instance obtained in Step 1. For more information, see [Resolve a domain name](/intl.en-US/Quick Start (New Console)/Resolve a domain name.md).
4.  Add the IP address of the SLB instance to the Anti-DDoS Origin Enterprise instance for protection.

    For more information, see [Add a cloud service to Anti-DDoS Origin Enterprise for protection](/intl.en-US/Anti-DDoS Origin User Guide/Instances/Add a cloud service to Anti-DDoS Origin Enterprise for protection.md).

    After you add the IP address of the SLB instance, the Anti-DDoS Origin Enterprise instance provides [unlimited protection](/intl.en-US/DDoS Protection Guide/Terms.md). The Anti-DDoS Origin Enterprise instance automatically scrubs service traffic to mitigate DDoS attacks.


