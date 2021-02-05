# Purchase an Anti-DDoS Origin Enterprise instance

This topic describes how to purchase an Anti-DDoS Origin Enterprise instance.

-   The enterprise real-name verification is completed for your Alibaba Cloud account.

    You can purchase an Anti-DDoS Origin Enterprise instance only after you complete enterprise real-name verification.

-   The cloud assets that you want to protect are public IP addresses of Elastic Compute Service \(ECS\) instances, public IP addresses of Server Load Balancer \(SLB\) instances, elastic IP addresses \(EIPs\), or IP addresses of Web Application Firewall \(WAF\) instances.

Anti-DDoS Origin is offered in two editions: Anti-DDoS Origin Basic and Anti-DDoS Origin Enterprise.

-   Anti-DDoS Origin Basic is activated by default. Anti-DDoS Origin Basic provides a basic protection capacity of up to 5 Gbit/s against DDoS attacks free of charge for public IP addresses of Alibaba Cloud resources.
-   Anti-DDoS Origin Enterprise must be purchased. Anti-DDoS Origin Enterprise protects public IP addresses of Alibaba Cloud resources, including ECS instances, SLB instances, EIPs, and WAF instances. Anti-DDoS Origin Enterprise provides shared and unlimited protection capacities. You do not need to change your service IP address. Unlimited protection defends against DDoS attacks based on the total network capacity of Alibaba Cloud. The unlimited protection capacity increases with the increase of the overall network capacity of Alibaba Cloud. You do not need to pay extra fees.

    For more information about the billing methods of Anti-DDoS Origin, see [Billing methods of Anti-DDoS Origin](/intl.en-US/Pricing/Billing methods of Anti-DDoS Origin.md).


1.  Access the [Anti-DDoS Origin page](https://common-buy-intl.alibabacloud.com/?commodityCode=ddos_ddosbgp_public_intl) by using your Alibaba Cloud account.

2.  On the **Anti-DDoS Origin** page, set **Product Type** to **Anti-DDoS Origin** and configure the following parameters.

    |Parameter|Description|
    |---------|-----------|
    |**Mitigation Plan**|The mitigation plan of the Anti-DDoS Origin instance. Default value: **Enterprise**. You cannot change the value of this parameter.|
    |**Mitigation Times**|Default value: **Unlimited**. You cannot change the value of this parameter.|
    |**IP Version**|The version of the IP protocol. Valid values: **IPV4** and **IPV6**.|
    |**Region**|The region where the Anti-DDoS Origin instance resides. **Note:**

    -   The Anti-DDoS Origin instance must reside in the same region as the assets that you want to protect.
    -   Anti-DDoS Origin Enterprise instances are available only in mainland China. If you want to purchase an Anti-DDoS Origin Enterprise instance outside mainland China, submit a [ticket](https://workorder-intl.console.aliyun.com/?#/ticket/add/?productId=80) or contact sales personnel. |
    |**Business Scale**|The average network bandwidth of the business that you want to protect.For more information about how to estimate the business scale, see [Instance specifications of Anti-DDoS Origin Enterprise](/intl.en-US/Pricing/Billing methods of Anti-DDoS Origin.mdsection_y6r_x7v_t68). |
    |**IP Addresses**|The total number of IP addresses that you want to protect. Valid values: **100** to **255**. Default value: **100**.|
    |**Mitigation Analysis \(Beta\)**|The Mitigation Analysis feature is in public preview. This feature provides log analysis and reports of protected traffic free of charge. Valid values: **On** and **Off**.**Note:** After you enable this feature, Mitigation Analysis \(Beta\) appears in the left-side navigation pane of the Anti-DDoS Origin console. |
    |**Resource Group**|A resource group is a group of resources that belong to an Alibaba Cloud account. You can manage members, permissions, and resources in a resource group. You can select an existing resource group or create one.For more information, see [Create a resource group](). |
    |**Quantity**|The number of the Anti-DDoS Origin instances that you want to purchase.**Note:** We recommend that you determine the number of instances that you want to purchase based on the number of IP addresses that you want to protect in the current region. For example, if each instance can provide protection for 200 IP addresses and you want to protect 400 IP addresses, you can purchase two instances. |
    |**Duration**|The validity period of the Anti-DDoS Origin instance. You can select **Auto-renewal** based on your business requirements.|

3.  Click **Buy Now**.

4.  Confirm the order and complete the payment.


After you purchase an Anti-DDoS Origin Enterprise instance, you can view the instance on the Manage Instances page in the [Anti-DDoS Origin console](https://yundun.console.aliyun.com/?p=ddosbgp). You can add specific IP addresses that you want to protect to the Anti-DDoS Origin Enterprise instance. For more information, see [Add a cloud service to Anti-DDoS Origin Enterprise for protection](/intl.en-US/Anti-DDoS Origin User Guide/Instances/Add a cloud service to Anti-DDoS Origin Enterprise for protection.md).

