# Create a tiered protection rule

You can use tiered protection for service interaction between Anti-DDoS Origin Enterprise and Anti-DDoS Pro or Anti-DDoS Premium. You can create a tiered protection rule to prevent common attacks by using Anti-DDoS Origin Enterprise. In this case, service traffic is directly sent to the origin server, which does not bring additional latency. If volumetric DDoS attacks occur, service traffic is forwarded to Anti-DDoS Pro or Anti-DDoS Premium for scrubbing. Normal service traffic is then forwarded to the origin server.

-   Your service uses **Alibaba Cloud resources that have public IP addresses**, such as an EIP or a WAF, ECS, or SLB instance with a public IP address.
-   An **Anti-DDoS Origin Enterprise** instance is purchased, and the public IP address of your service is added to Anti-DDoS Origin Enterprise. For more information, see [Add a protection target](/intl.en-US/Anti-DDoS Origin User Guide/Instances/Add a protection target.md).

    **Note:** The Anti-DDoS Origin Enterprise instance must be in the same region as the protected cloud resource, such as an EIP or an ECS, SLB, and WAF instance.

-   An **Anti-DDoS Pro or Anti-DDoS Premium** instance is purchased, and your service is added to Anti-DDoS Pro or Anti-DDoS Premium. For more information, see [Add a website](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Use domains/Add a website.md) \(website service\) and [Create forwarding rules](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Use ports/Create forwarding rules.md)\(non-website service\).

    **Note:** The bandwidth and QPS of the Anti-DDoS Pro or Anti-DDoS Premium instance must meet protection requirements of your service. This ensures that the instance can process service traffic after the traffic is switched to Anti-DDoS Pro or Anti-DDoS Premium.

-   The Anti-DDoS Pro or Anti-DDoS Premium instance can properly forward traffic. For more information, see [Verify the forwarding configuration on your local machine](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Use domains/Verify the forwarding configuration on your local machine.md).

## Procedure

1.  Log on to the [Anti-DDoS Pro console](https://yundun.console.aliyun.com/?p=ddoscoo).

2.  In the top navigation bar, select the region where your services are deployed.

    -   **Mainland China**: Anti-DDoS Pro
    -   **Outside Mainland China**: Anti-DDoS Premium
3.  In the left-side navigation pane, choose **Provisioning** \> **Sec-Traffic Manager**.

4.  On the **General** tab, click **Create Rule**.

5.  In the **Create Rule** pane, configure a **Tiered Protection** rule and click **Next**.

    ![Tiered protection rule](../images/p142066.png "The following figure shows the example configuration of a tiered protection rule in the Anti-DDoS Pro console.")

    |Parameter|Description|
    |---------|-----------|
    |**Interaction Scenario**|Select **Tiered Protection**.|
    |**Name**|Specify the name of the rule. The rule name can be up to 128 characters in length and can contain letters, digits, and underscores \(\_\). |
    |**Anti-DDoS Instance IP**|Select an Anti-DDoS Pro or Anti-DDoS Premium instance.|
    |**Cloud Service**|Cloud Resource IP: Select the region where the cloud resource resides and enter the IP address of the cloud resource.**Note:** You must enter the IP address of a cloud resource that you add to Anti-DDoS Origin Enterprise, such as an EIP or an ECS, SLB, and WAF instance.

You can click **Add Cloud Resource IP** and add up to 20 cloud resource IP addresses.

**Note:** If you add multiple cloud resource IP addresses, these IP addresses are associated with the IP address of the selected Anti-DDoS Pro or Anti-DDoS Premium instance. If one of these IP addresses encounters DDoS attacks, service traffic is forwarded to other IP addresses. Only if all the IP addresses are attacked, service traffic is forwarded to Anti-DDoS Pro or Anti-DDoS Premium. For information about how to forward service traffic to Anti-DDoS Pro or Anti-DDoS Premium when one of the IP addresses encounters attacks, see [Share one Anti-DDoS Pro or Anti-DDoS Premium instance among multiple cloud resources](). |
    |**The waiting time of switching back**|Specify the waiting time to switch service traffic back to cloud resources from Anti-DDoS Pro or Anti-DDoS Premium.To avoid frequent traffic switchover and consider the time required to deactivate blackhole filtering, set the value to at least 30 minutes. We recommend that you set this parameter to 60 minutes. |

    After the rule is created, Sec-Traffic Manager assigns a CNAME address for the rule. You can view the created rule and **CNAME** address in the list.

    ![CNAME address of a tiered protection rule](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/9203341061/p142192.png)

6.  Modify the DNS records.

    Modify the DNS records of your domain name on the website of the DNS service provider to point the domain name to the CNAME address provided by Sec-Traffic Manager. For more information, see [Modify the CNAME record to reroute traffic by using Sec-Traffic Manager](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Provisioning settings/Modify the CNAME record to reroute traffic by using Sec-Traffic Manager.md).


## What to do next

-   Switch traffic back: Assume that the general interaction rule takes effect and service traffic is switched to Anti-DDoS Pro or Anti-DDoS Premium. If the **waiting time of switching back** has not arrived, you can click **Switch back** to manually switch the traffic back to the cloud resource.

    **Note:** The **Switch back** button appears only when service traffic is switched to Anti-DDoS or Anti-DDoS Premium and the **waiting time of switching back** does not arrive.

    The following exceptions may occur when you perform this operation:

    -   If all cloud resources are in blackhole filtering, the operation fails.
    -   If some cloud resources are in blackhole filtering and some are normal, traffic is switched to the normal cloud resources. After blackhole filtering is deactivated, traffic is automatically switched to other cloud resources.
-   Edit an interaction rule: On the **General** tab, find the rule that you want to edit and click **Edit** in the Actions column. You can modify parameters except **Interaction Scenario** and **Name**.
-   Delete an interaction rule: On the **General** tab, find the rule that you want to delete and click **Delete** in the Actions column.

    **Warning:** Before you delete an interaction rule, make sure that the service traffic is no longer directed to the CNAME address assigned by Sec-Traffic Manager. Otherwise, your service becomes unavailable after you delete the rule.


