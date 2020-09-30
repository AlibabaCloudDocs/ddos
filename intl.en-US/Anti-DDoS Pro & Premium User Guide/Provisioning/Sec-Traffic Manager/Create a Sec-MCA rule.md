# Create a Sec-MCA rule

To add a Sec-MCA rule, you must purchase an Anti-DDoS Premium Insurance or Unlimited instance and an Anti-DDoS Premium Sec-MCA instance. You can direct traffic from all ISPs in mainland China \(excluding China Mobile\) to the IP address of the Sec-MCA instance and direct traffic from China Mobile and regions outside mainland China to the IP address of the Anti-DDoS Premium instance.

-   A **Sec-MCA** instance is purchased, and your service is added to the instance. For more information, see [Purchase a Sec-MCA plan for an Anti-DDoS Premium instance](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Purchase mitigation plans for Anti-DDoS Pro and Anti-DDoS Premium.md) and [Configure Anti-DDoS Premium Sec-MCA](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Configure Anti-DDoS Premium Sec-MCA.mdstep_lrw_qsw_3k0).

    **Note:** You only need to add your service to the Sec-MCA instance and do not need to modify DNS records of the domain name.


Sec-MCA accelerates service access in scenarios where your service is deployed outside mainland China but your users reside in mainland China. It also mitigates volumetric DDoS attacks on the networks of ISPs in mainland China, excluding China Mobile.

If you want to provide quick and stable access for all users, including users in and outside mainland China and users from various ISPs, such as China Unicom and China Mobile, you can use the Sec-MCA instance together with the Anti-DDoS Premium Insurance or Unlimited instance. The following figure shows how Sec-MCA and Anti-DDoS Premium work.

For more information, see [Configure Anti-DDoS Premium Sec-MCA](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Configure Anti-DDoS Premium Sec-MCA.md).

## Procedure

1.  Log on to the [Anti-DDoS Pro console](https://yundun.console.aliyun.com/?p=ddoscoo).

2.  In the top navigation bar, select **Outside Mainland China**.

3.  In the left-side navigation pane, choose **Provisioning** \> **Sec-Traffic Manager**.

4.  On the **General** tab, click **Create Rule**.

5.  In the **Create Rule** pane, configure a **Sec-MCA** rule and click **Next**.

    |Parameter|Description|
    |---------|-----------|
    |**Interaction Scenario**|Select **Sec-MCA**.|
    |**Name**|Specify the name of the rule. The rule name can be up to 128 characters in length and can contain letters, digits, and underscores \(\_\). |
    |**Sec-MCA**|Select the IP address of the Sec-MCA instance.|
    |**Anti-DDoS Premium**|Select an Anti-DDoS Pro or Anti-DDoS Premium instance.|

    After the rule is created, Sec-Traffic Manager assigns a CNAME address for the rule. You can view the created rule and **CNAME** address in the rule list.

6.  Modify the DNS records.

    Modify the DNS records of your domain name on the website of the DNS service provider to point the domain name to the CNAME address provided by Sec-Traffic Manager. For more information, see [Modify the CNAME record to reroute traffic by using Sec-Traffic Manager](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Provisioning settings/Modify the CNAME record to reroute traffic by using Sec-Traffic Manager.md).


## What to do next

-   Edit an interaction rule: On the **General** tab, find the rule that you want to edit and click **Edit** in the Actions column. You can modify parameters except **Interaction Scenario** and **Name**.
-   Delete an interaction rule: On the **General** tab, find the rule that you want to delete and click **Delete** in the Actions column.

    **Warning:** Before you delete an interaction rule, make sure that the service traffic is no longer directed to the CNAME address assigned by Sec-Traffic Manager. Otherwise, your service becomes unavailable after you delete the rule.


