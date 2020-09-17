# Mainland China Acceleration billing methods

This topic describes the billing methods of Anti-DDoS Premium Mainland China Acceleration \(MCA\). Before you use MCA, you must purchase an Anti-DDoS Premium instance. You can purchase an Anti-DDoS Premium instance to defend against DDoS attacks for services that are deployed outside mainland China. If no attacks are launched, you can use MCA to accelerate service delivery to users in mainland China.

## Overview

MCA is suitable for services that are deployed in regions outside mainland China and are protected by Anti-DDoS Premium. If no attack is launched against your Anti-DDoS Premium instance, you can use MCA to accelerate service delivery to users in mainland China.

**Note:** An MCA instance does not offer any protection and must be used with an Anti-DDoS Premium Insurance Plan or Unlimited Plan instance.

MCA instances support only the **subscription** billing method. Before you use MCA, you must purchase an MCA instance, and specify the specifications and the subscription period. An MCA instance provides acceleration for services that are added to Anti-DDoS Premium within the subscription period.

## Pricing

The following table lists the prices of an MCA instance based on different **clean bandwidths**1.

-   **1**Clean bandwidth****

    Clean bandwidth refers to the maximum bandwidth that an MCA instance can use to accelerate service delivery if no attacks are launched. The clean bandwidth of an MCA instance must be greater than the peak volume of the inbound and outbound traffic of the protected services.

    **Warning:** If the actual bandwidth exceeds the clean bandwidth of the instance, throttling and packet loss can occur. In some cases, your services become unavailable or slow down within a period of time.


|Clean bandwidth|Unit price \(USD/month\)|
|---------------|------------------------|
|10 Mbit/s|1,548|
|20 Mbit/s|3,096|
|30 Mbit/s|4,643|
|40 Mbit/s|6,191|
|50 Mbit/s|7,739|
|60 Mbit/s|9,287|
|70 Mbit/s|10,834|
|80 Mbit/s|12,382|
|90 Mbit/s|13,930|
|100 Mbit/s|15,478|

## Instance expiration

|Instance status|Description|
|---------------|-----------|
|Before expiration|Alibaba Cloud sends you text messages and emails seven days, three days, and one day before your instance expires to remind you to renew your subscription.|
|Within 30 days after expiration|-   Impact on acceleration:

You must renew the subscription of your MCA instance before the expiration date. After the MCA instance expires, it stops accelerating service delivery.

-   Impact on instance configurations:

The configurations of an expired MCA instance are retained for 30 days. To continue using the MCA instance with the retained configurations, renew the subscription of your MCA instance within 30 days after the expiration date. |
|30 days after expiration|If you do not renew the subscription of your MCA instance within 30 days after the instance expires, the instance and the instance configurations are automatically released. To continue using the acceleration service, you must purchase another MCA instance.|

## References

-   [Purchase an MCA plan for an Anti-DDoS Premium instance](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Purchase mitigation plans for Anti-DDoS Pro and Anti-DDoS Premium.md)
-   [Configure Anti-DDoS Premium MCA](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Configure Anti-DDoS Premium MCA.md)

