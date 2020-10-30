# Use the attack analysis feature

After you add your service to Anti-DDoS Pro, you can view the events and details of attacks on the Attack Analysis page. This allows you to obtain an overview of the protection status. You can also provide feedback on protection effectiveness. This topic describes how to view information on the Attack Analysis page.

-   An Anti-DDoS Pro instance is purchased. For more information, see [Purchase mitigation plans for Anti-DDoS Pro and Anti-DDoS Premium](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Purchase mitigation plans for Anti-DDoS Pro and Anti-DDoS Premium.md).

    **Note:** Only Anti-DDoS Pro supports attack analysis. If your service is added to Anti-DDoS Premium, you can view the protection status of your service traffic on the **Security Overview** page. For more information, see [Check security overview](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Check security overview.md).

-   Your service is added to Anti-DDoS Pro.
    -   For more information about how to add website services, see [Add a website](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Use domains/Add a website.md).
    -   For more information about how to add non-website services, such as client games, mobile games, and apps, see [Create forwarding rules](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Use ports/Create forwarding rules.md).

The **Attack Analysis** page in the Anti-DDoS Pro console shows the events and details of distributed denial of service \(DDoS\) attacks. The attacks include web resource exhaustion attacks, connection flood attacks, and volumetric attacks. On the **Attack Analysis** page, you can view information of an attack event, such as the attack target, start time, end time, and peak attack traffic. You can also provide feedback on protection effectiveness.

For more information about DDoS attack types, see [Common DDoS attack types](/intl.en-US/DDoS Protection Guide/Introduction to DDoS attacks.md).

For volumetric DDoS attacks, you can view the details of attack events on the **Attack Analysis** page. The details include the source IP addresses, source areas, source Internet service provider \(ISP\) networks, and attack types. This allows the visualization of the attack mitigation process and improves the user experience of protection analysis.

**Note:** Event details are not provided for connection flood attacks or web resource exhaustion attacks.

1.  Log on to the [Anti-DDoS Pro console](https://yundun.console.aliyun.com/?p=ddoscoo).

2.  In the top navigation bar, select **Mainland China**.

3.  In the left-side navigation pane, click **Attack Analysis**.

4.  On the **Attack Analysis** page, select an attack type and time range to query attack events.

    -   Attack type: Select **Web Resource Exhaustion Attack**, **Connection Flood Attack**, **Volumetric Attack**, or **All attack types**.
    -   Time range: Select **One Day**, **Seven Days**, or **One Month**. Alternatively, specify a specific time range. You can query attack events over the last 180 days.
    ![Attack Analysis](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/9539022061/p170724.png)

    The **Attack Analysis** page shows the following information:

    -   In the upper part of the page, **Peak of Volumetric Attack \(bps\)**, **Peak of Connection Flood Attack \(cps\)**, and **Peak of Web Resource Exhaustion Attack \(qps\)** are displayed.
    -   In the lower part of the page, the attack events are displayed. The information of each attack event contains **Attack type**, **Attack target**, **Starting and ending time**, and **Peak of Attack**.
    If you have suggestions or questions about the protection effectiveness on an attack event, click **Feedback** in the Actions column to submit your feedback. All suggestions will be greatly appreciated.

5.  View the details of a **Volumetric Attack** event.

    You can view the details of a **Volumetric Attack** event. Event details are not provided for connection flood attacks or web resource exhaustion attacks.

    On the **Attack Analysis** page, find a **Volumetric Attack** event and click **View details** in the Actions column. The **Details of the incident** page appears. You can view the event details and configure protection settings.

    ![Details of the incident](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/9539022061/p170725.png)

    The **Details of the incident** page shows the following information:

    -   In the upper part of the page, **Attack Time**, **Attack Target**, **Peak of attack bandwidth \(Gbps\)**, and **Peak of attack packet \(Kpps\)** are displayed. You can click **Mitigation Settings** for **Attack Target** to go to the **General Policies** page. On this page, you can modify the protection settings.
    -   **Attack protection details**: shows the trends of inbound and outbound traffic, traffic scrubbing bandwidth, and traffic scrubbing packets during the attack.
    -   **Attack source IP**: shows the source areas and IP addresses of attacks. In the list, the top 10 IP addresses from which the most attacks are initiated are displayed. You can click **More** to view information about the top 100 IP addresses.

        If you want to block traffic from specific IP addresses, click **Blacklist Settings** in the lower-left corner of the Attack source IP section. On the **General Policies** page, configure **Blacklist and Whitelist \(Instance IP\)**. For more information, see [Configure a blacklist and whitelist for an instance IP address](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Protection settings/Protection for infrastructure/Configure a blacklist and whitelist for an instance IP address.md).

    -   **Attack source area**: shows the distribution of areas from which attack traffic is originated. You can click **More** to view the proportions of requests from different areas.

        If you want to block traffic from specific areas, click **Geo-blocking Settings** in the lower-left corner of the Attack source area section. On the **General Policies** page, configure **Blocked Regions**. For more information, see [Configure blocked regions](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Protection settings/Protection for infrastructure/Configure blocked regions.md).

    -   **Attack source ISP**: shows the distribution of ISP networks from which attack traffic is originated. You can click **More** to view the proportions of requests from different ISP networks.
    -   **Attack type**: shows the distribution of attack types. You can click **More** to view the proportions of different attack types.

