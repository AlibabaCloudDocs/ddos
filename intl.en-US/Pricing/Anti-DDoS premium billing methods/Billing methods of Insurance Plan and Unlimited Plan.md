# Billing methods of Insurance Plan and Unlimited Plan

This topic describes the billing methods of Anti-DDoS Premium Insurance Plan and Unlimited Plan.

## Overview

Anti-DDoS Premium provides **advanced mitigation**1 to protect your services that are deployed in regions outside mainland China against DDoS attacks. The number of advanced mitigation sessions that you can use varies based on the mitigation plan that you purchase: **Insurance Plan**2 and **Unlimited Plan**3.

Anti-DDoS Premium supports only the **subscription** billing method. Before you use Anti-DDoS Premium to protect your services, you must purchase an Anti-DDoS Premium instance. When you purchase an Anti-DDoS Premium instance, you must specify the mitigation plan, the instance specifications, and the subscription period. An Anti-DDoS Premium instance provides advanced mitigation within the specified subscription period.

-   **1Advanced mitigation**

    Advanced mitigation integrates with all Alibaba Cloud Anti-DDoS scrubbing centers outside mainland China to protect your services from DDoS attacks.

    Services protected by Anti-DDoS Premium are less vulnerable to DDoS attacks. In most cases, the goal of DDoS attacks is to cause loss to the victims. However, because the cost of launching a DDoS attack is relatively high, the attackers tend to stop their attack if they cannot achieve their goal within their target time frame.

    Anti-DDoS Premium provides unlimited advanced mitigation sessions, and integrates with all Alibaba Cloud Anti-DDoS scrubbing centers outside mainland China to safeguard your services.

    **Note:** If the attacks launched against your services threaten the infrastructure of Anti-DDoS scrubbing centers, Alibaba Cloud reserves the rights to throttle the network traffic. If throttling is triggered for your Anti-DDoS Premium instance, your services may be adversely affected. For example, the network traffic may be throttled or even routed to a blackhole in some cases.

-   **2Insurance Plan**

    Insurance Plan is an entry-level mitigation plan for Anti-DDoS Premium. It provides two advanced mitigation sessions per month. Insurance Plan is suitable for users who are less likely to be targeted. If a DDoS attack that is targeted at your services is detected, an advanced mitigation session is triggered to provide unlimited mitigation over the next 24 hours. The number of available advanced mitigation sessions is automatically reset to two on the first day of each month.

    For example, a volumetric DDoS attack on a protected IP address is detected at 11:20:00 \(UTC+8\) on September 12, 2019, and an advanced mitigation session is triggered. One advanced mitigation session is consumed to provide unlimited protection for the IP address over the next 24 hours. Then, another volumetric DDoS attack on the same address is detected at 18:50:00 \(UTC+8\) on September 13, 2019, and an advanced mitigation session is triggered again. However, because this attack happened more than 24 hours after the first attack, another advanced mitigation session is consumed. This exhausts the two sessions included in Anti-DDoS Premium Insurance Plan for September. The number of available advanced mitigation sessions is reset to two on October 1, 2019.

    ![Billing example](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/2930937951/p35184.png)

    **Note:** If the two advanced mitigation sessions provided per month cannot meet your business needs, we recommend that you purchase global advanced mitigation. For more information, see [Billing methods for global advanced mitigation](/intl.en-US/Pricing/Anti-DDoS premium billing methods/Billing methods for global advanced mitigation.md).

-   **3Unlimited Plan**

    Anti-DDoS Premium Unlimited Plan provides unlimited mitigation sessions. If you purchase Unlimited Plan, Anti-DDoS Premium provides unlimited mitigation sessions to protect your services against DDoS attacks.


## Pricing

The following table lists prices of an Anti-DDoS Premium instance based on different **clean bandwidths**4 when the default specifications are used. Anti-DDoS Premium provides a standard function plan and an enhanced function plan. Fees vary based on the function plan that you choose. For more information about the standard function plan and the enhanced function plan, see [Function plan](/intl.en-US/Pricing/Function plan.md).

