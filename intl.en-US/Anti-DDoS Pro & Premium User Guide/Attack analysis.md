# Attack analysis

After you add your service to Anti-DDoS Pro, you can view events and details of attacks on the Attack Analysis page to learn about the protection effects. This topic describes how to view information on the Attack Analysis page.

-   An Anti-DDoS Pro instance is purchased. For more information, see [Purchase mitigation plans for Anti-DDoS Pro and Anti-DDoS Premium](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Purchase mitigation plans for Anti-DDoS Pro and Anti-DDoS Premium.md).

    **Note:** Only Anti-DDoS Pro supports attack analysis. If your service is added to Anti-DDoS Premium, you can view information about traffic protection on the **Security Overview** page. For more information, see [Check security overview](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Check security overview.md).

-   Your service is added to Anti-DDoS Pro.
    -   For more information about how to add a website service, see [Add a website](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Use domains/Add a website.md).
    -   For more information about how to add a non-website service, such as a client game, mobile game, and app, see [Create forwarding rules](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Use ports/Create forwarding rules.md).

The **Attack Analysis** page in the Anti-DDoS Pro console shows events and details of DDoS attacks, including web resource exhaustion attacks, connection flood attacks, and volumetric attacks. On the **Attack Analysis** page, you can view information of an attack event, such as the attack target, start time, end time, and peak attack traffic. You can also provide feedback on the protection effect.

For more information about DDoS attack types, see [Common DDoS attack types](/intl.en-US/DDoS Protection Guide/Introduction to DDoS attacks.md).

For **volumetric attacks**, you can view details of attack events on the **Attack Analysis** page. The details include attack source IP addresses, attack types, attack source areas, and attack source ISPs. This visualizes the attack protection process and improves the protection analysis experience.

**Note:** Event details are not supported for connection flood attacks and web resource exhaustion attacks.

1.  Log on to the [Anti-DDoS Pro console](https://yundun.console.aliyun.com/?p=ddoscoo).

2.  In the top navigation bar, select **Mainland China**.

3.  In the left-side navigation pane, click **Attack Analysis**.

4.  On the **Attack Analysis** page, select an attack type and time range to query attack events.

    -   Attack type: Select **Web Resource Exhaustion Attack**, **Connection Flood Attack**, **Volumetric Attack**, or **All attack types**.
    -   Time range: Select **One Day**, **Seven Days**, or **One Month** or specify a time range. You can query attack events over the last 180 days.
    ![Attack Analysis](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/9539022061/p170724.png)

    The **Attack Analysis** page shows the following information:

    -   On the upper part of the page, **Peak of Volumetric Attack \(bps\)**, **Peak of Connection Flood Attack \(cps\)**, and **Peak of Web Resource Exhaustion Attack \(qps\)** are displayed.
    -   On the lower part of the page, the attack events are displayed. The information of each attack event contains **Attack type**, **Attack target**, **Starting and ending time**, and **Peak of Attack**.
    If you have suggestions or questions about the protection effect of an attack event, click **Feedback** in the Actions column to submit your feedback. Anti-DDoS Pro will continue to optimize and improve the protection effect based on your suggestions.

    ![Feedback](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/9539022061/p170726.png)

5.  View details of a **Volumetric Attack** event.

    You can view details of a **Volumetric Attack** event. Event details are not supported for connection flood attacks and web resource exhaustion attacks.

    On the **Attack Analysis** page, find a **Volumetric Attack** event and click **View details** in the Actions column. The **Details of the incident** page appears. You can view the event details and configure protection settings.

    ![Details of the incident](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/9539022061/p170725.png)

    The **Details of the incident** page contains the following information:

    -   **Attack Time**, **Attack Target**, **Peak of attack bandwidth \(Gbps\)**, and **Peak of attack packet \(Kpps\)**: You can click **Mitigation Settings** next to **Attack Target** to go to the **General Policies** page. On this page, you can modify the protection settings.
    -   **Attack protection details**: shows the trends of inbound and outbound traffic, traffic scrubbing bandwidth, and traffic scrubbing packets during the attack.
    -   **Attack source IP**: shows the list of attack source IP addresses and source areas. You can click **More** to view distribution of the source IP addresses.

        If you want to block traffic from specific IP addresses, click **Blacklist Settings** in the lower-left corner of the Attack source IP section. On the **General Policies** page, configure **Blacklist and Whitelist \(Instance IP\)**. For more information, see [Configure a blacklist and whitelist for an instance IP address](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Protection settings/Protection for infrastructure/Configure a blacklist and whitelist for an instance IP address.md).

    -   **Attack source area**: shows source area distribution of attack traffic. You can click **More** to view proportions of requests from different areas.

        If you want to block traffic from specific areas, click **Geo-blocking Settings** in the lower-left corner of the Attack source area section. On the **General Policies** page, configure **Blocked Regions**. For more information, see [Configure blocked regions](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Protection settings/Protection for infrastructure/Configure blocked regions.md).

    -   **Attack source ISP**: shows source ISP distribution of attack traffic. You can click **More** to view proportions of requests from different ISP networks.
    -   **Attack type**: shows distribution of attack types. You can click **More** to view proportions of different attack types.

