# Sec-MCA billing methods

This topic describes the billing methods of Anti-DDoS Premium Secure Mainland China Acceleration \(Sec-MCA\).

## Overview

Anti-DDoS Premium Sec-MCA supports only the **subscription** billing method. Before you use Anti-DDoS Premium Sec-MCA to protect your services, you must purchase an Anti-DDoS Premium Sec-MCA instance, and specify the function plan, instance specifications, and subscription period. An Anti-DDoS Premium Sec-MCA instance provides access acceleration and DDoS mitigation services within the subscription period.

## Pricing

The following table lists the prices of an Anti-DDoS Premium Sec-MCA instance at different **clean bandwidths**1 when the default specifications are used. Anti-DDoS Premium Sec-MCA provides a standard function plan and an enhanced function plan. Fees vary based on the function plan that you choose. For more information, see [Function plan](/intl.en-US/Pricing/Function plan.md).

-   **1Clean bandwidth**

    Clean bandwidth refers to the maximum bandwidth that an Anti-DDoS Premium Sec-MCA instance can use to handle services if no attacks are launched. Make sure that the clean bandwidth of the instance is greater than the peak bandwidth of the inbound and outbound traffic of all the protected services.

    **Warning:** If the actual bandwidth exceeds the clean bandwidth of the instance, throttling and packet loss can occur. In some cases, your services become unavailable or slow down within a period of time.


**Note:** If the specifications of clean bandwidth listed in the following table cannot meet your business needs, [submit a ticket](https://workorder-intl.console.aliyun.com/?#/ticket/add/?productId=80).

|Clean bandwidth|Unit price of a standard function plan \(USD/month\)|Unit price of an enhanced function plan \(USD/month\)|
|---------------|----------------------------------------------------|-----------------------------------------------------|
|10 Mbit/s|15,480|16,680|
|20 Mbit/s|17,028|18,228|
|30 Mbit/s|18,576|19,776|
|40 Mbit/s|20,124|21,324|
|50 Mbit/s|21,672|22,872|
|60 Mbit/s|23,220|24,420|
|70 Mbit/s|24,768|25,968|
|80 Mbit/s|26,316|27,516|
|90 Mbit/s|27,864|29,064|
|100 Mbit/s|29,412|30,612|
|150 Mbit/s|37,152|38,352|
|200 Mbit/s|44,892|46,092|

The following table lists the default specifications of an Anti-DDoS Premium Sec-MCA instance and the prices for upgrades. If the default specifications cannot meet your needs, specify higher specifications when you purchase the instance or upgrade the instance after you purchase it.

|Specification|Description|Default value|Price for upgrades|
|-------------|-----------|-------------|------------------|
|Number of protected ports|The number of TCP and UDP ports that the instance protects.|5|Every 5 ports: USD 150/month|
|Number of protected domains|The number of HTTP and HTTPS domains that the instance protects.|10 **Note:** The 10 domain names can belong to only one top-level domain name. This means that the domain names protected by an instance must belong to the same top-level domain name.

|-   Standard function plan: USD 45/month for every 10 domains
-   Enhanced function plan: USD 75/month for every 10 domains

**Note:** For every plan you purchase, the total number of supported top-level domains increases by one. |
|Queries per second \(QPS\)|The maximum number of HTTP and HTTPS requests that the instance can concurrently process per second if no attacks are detected|500 QPS|Every 100 QPS: USD 150/month|

## Instance expiration

|Instance status|Description|
|---------------|-----------|
|Before expiration|Alibaba Cloud sends you text messages and emails seven days, three days, and one day before your instance expires to remind you to renew your subscription.|
|Within 30 days after expiration|-   Impact on mitigation:

If you do not renew the subscription of your Anti-DDoS Premium Sec-MCA instance before it expires, the instance stops access acceleration and DDoS attack mitigation upon expiration. The DDoS mitigation capacity for protected assets is restored to the free protection capacity.

-   Impact on configurations:

After an Anti-DDoS Premium Sec-MCA instance expires, the configurations are retained for 30 days. If you renew the subscription of your instance within 30 days, you can still use the instance with the retained configurations. |
|30 days after expiration|If you do not renew the subscription of your Anti-DDoS Premium Sec-MCA instance within 30 days after the instance expires, the instance and its configurations are released. If you need to continue using Anti-DDoS Premium Sec-MCA, you must purchase another Anti-DDoS Premium Sec-MCA instance and complete the configurations.|

## Refunding

The subscription of an Anti-DDoS Premium Sec-MCA instance cannot be canceled before the expiration date. The subscription fees cannot be refunded after you purchase the instance. After an Anti-DDoS Premium Sec-MCA instance is created, the fees you paid cannot be refunded.

## References

-   [Purchase a Sec-MCA plan for an Anti-DDoS Premium instance](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Purchase mitigation plans for Anti-DDoS Pro and Anti-DDoS Premium.md)
-   [Configure Anti-DDoS Premium Sec-MCA](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Configure Anti-DDoS Premium Sec-MCA.md)