-   **4Clean bandwidth**

    Clean bandwidth refers to the maximum bandwidth that an Anti-DDoS Premium instance can use to handle services if no attacks are launched. The clean bandwidth of an instance must be greater than the peak volume of the inbound and outbound traffic of the protected services.

    **Warning:** If the actual bandwidth exceeds the clean bandwidth of the instance, throttling and packet loss can occur. In some cases, your services become unavailable or slow down within a period of time.


**Note:** If the specifications of clean bandwidth listed in the following table cannot meet your business needs, [submit a ticket](https://workorder-intl.console.aliyun.com/?#/ticket/add/?productId=80).

|Mitigation plan|Clean bandwidth|Unit price in a standard function plan \(USD/month\)|Unit price in an enhanced function plan \(USD/month\)|
|---------------|---------------|----------------------------------------------------|-----------------------------------------------------|
|**Insurance Plan**Two advanced mitigation sessions/month

|100 Mbit/s|2,630|3,830|
|150 Mbit/s|3,420|4,620|
|200 Mbit/s|4,210|5,410|
|250 Mbit/s|5,000|6,200|
|300 Mbit/s|5,570|6,770|
|**Unlimited Plan**Unlimited advanced mitigation sessions

|100 Mbit/s|11,560|12,760|
|150 Mbit/s|12,610|13,810|
|200 Mbit/s|13,660|14,860|
|250 Mbit/s|14,720|15,920|
|300 Mbit/s|15,770|16,970|

The following table lists the default specifications of an Anti-DDoS Premium instance and the prices for upgrades. If the default specifications cannot meet your needs, you can specify higher specifications when you purchase the instance. You can also upgrade the instance after you purchase it.

|Specification|Description|Default value|Price for upgrades|
|-------------|-----------|-------------|------------------|
|Number of protected ports|The number of TCP and UDP ports that the instance protects.|5|Every 5 ports: USD 150/month|
|Number of protected domains|The number of HTTP and HTTPS domains that the instance protects.|10 **Note:** The 10 domain names can belong to only one top-level domain name. This means that the domain names protected by an instance must belong to the same top-level domain name.

|-   Standard function plan: USD 45/month for every 10 domains
-   Enhanced function plan: USD 75/month for every 10 domains

**Note:** For every plan you purchase, the total number of supported top-level domains increases by one. |
|Queries per second \(QPS\)|The maximum number of HTTP and HTTPS requests that the instance can concurrently process per second if no attacks are detected|-   Insurance Plan: 500 QPS
-   Unlimited Plan: 1,000 QPS

|Every 100 QPS: USD 150/month|

## Instance expiration

|Instance status|Description|
|---------------|-----------|
|Before expiration|Alibaba Cloud sends you text messages and emails seven days, three days, and one day before your instance expires to remind you to renew your subscription.|
|Within 30 days after expiration|-   Impact on mitigation:

If the subscription of an Anti-DDoS Premium instance is not renewed before the expiration date, the protection stops after the instance expires. The mitigation capacity is restored to the default free protection capacity.

-   Impact on instance configurations:

After an Anti-DDoS Premium instance expires, the configurations are retained for 30 days. If you renew the subscription of the instance within 30 days, you can still use the instance with the retained configurations. |
|30 days after expiration|If you do not renew the subscription of your Anti-DDoS Premium instance within 30 days after the instance expires, the instance and the instance configurations are automatically released. If you want to continue using Anti-DDoS Premium, you must purchase another Anti-DDoS Premium instance and complete the configurations.|

## Refunding

The subscription of an Anti-DDoS Premium instance cannot be canceled before the expiration date. The subscription fees cannot be refunded after you purchase the instance. After an Anti-DDoS Premium instance is created, the fees you paid cannot be refunded.

## References

-   [Purchase insurance and unlimited plans for Anti-DDoS Premium instances](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Purchase mitigation plans for Anti-DDoS Pro and Anti-DDoS Premium.md)
-   [Upgrade the specifications of an Anti-DDoS Pro or Anti-DDoS Premium instance](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Resource management/Upgrade the specifications of an Anti-DDoS Pro or Anti-DDoS Premium instance.md)

