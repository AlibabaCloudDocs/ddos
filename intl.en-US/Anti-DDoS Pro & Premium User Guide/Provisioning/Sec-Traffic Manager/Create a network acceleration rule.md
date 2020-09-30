# Create a network acceleration rule

You can use network acceleration for service interaction between an Anti-DDoS Premium Insurance or Unlimited instance and an Anti-DDoS Premium MCA instance. If no attacks occur, service traffic is sent to the IP address of the MCA instance for acceleration. If attacks occur, service traffic is automatically switched to the Anti-DDoS Premium Insurance or Unlimited instance for scrubbing. Normal traffic is then forwarded to the origin server.

-   An **Anti-DDoS Premium MCA** instance is purchased. For more information, see [Purchase an MCA plan for an Anti-DDoS Premium instance](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Purchase mitigation plans for Anti-DDoS Pro and Anti-DDoS Premium.md).
-   An **Anti-DDoS Premium Insurance or Unlimited** instance is purchased, and your service is added to the Anti-DDoS Premium Insurance or Unlimited instance. For more information, see [Purchase an insurance plan or unlimited plan for an Anti-DDoS Premium instance](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Purchase mitigation plans for Anti-DDoS Pro and Anti-DDoS Premium.md) and [Add a website](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Use domains/Add a website.md) \(website service\) and [Create forwarding rules](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Use ports/Create forwarding rules.md) \(non-website service\).

    **Note:** The bandwidth and QPS of the Anti-DDoS Premium Insurance or Unlimited instance must meet protection requirements of your service. This ensures that the instance can process service traffic after the traffic is switched to the Anti-DDoS Premium Insurance or Unlimited instance.

-   The Anti-DDoS Premium Insurance or Unlimited instance can forward traffic as expected. For more information, see [Verify the forwarding configuration on your local machine](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Use domains/Verify the forwarding configuration on your local machine.md).

Network acceleration rules apply to scenarios where your servers are deployed **outside mainland China** but your users come from **mainland China**.

If you add your service to only an Anti-DDoS Premium Insurance or Unlimited instance, users in mainland China will experience increased latency. You can purchase both an Anti-DDoS Premium Insurance or Unlimited instance and an Anti-DDoS Premium MCA instance. This allows you to accelerate user access by using the MCA instance if no attacks occur. If your service encounters attacks, service traffic is forwarded to the Anti-DDoS Premium Insurance or Unlimited instance for protection. The following figure shows the interaction process.

![Anti-DDoS Premium](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/0886328951/p35306.png)

For more information, see [Configure Anti-DDoS Premium MCA](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Configure Anti-DDoS Premium MCA.md).

## Procedure

1.  Log on to the [Anti-DDoS Pro console](https://yundun.console.aliyun.com/?p=ddoscoo).

2.  In the top navigation bar, select **Outside Mainland China**.

3.  In the left-side navigation pane, choose **Provisioning** \> **Sec-Traffic Manager**.

4.  On the **General** tab, click **Create Rule**.

5.  In the **Create Rule** pane, configure a **Network Acceleration** rule and click **Next**.

    ![Network Acceleration](../images/p142198.png "The following figure shows the example configuration of a network acceleration rule in the Anti-DDoS Premium console.")

    |Parameter|Description|
    |---------|-----------|
    |**Interaction Scenario**|Select **Network Acceleration**.|
    |**Name**|Specify the name of the rule. The rule name can be up to 128 characters in length and can contain letters, digits, and underscores \(\_\). |
    |**Anti-DDoS Instance IP**|Select an Anti-DDoS Pro or Anti-DDoS Premium instance.|
    |**Mainland China Acceleration IP**|Select the IP address of the MCA instance.|
    |**The waiting time of switching back**|Specify the waiting time to switch service traffic back to cloud resources from Anti-DDoS Pro or Anti-DDoS Premium.To avoid frequent traffic switchover and consider the time required to deactivate blackhole filtering, set the value to at least 30 minutes. We recommend that you set this parameter to 60 minutes. |

    After the rule is created, Sec-Traffic Manager assigns a CNAME address for the rule. You can view the created rule and **CNAME** address in the list.

    ![CNAME address of the network acceleration rule](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/0443341061/p142199.png)

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


