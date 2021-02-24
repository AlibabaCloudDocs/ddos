# FAQ about the billing of burstable protection

This topic provides answers to some commonly asked questions about the billing of burstable protection provided by Anti-DDoS Pro.

-   [If no attacks are detected, are burstable protection fees charged?](#section_b4l_uo0_8gz)
-   [If I purchase an Anti-DDoS instance with a basic protection bandwidth of 20 Gbit/s and a burstable protection bandwidth of 50 Gbit/s, what is the maximum mitigation capacity?](#section_e1g_n3h_ttq)
-   [What happens if the size of DDoS attacks exceeds the burstable protection bandwidth?](#section_reb_bc3_r9v)
-   [If the basic protection bandwidth is 30 Gbit/s, the burstable protection bandwidth is 50 Gbit/s, and the size of DDoS attacks is 45 Gbit/s, how is burstable protection charged?](#section_uew_cwl_895)
-   [Can I change the burstable protection bandwidth from 100 Gbit/s to 200 Gbit/s?](#section_tbb_9xh_h9r)
-   [If the basic protection bandwidth of 30 Gbit/s provided by the Anti-DDoS Pro instance cannot meet my requirements, can I increase the protection bandwidth anytime?](#section_ok3_fp4_0o5)
-   [If an IP address is attacked multiple times in a day, how is the mitigation fee calculated?](#section_f54_1kp_jy3)
-   [How do I prevent an Anti-DDoS Pro instance from providing burstable protection?](#section_nvf_ylt_5rd)

## If no attacks are detected, are burstable protection fees charged?

No, if no attacks are detected, no burstable protection fees are charged. Only subscription fees for basic protection are charged.

## If I purchase an Anti-DDoS instance with a basic protection bandwidth of 20 Gbit/s and a burstable protection bandwidth of 50 Gbit/s, what is the maximum mitigation capacity?

The maximum mitigation capacity is determined by the burstable protection bandwidth, which is 50 Gbit/s in this example. If you purchase a burstable protection bandwidth of 20 Gbit/s that equals the basic protection bandwidth, the maximum mitigation capacity is 20 Gbit/s. In this case, your Anti-DDoS instance does not provide burstable protection.

## What happens if the size of DDoS attacks exceeds the burstable protection bandwidth?

If the size of DDoS attacks exceeds the burstable protection bandwidth, the traffic that is destined for the protected IP addresses is forwarded by using null routes.

## If the basic protection bandwidth is 30 Gbit/s, the burstable protection bandwidth is 50 Gbit/s, and the size of DDoS attacks is 45 Gbit/s, how is burstable protection charged?

Burstable protection is charged based on the difference between the peak traffic throughout of DDoS attacks and the basic protection bandwidth. In this example, you are charged only for the burstable protection bandwidth of 15 Gbit/s.

For more information about the pricing of burstable protection, visit the [Anti-DDoS Pricing page](https://www.alibabacloud.com/product/ddos/pricing?#product_tab1-3). In this example, you are charged based on the burstable protection bandwidth of 15 Gbit/s at the price of USD 330/day.

![Pricing-intl](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9312488951/p130907.png)

## Can I change the burstable protection bandwidth from 100 Gbit/s to 200 Gbit/s?

Yes, you can change the burstable protection bandwidth from 100 Gbit/s to 200 Gbit/s.

You can manage **burstable protection** for an Anti-DDoS Pro instance on the **Instances** page in the [Anti-DDoS Pro console](https://yundun.console.aliyun.com/?p=ddoscoo). **Mainland China** is selected by default.

![Manage protection bandwidth](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9312488951/p130908.png)

**Note:** If burstable protection on the day when you change the burstable protection bandwidth is already charged, the system starts to charge burstable protection based on the newly selected bandwidth the next day.

## If the basic protection bandwidth of 30 Gbit/s provided by the Anti-DDoS Pro instance cannot meet my requirements, can I increase the protection bandwidth anytime?

Yes, you can increase the basic protection bandwidth or burstable protection bandwidth.

-   Increase the basic protection bandwidth

    You can manage **basic protection** for an Anti-DDoS Pro instance on the **Instances** page in the [Anti-DDoS Pro console](https://yundun.console.aliyun.com/?p=ddoscoo) and complete the payment. **Mainland China** is selected by default. For more information, see [Upgrade the specifications of an Anti-DDoS Pro or Anti-DDoS Premium instance](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Resource management/Upgrade the specifications of an Anti-DDoS Pro or Anti-DDoS Premium instance.md).

    ![Upgrade the instance](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9312488951/p130909.png)

-   Increase the burstable protection bandwidth

    You can manage **burstable protection** for an Anti-DDoS Pro instance on the **Instances** page in the [Anti-DDoS Pro console](https://yundun.console.aliyun.com/?p=ddoscoo). **Mainland China** is selected by default. Burstable protection is billed on a pay-as-you-go basis and charged based on the difference between the peak traffic throughout of DDoS attacks and the basic protection bandwidth. For more information, see [Burstable protection \(pay-as-you-go on a daily basis\)](/intl.en-US/Pricing/Anti-DDoS Pro billing methods.md).

    ![Manage protection bandwidth](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9312488951/p130908.png)


## If an IP address is attacked multiple times in a day, how is the mitigation fee calculated?

Burstable protection is charged only once based on the peak traffic throughout of DDoS attacks on the same day \(from 00:00 to 24:00\). For example, if three DDoS attacks are launched to a protected IP address, and the peak traffic throughout of the three DDoS attacks are 50 Gbit/s, 100 Gbit/s, and 200 Gbit/s, burstable protection is charged based on the highest peak traffic throughput \(200 Gbit/s\).

## How do I prevent an Anti-DDoS Pro instance from providing burstable protection?

You can set the burstable protection bandwidth and basic protection bandwidth to the same value. If DDoS attacks exhaust the basic protection bandwidth, no burstable protection is provided to mitigate the attacks and no bills are generated.

You can manage **burstable protection** for an Anti-DDoS Pro instance on the **Instances** page in the [Anti-DDoS Pro console](https://yundun.console.aliyun.com/?p=ddoscoo). **Mainland China** is selected by default.

![Manage protection bandwidth](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9312488951/p130908.png)

