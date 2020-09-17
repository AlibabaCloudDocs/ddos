# Create forwarding rules

To use Anti-DDoS Pro or Anti-DDoS Premium to protect your non-website services, such as client-based games, mobile games, or apps, you must create forwarding rules on the Port Config page. You can also configure Layer 4 anti-DDoS protection, such as session persistence, health checks, and anti-DDoS protection policies.

## Prerequisites

An Anti-DDoS Pro or Anti-DDoS Premium instance is purchased. For more information, see [Purchase mitigation plans for Anti-DDoS Pro and Anti-DDoS Premium](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Purchase mitigation plans for Anti-DDoS Pro and Anti-DDoS Premium.md).

## Create a forwarding rule

1.  Log on to the [Anti-DDoS Pro console](https://yundun.console.aliyun.com/?p=ddoscoo).

2.  In the top navigation bar, select the region where your services are deployed.

    -   **Mainland China**: Anti-DDoS Pro
    -   **Outside Mainland China**: Anti-DDoS Premium
3.  In the left-side navigation pane, choose **Provisioning** \> **Port Config**.

4.  On the **Port Config** page, select an instance that you want to manage and click **Create Rule**.

    **Note:** You can also create multiple rules at a time. For more information, see [Create multiple forwarding rules at a time](#section_mcd_7yq_9rx).

    Automatically generate forwarding rules when you add website configurations:

    If a rule is automatically generated after a domain name is added, the ![Exclamation point](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/7097449951/p128503.png) icon is next to the protocol of the rule. For more information, see [Add a website](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Use domains/Add a website.md).

    -   If you specify port 80 of the origin server when you add a domain name to an instance, Anti-DDoS Pro or Anti-DDoS Premium generates a forwarding rule. This rule is used to forward traffic to the origin server over port 80 by using TCP.
    -   If you specify port 443 of the origin server when you add a domain name to an instance, Anti-DDoS Pro or Anti-DDoS Premium generates a forwarding rule. This rule is used to forward traffic to the origin server over port 443 by using TCP.
    Anti-DDoS Pro and Anti-DDoS Premium do not generate forwarding rules that are generated when you add another website.

    ![Configure a port](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/7097449951/p46883.png)

    **Note:** You cannot edit or delete rules that are automatically generated. To delete these rules, you must disassociate all the websites that use these rules from the Anti-DDoS Pro or Anti-DDoS Premium instance.

5.  In the Create Rule dialog box, configure the parameters and click **OK**.

    ![Configure a rule](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/7097449951/p46880.png)

    |Parameter|Description|
    |---------|-----------|
    |**Forwarding Protocol**|The protocol that you want to use to forward traffic. Valid values: **TCP** and **UDP**.|
    |**Forwarding Port**|The port that you want to use to forward traffic. **Note:**

    -   We recommend that you specify the same port for **Forwarding Port** and **Origin Server Port**.
    -   To prevent domain owners from creating their own DNS servers to protect services, Anti-DDoS Pro and Anti-DDoS Premium do not protect services that use port 53.
    -   You cannot specify a port that is already used as the forwarding port for another rule. In an instance, forwarding rules that use the same protocol must use different forwarding ports. If you attempt to create a rule with a protocol and forwarding port that are already used by another rule, an error message appears. This error message indicates that these rules overlap. Do not create a rule that overlaps with forwarding rules that are automatically generated. For more information, see [Automatically generate forwarding rules when you add website configurations](#step_p2d_akc_br3). |
    |**Origin Server Port**|The port of the origin server.|
    |**Origin Server IP**|The IP address of the origin server. **Note:** You can specify up to 20 origin server IP addresses to implement load balancing. Separate multiple IP addresses with commas \(,\). |

    After you create forwarding rules, you can view the created rules on the **Port Config** page. You can also perform the following operations:

    -   Configure Layer 4 anti-DDoS protection, such as session persistence, health checks, and anti-DDoS protection policies. For more information, see [Configure port forwarding and anti-DDoS protection policies](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Quick Start/Set up Anti-DDoS Pro using IPs and ports/Step 2: Configure port forwarding and anti-DDoS protection policies.md).
    -   Edit or delete rules. For more information, see [Edit forwarding rules](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Use ports/Edit forwarding rules.md) and [Delete forwarding rules](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Use ports/Delete forwarding rules.md).
    -   Export multiple forwarding rules and Layer 4 anti-DDoS protection settings at a time. For more information, see [Export multiple port configurations](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Use ports/Export multiple port configurations.md).

## Create multiple forwarding rules at a time

1.  Log on to the [Anti-DDoS Pro console](https://yundun.console.aliyun.com/?p=ddoscoo).

2.  In the top navigation bar, select the region where your services are deployed.

    -   **Mainland China**: Anti-DDoS Pro
    -   **Outside Mainland China**: Anti-DDoS Premium
3.  In the left-side navigation pane, choose **Provisioning** \> **Port Config**.

4.  On the Port Config page, select the instance that you want to manage, click **Batch Operations** \> **Create Rule**.

5.  In the Create Rule dialog box, enter the required information as shown in the sample file and click **OK**.

    ![Create rules](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/7097449951/p67614.png)

    You can create a rule based on the following requirements.

    -   Each line represents a rule.
    -   From left to right, the fields in each rule indicate the following parameters: forwarding protocol, forwarding port, origin server port, origin server IP address. Fields are separated with spaces. For more information about the related parameters, see [Rule parameters](#table_cmg_aw2_bd3).
6.  Check the entered information, select the rules that you want to create, and click **OK**.

    ![Upload multiple forwarding rules](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/7097449951/p67617.png)

7.  After the rules are uploaded, close the Create Rule dialog box.


## What to do next

After you create forwarding rules, you must perform the following operations to protect your non-website services.

1.  Allow the back-to-origin IP address of Anti-DDoS Pro and Anti-DDoS Premium on the origin server. This ensures that the traffic from Anti-DDoS Pro or Anti-DDoS Premium is allowed by security software on your origin server. For more information, see [Allow back-to-origin IP addresses to access the origin server](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Allow back-to-origin IP addresses to access the origin server.md).
2.  Verify that the forwarding rules have taken effect from the local computer to avoid service exceptions caused by incorrect forwarding rule configurations. For more information, see [Verify the forwarding configuration on your local machine](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Use domains/Verify the forwarding configuration on your local machine.md).

    **Warning:** If you switch your service traffic to instances before the forwarding rules take effect, your services may be interrupted.

3.  Redirect the traffic of your non-web services to the Anti-DDoS Pro or Anti-DDoS Premium instance. You can redirect the traffic by using one of the following methods:
    -   If your service is reachable over the IP address, replace the service IP address with the exclusive IP address of the Anti-DDoS Pro or Anti-DDoS Premium instance.

        **Note:** The method to replace the IP address depends on your platform.

    -   If your service is also reachable over a domain name, for example, aliyundemo.com that functions as the server address or is added to a client program, change the A record at the DNS resolution service provider of the domain name to direct the traffic to the exclusive IP address of the Anti-DDoS Pro or Anti-DDoS Premium instance. For more information, see [Change the DNS record](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Provisioning settings/Modify DNS records to protect websites.md).

