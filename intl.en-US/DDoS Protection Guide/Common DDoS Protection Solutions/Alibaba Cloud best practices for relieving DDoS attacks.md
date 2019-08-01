# Alibaba Cloud best practices for relieving DDoS attacks {#concept_65932_zh .concept}

Distributed Denial of Service Attack \(DDoS Attack\) is a malicious cyber-attack on a target system. It usually makes the victim’s services unable to be normally accessed, i.e., the denial of service.

Common DDoS attacks include:

-   Network layer attack

    The typical network layer attack is a UDP reflection attack. It mainly congests the network bandwidth of the victim using heavy traffic, causing the victim’s services not to respond to customer access normally.

-   Transport layer attack

    The typical transport layer attack includes an SYN flood attack, a connections attack, etc. It occupies connection pool resources of a server to achieve the purpose of denying the service.

-   Session layer attack

    The typical session layer attack is an SSL connection attack. It occupies SSL session resources of a server to achieve the purpose of denying the service.

-   Application layer attack

    The typical application layer attack includes a DNS flood attack, an HTTP flood attack, a dummy attack, etc. It occupies application processing resources of a server and significantly consumes the processing performance of the server to achieve the purpose of denying the service.


## Best practices for relieving DDoS attacks {#section_mbf_b80_qwd .section}

It is recommended that Alibaba Cloud users relieve DDoS attacks through the following methods:

