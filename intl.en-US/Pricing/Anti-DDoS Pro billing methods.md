# Anti-DDoS Pro billing methods

This topic describes the billing methods of Anti-DDoS Pro.

## Overview

Anti-DDoS Pro provides **basic protection** and **burstable protection** to safeguard your services that are deployed in mainland China. You are charged for these protection services based on the following billing methods:

-   Basic protection: subscription billing \(billed monthly\)

    Before you use Anti-DDoS Pro, you must purchase an Anti-DDoS Pro instance. When you purchase an Anti-DDoS Pro instance, you must specify the specifications and the subscription period. An Anti-DDoS Pro instance provides basic protection within the subscription period.

    Assume that you have purchased a basic protection bandwidth of 30 Gbit/s for an Anti-DDoS Pro instance. If the peak bandwidth of DDoS attacks is 30 Gbit/s or lower, no additional fees are charged.

-   Burstable protection: pay-as-you-go \(billed daily\)

    You can enable burstable protection based on your business needs. To enable burstable protection, specify a burstable protection bandwidth that is higher than the basic protection bandwidth. When the attack bandwidth is higher than the basic protection bandwidth but no higher than the burstable protection bandwidth, Anti-DDoS Pro can still mitigate DDoS attacks. Burstable protection is charged based on the difference between the peak bandwidth of the DDoS attacks on the day and the basic protection bandwidth.

    For example, the basic protection bandwidth of your Anti-DDoS Pro instance is 30 Gbit/s and the burstable protection bandwidth is 100 Gbit/s. Then, burstable protection is charged for mitigating DDoS attacks with a peak bandwidth between 30 Gbit/s and 100 Gbit/s. If the peak bandwidth of the DDoS attacks exceeds the burstable protection bandwidth, the instance is unable to mitigate the attacks. In this case, no additional fee is charged. If the peak bandwidth of DDoS attacks is 30 Gbit/s or lower, only basic protection is triggered. In this case, no fee is charged for burstable protection.


