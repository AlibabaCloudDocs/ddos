# Step 1: Create a port forwarding rule

To use Anti-DDoS Pro or Anti-DDoS Premium to protect non-website services, such as client-based games, mobile games, or apps, you must create port forwarding rules. You must also use the IP address of your Anti-DDoS Pro or Anti-DDoS Premium instance as the service IP address. This topic describes how to create a port forwarding rule in the Anti-DDoS Pro or Anti-DDoS Premium console.

An Anti-DDoS Pro or Anti-DDoS Premium instance is purchased. For more information, see [Purchase mitigation plans for Anti-DDoS Pro and Anti-DDoS Premium](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Purchase mitigation plans for Anti-DDoS Pro and Anti-DDoS Premium.md).

If you configure your Anti-DDoS Pro or Anti-DDoS Premium instance to protect non-website services, your instance supports only Layer 4 forwarding. Both Anti-DDoS Pro and Anti-DDoS Premium provide protection only against Layer 4 attacks, such as SYN and UDP flood attacks. They do not parse Layer 7 packets or mitigate Layer 7 attacks, such as HTTP flood attacks and web attacks. To create an instance to protect non-website services, you need only to create port forwarding rules. Then, you can use the IP address of your instance as the service IP address.

1.  Log on to the [Anti-DDoS Pro console](https://yundun.console.aliyun.com/?p=ddoscoo).

2.  In the top navigation bar, select the region where your instance resides.

    -   **Mainland China**: If you select this region, the **Anti-DDoS Pro console** appears.
    -   **Outside Mainland China**: If you select this region, the **Anti-DDoS Premium console** appears.
    You can switch the region to configure and manage Anti-DDoS Pro or Anti-DDoS Premium instances. Make sure that you select the required region when you use Anti-DDoS Pro or Anti-DDoS Premium.

3.  In the left-side navigation pane, choose **Provisioning** \> **Port Config**.

4.  On the **Port Config** page, select the instance you want to use and click **Create Rule**.

    **Note:** You can also create more than one rule at a time. For more information, see [Create multiple forwarding rules at a time](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Use ports/Create forwarding rules.md).

5.  In the **Create Rule** dialog box, configure the following parameters.

    ![Configure a rule](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/2410999061/p46880.png)

    |Parameter|Description|
    |---------|-----------|
    |**Forwarding Protocol**|The protocol that you want to use to forward traffic. Valid values: **TCP** and **UDP**.|
    |**Forwarding Port**|The port that you want to use to forward traffic.     -   We recommend that you specify the same port for **Forwarding Port** and **Origin Server Port**.
    -   To prevent domain owners from creating their own DNS servers to protect services, Anti-DDoS Pro and Anti-DDoS Premium do not protect services that use port 53.
    -   You cannot specify a port that is used as the forwarding port for another rule. In an instance, forwarding rules that use the same protocol must use different forwarding ports. If you attempt to create a rule with a protocol and forwarding port that are used by another rule, an error message appears. The error message indicates that these rules overlap. Do not create a rule that overlaps with forwarding rules that are automatically generated. For more information, see [Automatically generate forwarding rules when you add website configurations](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Use ports/Create forwarding rules.md). |
    |**Origin Server Port**|The port of the origin server.|
    |**Origin Server IP**|The IP address of the origin server. **Note:** You can specify up to 20 origin server IP addresses to implement load balancing. Separate multiple IP addresses with commas \(,\). |

6.  Click **OK**.


After a port forwarding rule is created, you must change the IP address of your service to the IP address of the Anti-DDoS Pro or Anti-DDoS Premium instance to redirect service traffic to the instance. After you change the IP address, the instance scrubs inbound traffic and then forwards normal traffic to the origin server.

**Note:** Before you change the IP address to redirect inbound traffic to your instance, we recommend that you verify that the forwarding rule is in effect. For more information, see [Verify the forwarding configuration on your local machine](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Use domains/Verify the forwarding configuration on your local machine.md). If you change the IP address of the service before the forwarding rule is applied, your service may be interrupted.

The Anti-DDoS Pro or Anti-DDoS Premium instance uses default policies to scrub and forward traffic. You can customize DDoS mitigation policies and enable the session persistence and health check features based on your business requirements. For more information, see [Step 2: Configure port forwarding and anti-DDoS protection policies](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Quick Start/Set up Anti-DDoS Pro using IPs and ports/Step 2: Configure port forwarding and anti-DDoS protection policies.md).

