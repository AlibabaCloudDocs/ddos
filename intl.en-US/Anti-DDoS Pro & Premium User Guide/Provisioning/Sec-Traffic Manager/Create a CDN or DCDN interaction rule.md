# Create a CDN or DCDN interaction rule

If you have added the domain name of your website to CDN or Dynamic Route for CDN \(DCDN\) and Anti-DDoS Pro or Anti-DDoS Premium, you can enable CDN or DCDN interaction to protect the website. If no attacks occur, service traffic is directly forwarded to the nearest CDN or DCDN node for acceleration. If attacks occur, the traffic is automatically forwarded to Anti-DDoS Pro or Anti-DDoS Premium for scrubbing. Normal traffic is then forwarded to the origin server.

-   The domain name is added to CDN or DCDN. For more information, see [Add a domain name for CDN](/intl.en-US/Quick Start/Add a domain.md) \(CDN\) or [Add a domain]() \(DCDN\).

    For more information about the limits of interaction between CDN or DCDN and Anti-DDoS Pro or Anti-DDoS Premium, see [Limits](#section_fa8_anx_7lc).

-   An **Anti-DDoS Pro or Anti-DDoS Premium** instance with the **Enhanced** function plan is purchased, and your website is added to Anti-DDoS Pro or Anti-DDoS Premium. For more information, see [Add a website](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Use domains/Add a website.md).

    **Note:** The bandwidth and QPS of the Anti-DDoS Pro or Anti-DDoS Premium instance must meet protection requirements of your website. This ensures that the instance can process service traffic after the traffic is switched to Anti-DDoS Pro or Anti-DDoS Premium.

-   The Anti-DDoS Pro or Anti-DDoS Premium instance can properly forward traffic. For more information, see [Verify the forwarding configuration on your local machine](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Use domains/Verify the forwarding configuration on your local machine.md).

## Limits

The following table describes the requirements that must be met before you can use CDN or DCDN interaction.

|Item|Limit|
|----|-----|
|Service type|CDN or DCDN interaction applies only to HTTP and HTTPS services and does not support video live streaming.|
|Service scenario|-   Your service is not attacked more than three times per week.
-   Your service does not require that anti-DDoS protection settings immediately take effect.

**Note:** After service traffic is switched to Anti-DDoS Pro or Anti-DDoS Premium, the settings take effect based on the TTL values of your DNS records.

-   Your service bandwidth does not exceed 3 Gbit/s, and the QPS does not exceed 10,000.

**Note:** If your service bandwidth and QPS exceed the limits, [submit a ticket](https://workorder-intl.console.aliyun.com/?#/ticket/add/?productId=80) to contact technical support. |
|Domain name status in CDN or DCDN|A CDN- or DCDN-accelerated domain name cannot be added to a sandbox. **Note:** If your domain name is added to a sandbox by CDN or DCDN, we recommend that you use Anti-DDoS Pro or Anti-DDoS Premium and do not enabled CDN interaction. |
|Traffic switchover between CDN or DCDN and Anti-DDoS Pro or Anti-DDoS Premium|To enable CDN or DCDN interaction, you must configure a QPS threshold to trigger traffic switchover between CDN or DCDN and Anti-DDoS Pro or Anti-DDoS Premium. The following requirements must be met:-   Switch from CDN or DCDN to Anti-DDoS Pro or Anti-DDoS Premium
    -   If the QPS exceeds the threshold 3 consecutive times within 3 minutes or more than 6 times within 10 minutes and the service bandwidth on CDN or DCDN does not exceed 10 Gbit/s, the traffic is switched to Anti-DDoS Pro or Anti-DDoS Premium.

**Note:** The maximum service bandwidth that an Anti-DDoS Pro or Anti-DDoS Premium instance can protect is 10 Gbit/s.

    -   If a domain name is added to a sandbox and the service bandwidth on CDN or DCDN does not exceed 10 Gbit/s, the traffic is switched to Anti-DDoS Pro or Anti-DDoS Premium.
-   Switch from Anti-DDoS Pro or Anti-DDoS Premium to CDN or DCDN
    -   If the QPS remains less than 80% of the threshold and the protection success rate against HTTP flood attacks remains less than 10% for more than 12 consecutive hours, the traffic is switched back to CDN or DCDN.
    -   The IP address of the Anti-DDoS Pro or Anti-DDoS Premium instance cannot be in blackhole filtering or traffic scrubbing in the last 60 minutes. Your domain name is not added to a sandbox.
    -   Service traffic can be switched back to CDN or DCND only from 08:00:00 to 23:00:00. |

## Procedure

**Note:** The following procedure describes how to configure CDN or DCDN interaction in the [Anti-DDoS Pro console](https://yundun.console.aliyun.com/?p=ddoscoo). You can also configure CDN interaction in the [CDN console](https://cdn.console.aliyun.com/). For more information, see [Integrate CDN with Anti-DDoS](/intl.en-US/Domain Management/Security configuration/Integrate CDN with Anti-DDoS.md).

1.  Log on to the [Anti-DDoS Pro console](https://yundun.console.aliyun.com/?p=ddoscoo).

2.  In the top navigation bar, select the region where your services are deployed.

    -   **Mainland China**: Anti-DDoS Pro
    -   **Outside Mainland China**: Anti-DDoS Premium
3.  In the left-side navigation pane, choose **Provisioning** \> **Sec-Traffic Manager**.

4.  Click the **CDN/DCDN Interaction** tab.

5.  Find the domain name for which you want to create a CDN or DCDN interaction rule and click **Add Interaction**.

6.  In the **Create Rule** pane, configure the parameters and click **Next**.

    ![Create Rule](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/0102937951/p111665.png)

    |Parameter|Description|
    |---------|-----------|
    |**Anti-DDoS Instance**|The Anti-DDoS Pro or Anti-DDoS Premium instance to which the domain name is added. You do not need to manually select an instance. Make sure that the Anti-DDoS Pro or Anti-DDoS Premium instance uses the **Enhanced** function plan.If the system prompts **To use the CDN interaction feature, you must purchase the Enhanced Function plan for this instance.**, click **Purchase** to upgrade the instance.

If the system prompts **No Anti-DDoS instance selected**, add your domain name to Anti-DDoS Pro or Anti-DDoS Premium. For more information, see [Add a website](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Use domains/Add a website.md). |
    |**Cloud Service**|If your domain name is added to **Alibaba Cloud CDN** or **Dynamic Route for CDN**, you do not need to manually select a service.If your domain name is not added to **Alibaba Cloud CDN** or **Dynamic Route for CDN**, select **Alibaba Cloud CDN** or **Dynamic Route for CDN** and add the domain name as required. |
    |**Request per Second**|The minimum QPS that triggers traffic switchover to Anti-DDoS Pro or Anti-DDoS Premium. For more information, see [Limits](#section_fa8_anx_7lc).**Note:** We recommend that you set the QPS to more than two to three times the historical peak QPS of your website to deal with service spikes. Do not set a QPS lower than 500 even if the QPS of your website is low. |

    After the rule is created, Sec-Traffic Manager assigns a CNAME address for the rule. You can view the CNAME address and interaction status of the domain name on the CDN/DCDN Interaction tab.

7.  Modify the DNS records.

    Modify the DNS records of your domain name on the website of the DNS service provider to point the domain name to the CNAME address provided by Sec-Traffic Manager. For more information, see [Modify the CNAME record to reroute traffic by using Sec-Traffic Manager](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Provisioning settings/Modify the CNAME record to reroute traffic by using Sec-Traffic Manager.md).


## What to do next

-   Edit an interaction rule: Click the **CDN/DCDN Interaction** tab. Find the domain name whose rule you want to edit and click **Edit** in the Actions column to change **Request per Second** under **Trigger Condition**.
-   Delete an interaction rule: Click the **CDN/DCDN Interaction** tab. Find the domain name whose rule you want to delete and click **Delete** in the Actions column.

    **Warning:** Before you delete an interaction rule, make sure that the service traffic is no longer directed to the CNAME address assigned by Sec-Traffic Manager. Otherwise, the website becomes unavailable after you delete the rule.