For more information, visit the [Anti-DDoS pricing page](https://www.alibabacloud.com/product/ddos/pricing#product_tab1-3).

## Basic protection: subscription billing \(billed monthly\)

The following table lists the prices of an Anti-DDoS Pro instance based on different basic protection bandwidths when the default specifications are used. An Anti-DDoS Pro instance provides a standard function plan and an enhanced function plan. The prices vary based on the function plan. For more information about the standard function plan and the enhanced function plan, see [Function plan](/intl.en-US/Pricing/Function plan.md).

**Note:** If the protection bandwidths listed in the following table cannot meet your business needs, [ticket](https://workorder-intl.console.aliyun.com/?#/ticket/add/?productId=80).

|Basic protection bandwidth|Line|Price \(standard function plan\)|Price \(enhanced function plan\)|
|--------------------------|----|--------------------------------|--------------------------------|
|30 Gbit/s|Eight BGP lines|USD 3,120/month|USD 4,320/month|
|60 Gbit/s|USD 7,020/month|USD 8,220/month|
|100 Gbit/s|USD 49,230/year \(available only for annual subscription\)|USD 63,630/year \(available only for annual subscription\)|
|300 Gbit/s|USD 79,260/year \(available only for annual subscription\)|USD 93,660/year \(available only for annual subscription\)|
|400 Gbit/s|USD 145,300/year \(available only for annual subscription\)|USD 159,700/year \(available only for annual subscription\)|
|500 Gbit/s|USD 563,430/year \(available only for annual subscription\)|USD 577,830/year \(available only for annual subscription\)|
|600 Gbit/s|USD 670,610/year \(available only for annual subscription\)|USD 685,010/year \(available only for annual subscription\)|

The following table lists the default specifications of an Anti-DDoS Pro instance and the price for upgrades. If the default specifications cannot meet your needs, you can specify higher specifications when you purchase the instance. You can also upgrade the instance after you purchase it.

|Specification|Description|Default value|Price for upgrades|
|-------------|-----------|-------------|------------------|
|Number of protected ports|The number of TCP and UDP ports that the instance protects.|50|Every 5 ports: USD 37.5/month|
|Number of protected domains|The number of HTTP and HTTPS domains that the instance protects.|50 **Note:** The domain names that you add to an instance can belong to up to five top-level domain names.

|-   Standard function plan: USD 4.5/month for every 10 domains
-   Enhanced function plan: USD 7.5/month for every 10 domains

**Note:** For every plan you purchase, the total number of supported top-level domains increases by one. |
|Clean bandwidth|The maximum bandwidth that the instance uses to handle services if no attacks are launched.|100 Mbit/s|1 Mbit/s: USD 15/month**Note:** If your clean bandwidth exceeds 600 Mbit/s, you are charged a monthly fee of USD 11/month per Mbit/s for the extra bandwidth usage. |
|Queries per second \(QPS\)|The maximum number of HTTP and HTTPS requests that the instance can concurrently process per second if no attacks are launched.|3,000 QPS|Every 100 QPS: USD 150/month|

## Burstable protection \(pay-as-you-go on a daily basis\)

Anti-DDoS Pro provides burstable protection to safeguard your services when the peak bandwidth of DDoS attacks exceeds the basic protection bandwidth. Burstable protection is charged based on the difference between the peak bandwidth of DDoS attacks on the day and the basic protection bandwidth.

**Note:** If you specify the same value for the burstable protection bandwidth and the basic protection bandwidth, no additional fee is charged. However, your Anti-DDoS Pro instance does not provide burstable protection.

Billing:

-   If the peak bandwidth of DDoS attacks on the day is lower than or equal to the basic protection bandwidth, no fee is charged for burstable protection.
-   If the peak bandwidth of DDoS attacks on the day is higher than the burstable protection bandwidth, no fee is charged for burstable protection. In this case, network traffic destined for the domain that is protected by an Anti-DDoS Pro instance is routed to the blackhole.
-   The bill for the burstable protection service you use each day is generated between 08:00:00 to 09:00:00 the following day.

For example, the basic protection bandwidth of your Anti-DDoS Pro instance is 30 Gbit/s and the burstable protection bandwidth is 100 Gbit/s. Two DDoS attacks are launched against the instance on the same day. The peak bandwidths of the two DDoS attacks are 80 Gbit/s and 40 Gbit/s, both of which exceed the basic protection bandwidth. Burstable protection is charged based on the higher peak bandwidth \(80 Gbit/s\). The difference between the peak bandwidth and the basic protection bandwidth \(30 Gbit/s\) is 50 Gbit/s. In this case, Anti-DDoS Pro charges USD 960 for burstable protection.

The following table lists prices of burstable protection based on different pricing tiers.

|Pricing tier|Price of burstable protection \(USD/day\)|
|------------|-----------------------------------------|
|0 Gbit/s < Bandwidth difference ≤ 5 Gbit/s|120|
|5 Gbit/s < Bandwidth difference ≤ 10 Gbit/s|180|
|10 Gbit/s < Bandwidth difference ≤ 20 Gbit/s|330|
|20 Gbit/s < Bandwidth difference ≤ 30 Gbit/s|540|
|30 Gbit/s < Bandwidth difference ≤ 40 Gbit/s|730|
|40 Gbit/s < Bandwidth difference ≤ 50 Gbit/s|960|
|50 Gbit/s < Bandwidth difference ≤ 60 Gbit/s|1,170|
|60 Gbit/s < Bandwidth difference ≤ 70 Gbit/s|1,380|
|70 Gbit/s < Bandwidth difference ≤ 80 Gbit/s|1,590|
|80 Gbit/s < Bandwidth difference ≤ 100 Gbit/s|1,770|
|100 Gbit/s < Bandwidth difference ≤ 150 Gbit/s|2,190|
|150 Gbit/s < Bandwidth difference ≤ 200 Gbit/s|3,240|
|200 Gbit/s < Bandwidth difference ≤ 300 Gbit/s|4,200|
|300 Gbit/s < Bandwidth difference ≤ 400 Gbit/s|6,000|
|400 Gbit/s < Bandwidth difference ≤ 500 Gbit/s|7,510|
|500 Gbit/s < Bandwidth difference ≤ 600 Gbit/s|9,010|
|600 Gbit/s < Bandwidth difference ≤ 700 Gbit/s|10,510|
|700 Gbit/s < Bandwidth difference ≤ 800 Gbit/s|12,010|
|800 Gbit/s < Bandwidth difference ≤ 900 Gbit/s|13,510|
|900 Gbit/s < Bandwidth difference ≤ 1,000 Gbit/s|15,010|
|1,000 Gbit/s < Bandwidth difference ≤ 1,100 Gbit/s|16,510|
|1,100 Gbit/s < Bandwidth difference ≤ 1,200 Gbit/s|18,010|
|1,200 Gbit/s < Bandwidth difference ≤ 1,300 Gbit/s|19,510|
|1,300 Gbit/s < Bandwidth difference ≤ 1,400 Gbit/s|21,010|
|1,400 Gbit/s < Bandwidth difference ≤ 1,500 Gbit/s|22,520|

## Instance expiration

|Instance status|Description|
|---------------|-----------|
|Before expiration|Alibaba Cloud sends you text messages, emails, and internal messages seven days, three days, and one day before your Anti-DDoS Pro instance expires to remind you to renew your subscription.|
|Within seven days after expiration|-   Impact on protection:

If you do not renew the subscription of your Anti-DDoS Pro instance before the expiration date, the expired instance stops providing burstable protection and restores the protection bandwidth to the default bandwidth \(5 Gbit/s\). However, the Anti-DDoS Pro instance still forwards your network traffic within seven days after it expires.

-   Notification:

Alibaba Cloud reminds you to renew the expired instance. The instance is valid within seven days after it expires. |
|Seven days after expiration|-   Impact on traffic forwarding:

If you do not renew the subscription of an Anti-DDoS Pro instance within seven days after the instance expires, the instance stops forwarding traffic. After you renew the expired Anti-DDoS Pro instance, the instance becomes available and can continue to forward traffic.

**Note:** If Anti-DDoS Pro stops forwarding traffic, your services may be interrupted. We recommend that you read the notifications of instance expiration and renew the subscription of instances at the earliest opportunity. Alternatively, you can enable auto-renewal.

![Notification of instance expiration](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9830937951/p76372.png)

-   Impact on instance configurations:

Alibaba Cloud reclaims instance resources on a regular basis. If you do not renew the subscription of an Anti-DDoS Pro instance that has been expired for more than seven days, the instance and the resources that are configured for the instance are released.

-   Notification:

Seven days after the expiration date, Alibaba Cloud notifies you that the expired instance has stopped forwarding traffic. |

## Refunding

The subscription of an Anti-DDoS Pro instance cannot be canceled before the expiration date. The subscription fees cannot be refunded after you purchase the instance. After an Anti-DDoS Pro instance is created, the fees you paid cannot be refunded.

## References

-   [Purchase an Anti-DDoS Pro instance](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Purchase mitigation plans for Anti-DDoS Pro and Anti-DDoS Premium.md)
-   [Upgrade the specifications of an Anti-DDoS Pro or Anti-DDoS Premium instance](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Resource management/Upgrade the specifications of an Anti-DDoS Pro or Anti-DDoS Premium instance.md)

