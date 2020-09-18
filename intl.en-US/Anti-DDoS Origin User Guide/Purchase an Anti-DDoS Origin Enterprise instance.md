# Purchase an Anti-DDoS Origin Enterprise instance

This topic describes how to purchase an Anti-DDoS Origin Enterprise instance.

Anti-DDoS Origin Enterprise instances are available only after you complete enterprise real-name verification. Before you purchase an Anti-DDoS Origin Enterprise instance, you must submit an application form on the [Application for Anti-DDoS Origin](https://page-intl.aliyun.com/form/act1373289212/index.htm) page.

![Apply for an Anti-DDoS Origin Enterprise instance](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/5256430061/p142409.png)

Anti-DDoS Origin consists of Anti-DDoS Origin Basic and Anti-DDoS Origin Enterprise.

-   Anti-DDoS Origin Basic provides basic protection against DDoS attacks for the public IP addresses of Alibaba Cloud resources free of charge. Anti-DDoS Origin Basic provides protection capacity of no more than 5 Gbit/s.
-   After you purchase an Anti-DDoS Origin Enterprise instance, the instance protects the public IP addresses of Alibaba Cloud resources. These resources include Elastic Compute Service \(ECS\) instances, Server Load Balancer \(SLB\) instances, elastic IP addresses \(EIPs\), and Web Application Firewall \(WAF\) instances. Anti-DDoS Origin Enterprise provides shared and unlimited protection capacity. This eliminates the need to change IP addresses of the resources that you want to protect. Unlimited protection provides defense against DDoS attacks. The unlimited protection capacity is based on the total number of resources that reside in an anti-DDoS cluster. The unlimited protection capacity strengthens with the increase of the overall network capacity of Alibaba Cloud. The improved protection capacity is free of charge.

    For more information about the billing methods of Anti-DDoS Origin, see [Billing methods of Anti-DDoS Origin](/intl.en-US/Pricing/Billing methods of Anti-DDoS Origin.md).


1.  Visit the product homepage of [Anti-DDoS](https://www.alibabacloud.com/product/ddos-pro) and log on to your Alibaba Cloud account.

2.  Click **Buy Now**.

3.  Set **Product Type** to **Anti-DDoS Origin**.

4.  On the **Anti-DDoS Origin** buy page, configure the parameters for the **Enterprise** instance.

    |Parameter|Description|
    |---------|-----------|
    |**Mitigation Plan**|Select **Enterprise**.|
    |**IP Version**|The IP version supported by Anti-DDoS Origin instances. Valid values: **IPV4** and **IPV6**.|
    |**Region**|The region where the Anti-DDoS Origin instance resides. **Note:**

    -   The Anti-DDoS Origin instance must reside in the same region as the assets that you want to protect. The assets are cloud resources such as ECS instances, SLB instances, WAF instances, and EIPs.
    -   Anti-DDoS Origin Enterprise instances are available only in mainland China. If you want to purchase an Anti-DDoS Origin Enterprise instance outside mainland China, you must [submit a ticket](https://workorder-intl.console.aliyun.com/?#/ticket/add/?productId=80) or contact sales personnel. |
    |**Clean Bandwidth**|The average throughput of the business that you want to protect. Unit: bit/s. Valid values: 100 Mbps, 300 Mbps, 500 Mbps, 800 Mbps, 1 Gbps, 1.5 Gbps, 2 Gbps, 2.5 Gbps, and 3 Gbps. For more information about how to evaluate a clean bandwidth, see [Anti-DDoS Origin Enterprise instance specifications](/intl.en-US/Pricing/Billing methods of Anti-DDoS Origin.mdsection_y6r_x7v_t68). |
    |**IP Addresses**|The total number of the IP addresses that you want to protect. Valid values: **100** to **255**. The default value is **100**.|
    |**Quantity**|The number of the Anti-DDoS Origin instances that you want to purchase.**Note:** We recommend that you calculate the number of the instances that you want to purchase based on the number of the IP addresses that you want to protect in the current region. For example, if each instance provides protection for 200 IP addresses, and 400 IP addresses require protection, you can purchase two instances. |
    |**Subscription**|The validity period of the Anti-DDoS Origin instances that you want to purchase. You can select **Auto-renewal** as required.|

5.  Click **Buy Now**.

6.  Complete the payment.


After you purchase an Anti-DDoS Origin Enterprise instance, you can view the purchased instance on the [Anti-DDoS Origin](https://yundun.console.aliyun.com/?p=ddosbgp) Instances page.

[Add a protection target](/intl.en-US/Anti-DDoS Origin User Guide/Instances/Add a protection target.md).