-   Reduce surface exposure and isolate resources and irrelevant services to reduce the risk of being attacked.
    -   Configure a security group

        Avoid exposing ports which are not required for the service on the public network as much as possible so as to avoid requests and accesses irrelevant to the service. Configuring a security group can effectively prevent the system from being scanned or exposed accidentally.

        For more information, see [Security Group User Guide](../../../../reseller.en-US/Security/Security groups/Create a security group.md#).

    -   Use Virtual Private Cloud \(VPC\)

        The logic isolation within the network is implemented through VPC to prevent attacks from Intranet zombie computers.

        For more informatioin, see [VPC User Guide](../../../../reseller.en-US/User Guide/VPC and subnets/Manage a VPC.md#).

-   Optimize the business architecture and design auto scaling and failover based on features of the public cloud.
    -   Deploy Server Load Balancer

        Transport layer DDoS attacks within a certain amount of traffic can be effectively relieved by deploying Server Load Balancer \(SLB\) instances to balance loads across multiple servers. Meanwhile, after the SLB is deployed, the user access traffic can be allocated to servers uniformly to reduce the burden of a single server and increase the access speed.

        For more information, see [SLB User Guide](../../../../reseller.en-US/Quick Start (New Console)/Tutorial overview.md#).

    -   Deploy Auto Scaling

        Auto Scaling is a management service that automatically adjusts elastic computing resources according to your business needs and policies in an economical manner. By deploying Auto Scaling, the system can effectively relieve session layer and application layer attacks, and automatically adds servers when being attacked, which improves the processing performance and avoids severe impact to the service.

        For more information, see [Auto Scaling User Guide](../../../../reseller.en-US/Quick Start/Step 1. Activate and authorize the Auto Scaling service.md#).

    -   Deploy smart DNS resolution Optimize DNS resolution by using the smart resolution to effectively avoid risks caused by DNS traffic attacks. Meanwhile, we recommend that you host the service on multiple DNS service providers.
        -   Shield unrequested DNS response information
        -   Discard the fast retransmit data packet
        -   Enable TTL
        -   Discard the unknown DNS query request and response data
        -   Discard unrequested or sudden DNS requests
        -   Enable DNS client verification
        -   Cache response information
        -   Use the ACL permission
        -   Use ACL, BCP38, and IP reputation
    -   Prepare the remaining bandwidth

        Run a server performance test to assess bandwidth and the number of requests that the normal business environment can withstand. Make sure that a certain remaining bandwidth is available when purchasing the bandwidth, thus avoiding the influence on normal users when the bandwidth is greater than the normal bandwidth usage while being attacked.

-   Strengthen the server security and improve performances of the server such as connections.

    Strengthen the server security, reduce attacked items, and increase the attack cost of the attacker.

    -   Make sure that system files on the server are up-to-date, and promptly update system patches.
    -   Check the host of all servers to know the source of visitors.
    -   Filter unnecessary services and ports. For example, only enable port 80 for WWW servers, and disable all other ports, or set block policies on the firewall.
    -   Limit the number of SYN semi-joins that are open at the same time, shorten the timeout for SYN semi-joins, and limit SYN/ICMP traffic.
    -   Check logs for network devices and server systems carefully. As long as vulnerabilities or changes in time appear, this server may be attacked.
    -   Restrict file sharing with network files outside the firewall. Reduce the opportunity that hackers intercept system files. If the hackers replace it with a Trojan, file transfer functions are undoubtedly paralyzed.
    -   Make full use of network devices to protect network resources. The following strategy configurations must be considered when configuring the router: traffic control, packet filtering, semi-join timeout, garbage packet discarding, counterfeit source data packet discarding from the source, SYN threshold, disabling ICMP and UDP broadcasts.
    -   Restrict new TCP connections, connections, and the transmission rate of suspected malicious IPs via software firewalls such as iptable.
-   Carry out business monitoring and emergency response.
    -   Focus on Anti-DDoS Basic monitoring

        When your services are suffering from DDoS attacks, Anti-DDoS Basic sends alert information through SMS or mail. It also supports alarming by phone when the services are suffering from heavy traffic attacks. It is recommended that you perform emergency response processing immediately when receiving the alert.

        For more information about configuring the alert message recipient and voice alert method, see [Anti-DDoS Basic Message Recipient Setting](../../../../reseller.en-US/Anti-DDoS Basic Service/User Guide/Configure DDoS Protection notification settings.md#).

    -   CloudMonitor

        CloudMonitor can be used to collect and obtain monitoring metrics for Alibaba Cloud resources or monitoring metrics customized by users, to test the availability of services, and to set alarms for these metrics.

        For more information, see [CloudMonitor User Guide](../../../../reseller.en-US/Product Introduction/Overview.md#).

-   Select an appropriate commercial security solution. Alibaba Cloud provides free Anti-DDoS Basic and commercial security solutions such as Anti-DDoS Pro IP and Game Shield. You can also select security solutions from other manufacturers.
    -   Web Application Firewall \(WAF\)

        WAF can provide effective safeguard on transport layer attacks, session layer attacks, and application layer attacks for web applications.

        For more information, see [WAF User Guide](../../../../reseller.en-US/User Guide/Overview.md#).

    -   Anti-DDoS Pro IP

        It is recommended that you use Alibaba Cloud Anti-DDoS Pro IP for heavy traffic DDoS attacks.

        For more information, see [Anti-DDoS Pro IP User Guide](../../../../reseller.en-US/Anti-DDoS Pro Service/Product Introduction/What is Anti-DDoS Pro.md#).

    -   Game Shield

        Game Shield is an industry solution proposed for common DDoS attacks and HTTP flood attacks in the game industry. Compared with Anti-DDoS Pro IP, Game Shield provides more pertinence, better defense effects, and a lower cost.


## Cautions {#section_rfd_tmv_6az .section}

DDoS attacks are the recognized public enemy industry-wide. It not only affects the victims, but also affects the service providers’ network stability, thus causing service losses to other users within the same network.

Computer networks are shared environments. The stability must be maintained by each party. Some behaviors may affect the whole network and the network of other tenants. So you need to pay attention to the following items:

-   Do not establish the DDoS protection platform using Alibaba Cloud product mechanism
-   Do not release instances which are in black hole status
-   Do not continuously replace, unbind, and add IP products such as SLB IP, Elastic IP, and NAT Gateway to servers which are in black hole status
-   Do not defend by establishing an IP pool or allocating the attack traffic to a large variety of IPs
-   Do not prepose Alibaba Cloud non-network security defense products \(including but not limited to CDN and OSS\) that are vulnerable to attack
-   Do not get around the rules by using multiple accounts

