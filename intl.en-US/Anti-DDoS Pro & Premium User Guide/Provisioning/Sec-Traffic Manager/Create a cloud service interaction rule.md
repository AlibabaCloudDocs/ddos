# Create a cloud service interaction rule

You can use cloud service interaction for services that use Global Accelerator or other Alibaba Cloud resources that have public IP addresses. After you add your service to Anti-DDoS Pro or Anti-DDoS Premium, the cloud resources can be associated with Anti-DDoS Pro or Anti-DDoS Premium. If no attacks occur, traffic is not scrubbed by Anti-DDoS Pro or Anti-DDoS Premium and directly reaches the origin server. If attacks occur, traffic is automatically switched to Anti-DDoS Pro or Anti-DDoS Premium for scrubbing. Normal traffic is then forwarded to the origin server.

-   Your service uses **Global Accelerator** or **Alibaba Cloud resources that have public IP addresses**, such as an EIP, a WAF instance, or an ECS or SLB instance with a public IP address.

    For more information about the limits of interaction between Global Accelerator and Anti-DDoS Pro or Anti-DDoS Premium, see [Interaction between Global Accelerator and Anti-DDoS Pro or Anti-DDoS Premium](#section_b1u_nrx_njn).

-   An **Anti-DDoS Pro or Anti-DDoS Premium** instance is purchased, and your service is added to Anti-DDoS Pro or Anti-DDoS Premium. For more information, see [Add a website](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Use domains/Add a website.md) \(website service\) and [Create forwarding rules](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Use ports/Create forwarding rules.md)\(non-website service\).

    **Note:** The bandwidth and QPS of the Anti-DDoS Pro or Anti-DDoS Premium instance must meet protection requirements of your service. This ensures that the instance can process service traffic after the traffic is switched to Anti-DDoS Pro or Anti-DDoS Premium.

-   The Anti-DDoS Pro or Anti-DDoS Premium instance can properly forward traffic. For more information, see [Verify the forwarding configuration on your local machine](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Use domains/Verify the forwarding configuration on your local machine.md).

After you add your service to Anti-DDoS Pro or Anti-DDoS Premium, service traffic is scrubbed by Anti-DDoS Pro or Anti-DDoS Premium. Only normal traffic is forwarded to the origin server. Even if no attacks occur, normal traffic is forwarded by Anti-DDoS Pro or Anti-DDoS Premium. This increases latency in service access.

If you want to avoid additional latency, you can use Sec-Traffic Manager to create a cloud service interaction rule. This rule allows traffic to be directly sent to the origin server in normal periods and is switched to Anti-DDoS Pro or Anti-DDoS Premium only when an attack occurs. You can specify a time to automatically switch traffic back to the origin server or manually switch the traffic back.

## Interaction between Global Accelerator and Anti-DDoS Pro or Anti-DDoS Premium

To configure interaction between Global Accelerator and Anti-DDoS Pro or Anti-DDoS Premium, you must determine the location where you want service traffic to be switched from Anti-DDoS Pro or Anti-DDoS Premium to Global Accelerator. If the location is in mainland China, use Anti-DDoS Pro. If the location is outside mainland China, use Anti-DDoS Premium. For more information, see [What is Global Accelerator?](/intl.en-US/Product Introduction/What is Global Accelerator?.md).

-   Interaction between Global Accelerator and Anti-DDoS Pro
    -   When you add a domain name to Anti-DDoS Pro, in the **Enter Site Information** step, set **Server IP** to **Origin Server Domain** and enter the CNAME address provided by the Global Accelerator instance. For more information, see [Add a website](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Use domains/Add a website.md).

        ![Enter Site Information](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/3243341061/p139386.png)

        Service traffic is scrubbed by Anti-DDoS Pro and then forwarded to Global Accelerator. The back-to-origin traffic of Anti-DDoS Pro is sent to the IP address of Global Accelerator by using a leased line and is not affected even if blackhole filtering is triggered for the IP address. This protects your service and implements network acceleration.

        You can obtain the CNAME address on the instance details page in the [Global Accelerator console](https://ga.console.aliyun.com/list). For more information, see [Step 1: Obtain the CNAME of the accelerated domain](/intl.en-US/User Guide/Create a CNAME record.md).

        ![CNAME address of Global Accelerator](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/3243341061/p139387.png)

    -   When you add a port to Anti-DDoS Pro, set **Origin Server IP** to the IP address of your origin server in the port forwarding rule. Domain names are not supported. For more information, see [Create forwarding rules](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Use ports/Create forwarding rules.md).

        **Note:** In this configuration, service access is not accelerated.

        ![Origin Server IP](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/3243341061/p139417.png)

-   Interaction between Global Accelerator and Anti-DDoS Premium

    When you add a domain name or port to Anti-DDoS Premium, set Server IP or Origin Server IP to the IP address of your origin server.

    **Note:** In this configuration, service access is not accelerated.


## Procedure

1.  Log on to the [Anti-DDoS Pro console](https://yundun.console.aliyun.com/?p=ddoscoo).

2.  In the top navigation bar, select the region where your services are deployed.

    -   **Mainland China**: Anti-DDoS Pro
    -   **Outside Mainland China**: Anti-DDoS Premium
3.  In the left-side navigation pane, choose **Provisioning** \> **Sec-Traffic Manager**.

4.  On the **General** tab, click **Create Rule**.

5.  In the **Create Rule** pane, configure a **Cloud Service Interaction** rule and click **Next**.

    ![Cloud Service Interaction rule](../images/p65101.png "The following figure shows the example configuration of a cloud service interaction rule in the Anti-DDoS Pro console.")

    |Parameter|Description|
    |---------|-----------|
    |**Interaction Scenario**|Select **Cloud Service Interaction**.|
    |**Name**|Specify the name of the rule. The rule name can be up to 128 characters in length and can contain letters, digits, and underscores \(\_\). |
    |**Anti-DDoS Instance IP**|Select an Anti-DDoS Pro or Anti-DDoS Premium instance.|
    |**Cloud Service**|Select the cloud resource to be interacted with Anti-DDoS Pro or Anti-DDoS Premium. Valid values: **Cloud Resource IP** and **Global Accelerator Instance**.    -   **Cloud Resource IP**: Select the region where the cloud resource resides and enter the IP address of the cloud resource.

You can click **Add Cloud Resource IP** and add up to 20 cloud resource IP addresses.

**Note:** If you add multiple cloud resource IP addresses, these IP addresses are associated with the IP address of the selected Anti-DDoS Pro or Anti-DDoS Premium instance. If one of these IP addresses encounters DDoS attacks, service traffic is forwarded to other IP addresses. Only if all the IP addresses are attacked, service traffic is forwarded to Anti-DDoS Pro or Anti-DDoS Premium. For information about how to forward service traffic to Anti-DDoS Pro or Anti-DDoS Premium when one of the IP addresses encounters attacks, see [Share one Anti-DDoS Pro or Anti-DDoS Premium instance among multiple cloud resources]().

    -   **Global Accelerator Instance**: Select a Global Accelerator instance. You can select only one instance. |
    |**The waiting time of switching back**|Specify the waiting time to switch service traffic back to cloud resources from Anti-DDoS Pro or Anti-DDoS Premium.To avoid frequent traffic switchover and consider the time required to deactivate blackhole filtering, set the value to at least 30 minutes. We recommend that you set this parameter to 60 minutes. |

    After the rule is created, Sec-Traffic Manager assigns a CNAME address for the rule. You can view the created rule and **CNAME** address in the list.

    ![CNAME](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/3243341061/p141978.png)

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


