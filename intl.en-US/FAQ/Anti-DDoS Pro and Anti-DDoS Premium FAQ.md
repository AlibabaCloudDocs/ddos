# Anti-DDoS Pro and Anti-DDoS Premium FAQ

This topic provides answers to some commonly asked questions about Anti-DDoS Pro and Anti-DDoS Premium.

-   [What happens if an Anti-DDoS Pro or Anti-DDoS Premium instance expires?](#section_urg_0kt_c2b)
-   [What is the clean bandwidth of an Anti-DDoS Pro or Anti-DDoS Premium instance?](#section_i7x_ce0_9a8)
-   [What happens if the actual bandwidth exceeds the clean bandwidth of an Anti-DDoS Pro or Anti-DDoS Premium instance?](#section_j32_xy6_kkn)
-   [Can I manually deactivate the black hole status?](#section_p5r_kk3_ocs)
-   [What are the back-to-origin CIDR blocks for Anti-DDoS Pro and Anti-DDoS Premium?](#section_woj_jo4_6di)
-   [Are the back-to-origin CIDR blocks of Anti-DDoS Pro and Anti-DDoS Premium automatically added to a security group?](#section_rob_5uy_808)
-   [Can I use an internal IP address as the origin server IP address for an Anti-DDoS Pro or Anti-DDoS Premium instance?](#section_dej_vzv_e83)
-   [Does the configuration of the origin server IP address for an Anti-DDoS Pro or Anti-DDoS Premium instance take effect immediately?](#section_xrr_p7z_rki)
-   [How do I identify which website is under attack when multiple website services are protected by an Anti-DDoS Pro or Anti-DDoS Premium instance?](#section_x1f_4c0_3zj)
-   [Do Anti-DDoS Pro and Anti-DDoS Premium support the health check feature?](#section_dth_0eg_s56)
-   [How is traffic distributed to multiple origin servers protected by an Anti-DDoS Pro or Anti-DDoS Premium instance?](#section_wel_rpm_7j6)
-   [Can I configure session persistence in Anti-DDoS Pro and Anti-DDoS Premium?](#section_quj_81r_c1a)
-   [How does session persistence work for an Anti-DDoS Pro or Anti-DDoS Premium instance?](#section_2l2_myz_dst)
-   [What is the default TCP timeout period for an Anti-DDoS Pro or Anti-DDoS Premium instance?](#section_d4i_dvu_z2t)
-   [What are the default HTTP and HTTPS timeout periods for an Anti-DDoS Pro or Anti-DDoS Premium instance?](#section_w5s_6lw_8my)
-   [Do Anti-DDoS Pro and Anti-DDoS Premium support IPv6?](#section_rlz_9lo_tbd)
-   [Do Anti-DDoS Pro and Anti-DDoS Premium support WebSocket?](#section_tip_66a_ulc)
-   [Does Anti-DDoS Pro or Anti-DDoS Premium support mutual HTTPS authentication?](#section_cfz_baq_wws)
-   [Why am I unable to access HTTPS websites by using the browsers of earlier versions or from an Android mobile client?](#section_l32_vr6_x4j)
-   [Which SSL protocols and cipher suites are supported by Anti-DDoS Pro or Anti-DDoS Premium?](#section_kkt_vxb_72v)
-   [What are the limits on the numbers of ports and domain names protected by an Anti-DDoS Pro or Anti-DDoS Premium instance?](#section_jar_w1u_k7f)
-   [Why does the traffic chart show a traffic scrubbing event even though the size of the traffic received by the server does not exceed the traffic scrubbing threshold?](#section_joj_hbi_7p8)
-   [Do Anti-DDoS Pro and Anti-DDoS Premium protect websites that use NTLM authentication?](#section_wgn_qt3_mgb)

## What happens if an Anti-DDoS Pro or Anti-DDoS Premium instance expires?

An expired instance no longer protects your services.

-   The instance still forwards your traffic for seven days after it expires. If the actual bandwidth exceeds the clean bandwidth of the instance, throttling is triggered and packet loss may occur.
-   The instance stops forwarding traffic seven days after it expires. If the IP addresses of your services are mapped to the instance, your services become inaccessible.

For more information, see [Instance expiration](/intl.en-US/Pricing/Anti-DDoS Pro billing methods.md).

## What is the clean bandwidth of an Anti-DDoS Pro or Anti-DDoS Premium instance?

The clean bandwidth of an instance is equal to the peak value of the inbound or outbound traffic of the protected service, whichever is greater. Unit: Mbit/s.

You can increase the **clean bandwidth** of an instance on the **Instances** page in the [Anti-DDoS Pro console](https://yundun.console.aliyun.com/?p=ddoscoo). For more information, see [Upgrade the specifications of an Anti-DDoS Pro or Anti-DDoS Premium instance](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Resource management/Upgrade the specifications of an Anti-DDoS Pro or Anti-DDoS Premium instance.md).

## What happens if the actual bandwidth exceeds the clean bandwidth of an Anti-DDoS Pro or Anti-DDoS Premium instance?

If the actual bandwidth exceeds the clean bandwidth of the instance, throttling is triggered and packet loss may occur.

## Can I manually deactivate the black hole status?

-   You can manually deactivate the black hole status for an Anti-DDoS Pro instance. Each Alibaba Cloud account can deactivate the black hole status up to five times a day. The limit is reset at 00:00:00 \(UTC+8\) the next day. For more information, see [Deactivate blackhole filtering](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Protection settings/Protection for infrastructure/Deactivate blackhole filtering.md).
-   You cannot manually deactivate the black hole status for an Anti-DDoS Premium instance.

## What are the back-to-origin CIDR blocks for Anti-DDoS Pro and Anti-DDoS Premium?

You can view the back-to-origin CIDR blocks on the **Website Config** page in the [Anti-DDoS Pro console](https://yundun.console.aliyun.com/?p=ddoscoo). For more information, see [Allow back-to-origin IP addresses to access the origin server](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Allow back-to-origin IP addresses to access the origin server.md).

![Back-to-origin CIDR blocks](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/0412488951/p130910.png)

## Are the back-to-origin CIDR blocks of Anti-DDoS Pro and Anti-DDoS Premium automatically added to a security group?

No. If you deploy Web Application Firewall \(WAF\) or a third-party security service on your origin server, you must manually add the back-to-origin CIDR blocks of Anti-DDoS Pro to the whitelist of the security software. For more information, see [Allow back-to-origin IP addresses to access the origin server](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Allow back-to-origin IP addresses to access the origin server.md).

## Can I use an internal IP address as the origin server IP address for an Anti-DDoS Pro or Anti-DDoS Premium instance?

No, you cannot use internal IP addresses because Anti-DDoS Pro and Anti-DDoS Premium support forwarding traffic to origin servers only over the Internet.

## Does the configuration of the origin server IP address for an Anti-DDoS Pro or Anti-DDoS Premium instance take effect immediately?

No, the configuration does not immediately take effect. The configuration requires about five minutes to take effect. We recommend that you perform this operation during off-peak hours. For more information, see [Change the public IP address of an ECS origin server](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Change the public IP address of an ECS origin server.md).

## How do I identify which website is under attack when multiple website services are protected by an Anti-DDoS Pro or Anti-DDoS Premium instance?

When website services are targeted by volumetric DDoS attacks, you cannot identify which website is under attack from the dimension of data packets. We recommend that you connect your website services to multiple instances. This way, you can view the monitoring data of the website services separately.

## Do Anti-DDoS Pro and Anti-DDoS Premium support the health check feature?

Yes, Anti-DDoS Pro and Anti-DDoS Premium instance support the health check feature.

-   The health check feature is enabled for website services by default.
-   The health check feature is disabled for non-website services by default. You can enable the health check feature in the Anti-DDoS Pro console. For more information, see [Configure a health check](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Use ports/Configure a health check.md).

For more information about the health check feature, see [Health check overview](/intl.en-US/Classic Load Balancer/User Guide/Health check/Health check overview.md).

## How is traffic distributed to multiple origin servers protected by an Anti-DDoS Pro or Anti-DDoS Premium instance?

-   Traffic destined for website services is distributed to origin servers by using the IP hash policy.
-   Traffic destined for non-website services is distributed to origin servers by using the weighted round robin policy.

## Can I configure session persistence in Anti-DDoS Pro and Anti-DDoS Premium?

Yes, you can configure session persistence for non-website services in the console. For more information, see [Configure session persistence](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Use ports/Configure session persistence.md).

## How does session persistence work for an Anti-DDoS Pro or Anti-DDoS Premium instance?

After you configure session persistence for an instance, the instance forwards requests from the same IP address to the same origin server within a specific time period. If you change the network from a wired network or 4G network to a wireless network, the change in the client IP address results in a session persistence failure.

## What is the default TCP timeout period for an Anti-DDoS Pro or Anti-DDoS Premium instance?

The default timeout period is 900 seconds. You can set the timeout period for non-website services in the Anti-DDoS Pro console. For more information, see [Configure session persistence](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Use ports/Configure session persistence.md).

## What are the default HTTP and HTTPS timeout periods for an Anti-DDoS Pro or Anti-DDoS Premium instance?

The default timeout periods are 120 seconds.

## Do Anti-DDoS Pro and Anti-DDoS Premium support IPv6?

No, Anti-DDoS Pro and Anti-DDoS Premium do not support IPv6.

## Do Anti-DDoS Pro and Anti-DDoS Premium support WebSocket?

Yes, Anti-DDoS Pro and Anti-DDoS Premium support WebSocket. For more information, see [How do I enable WebSocket?]().

## Does Anti-DDoS Pro or Anti-DDoS Premium support mutual HTTPS authentication?

-   Website services that are added to Anti-DDoS Pro or Anti-DDoS Premium do not support mutual HTTPS authentication.
-   Non-website services that are added to Anti-DDoS Pro or Anti-DDoS Premium and use TCP port forwarding support mutual HTTPS authentication.

## Why am I unable to access HTTPS websites by using the browsers of earlier versions or from an Android mobile client?

This issue occurs because the browser or client does not support Server Name Indication \(SNI\). Make sure that the browser or client supports SNI. For more information, see [How do I handle HTTPS access exceptions that occur when clients do not support SNI?]().

## Which SSL protocols and cipher suites are supported by Anti-DDoS Pro or Anti-DDoS Premium?

Supported SSL protocols:

-   TLS v1.0
-   TLS v1.1
-   TLS v1.2

Supported cipher suites:

-   ECDHE-ECDSA-AES128-GCM-SHA256
-   ECDHE-ECDSA-AES256-GCM-SHA384
-   ECDHE-ECDSA-AES128-SHA256
-   ECDHE-ECDSA-AES256-SHA384
-   ECDHE-RSA-AES128-GCM-SHA256
-   ECDHE-RSA-AES256-GCM-SHA384
-   ECDHE-RSA-AES128-SHA256
-   ECDHE-RSA-AES256-SHA384
-   AES128-GCM-SHA256
-   AES256-GCM-SHA384
-   AES128-SHA256
-   AES256-SHA256
-   ECDHE-ECDSA-AES128-SHA
-   ECDHE-ECDSA-AES256-SHA
-   ECDHE-RSA-AES128-SHA
-   ECDHE-RSA-AES256-SHA
-   AES128-SHA
-   AES256-SHA
-   DES-CBC3-SHA
-   RSA+3DES

## What are the limits on the numbers of ports and domain names protected by an Anti-DDoS Pro or Anti-DDoS Premium instance?

-   Maximum number of protected ports:
    -   An Anti-DDoS Pro instance protects 50 ports by default. You can upgrade the instance to protect a maximum of 400 ports.
    -   An Anti-DDoS Premium instance protects 5 ports by default. You can upgrade the instance to protect a maximum of 400 ports.
-   Maximum number of protected domain names:
    -   An Anti-DDoS Pro instance protects 50 domain names by default. You can upgrade the instance to protect a maximum of 200 domain names.
    -   An Anti-DDoS Premium instance protects 10 domain names by default. You can upgrade the instance to protect a maximum of 200 domain names.

## Why does the traffic chart show a traffic scrubbing event even though the size of the traffic received by the server does not exceed the traffic scrubbing threshold?

An Anti-DDoS Pro or Anti-DDoS Premium instance automatically filters out malformed packets, such as small SYN packets and packets that do not meet TCP requirements, and invalid SYN flags for protected services. This way, your servers do not allocate resources to manage these malformed packets. These filtered malformed packets are counted in the scrubbed traffic statistics. This indicates that the traffic chart may show a traffic scrubbing event even though the size of the traffic received by the server does not exceed the traffic scrubbing threshold.

## Do Anti-DDoS Pro and Anti-DDoS Premium protect websites that use NTLM authentication?

No, Anti-DDoS Pro and Anti-DDoS Premium do not protect websites that use NTLM authentication. The website request forwarded by an Anti-DDoS Pro or Anti-DDoS Premium instance cannot pass the NTLM authentication of the origin server. The client encounters repeated authentication requests. We recommend that you use other authentication methods for your website.

