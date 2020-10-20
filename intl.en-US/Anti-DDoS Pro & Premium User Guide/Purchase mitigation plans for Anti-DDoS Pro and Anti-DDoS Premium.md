# Purchase mitigation plans for Anti-DDoS Pro and Anti-DDoS Premium

This topic describes how to purchase mitigation plans for different types of Anti-DDoS instances. You can purchase professional plans for Anti-DDoS Pro instances. You can also purchase insurance plans, unlimited plans, Mainland China Acceleration \(MCA\) plans, or Secured Mainland China Acceleration \(Sec-MCA\) plans for Anti-DDoS Premium instances.

## Select an instance type

You can purchase an Anti-DDoS instance based on the regions where your workloads are deployed and where your users are located.

-   If your workloads are deployed **in mainland China**, you must purchase a professional plan for an Anti-DDoS Pro instance.

    **Note:** You cannot use Anti-DDoS Pro instances to protect domain names that do not have Internet Content Provider \(ICP\) numbers. Before you use an Anti-DDoS Pro instance to protect your website, apply for an ICP number for the domain name of your website.

-   If your workloads are deployed **outside mainland China** and and your services are provided to users who are located **outside mainland China**, you must purchase an insurance plan or unlimited plan for an Anti-DDoS Premium instances.
-   If your workloads are deployed **outside mainland China** and you purchase an Anti-DDoS Premium instance that uses an insurance or unlimited plan, users **in mainland China** experience a high network latency. The average network latency is about 300 milliseconds. We recommend that you consider the following solution:
    -   If you only need to ensure stable and fast access for users in mainland China, purchase a Sec-MCA plan for an Anti-DDoS Premium instance. This solution is not applicable to China Mobile users in mainland China.

        **Note:** Sec-MCA provides DDoS scrubbing capabilities and access acceleration. Therefore, you must purchase only a Sec-MCA plan for the Anti-DDoS Premium instance. For more information, see [Configure Anti-DDoS Premium Sec-MCA](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Configure Anti-DDoS Premium Sec-MCA.md).

    -   If the preceding solution cannot meet your requirements, we recommend that you purchase an insurance or unlimited plan and an MCA plan for the Anti-DDoS Premium instance.

        **Note:** You must use Sec-Traffic Manager to configure **network acceleration** rules for the Anti-DDoS Premium instance. If no DDoS attacks are detected, MCA accelerates requests that are destined for protected services. If DDoS attacks are detected, the Anti-DDoS Premium instance that uses an insurance plan or unlimited plan protects the services against DDoS attacks. For more information, see [Overview](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Sec-Traffic Manager/Overview.md).


## Purchase an Anti-DDoS Pro instance

1.  Go to the[Anti-DDoS Pro buy page](https://common-buy-intl.aliyun.com/?commodityCode=ddoscoo_intl#/buy) and log on with your Alibaba Cloud account.

2.  Configure an Anti-DDoS Pro instance that meets your service requirements.

    ![Buy page](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/8632097951/p69110.png)

    |Parameter|Description|
    |---------|-----------|
    |**Product Type**|**Anti-DDoS Pro \(Mainland China\)** is selected by default.|
    |**Mitigation Plan**|**Profession** is selected by default.|
    |**Basic Protection**|Specify the basic protection bandwidth for the instance. Basic protection is billed on a subscription basis. It takes effect only after you complete the payment. The total instance cost increases with the basic protection bandwidth that you select. |
    |**Burstable Protection**|Specify the burstable protection bandwidth for the instance. Burstable protection is billed on a pay-as-you-go basis. Burstable protection bandwidth determines the maximum mitigation capacity provided by the instance.

    -   If you set the **burstable protection bandwidth** and **basic protection bandwidth** to the same value, the maximum mitigation capacity equals the **basic protection** bandwidth. When DDoS attacks exhaust the basic protection bandwidth, no additional bandwidth resources are provided to mitigate the attacks and therefore no bill is generated.
    -   If you set the **burstable protection bandwidth** to a value greater than **basic protection bandwidth**, Anti-DDoS Pro can mitigate DDoS attacks between the **basic protection bandwidth** and **burstable protection bandwidth** in size. The amount of bandwidth that exceeds the **basic protection bandwidth** is billed based on the daily peak value minus the basic protection bandwidth. |
    |**Clean Bandwidth**|Select the clean bandwidth for normal workloads protected by the instance. Minimum value: 100 Mbit/s. Set **Clean Bandwidth** to a value that is greater than the peak value of the inbound or outbound traffic of your workloads protected by the instance, whichever is higher. For more information, see [Select the clean bandwidth](#section_5z0_b0o_n40).

**Warning:** When the volume of the traffic received or sent by your instance exceeds the clean bandwidth, packet loss and service interruptions may occur. We recommend that you increase the clean bandwidth to resolve these issues. |
    |**Function Plan**|Select a function plan for the instance. Valid values:     -   **Standard Function**
    -   **Enhanced Function**
For more information, see [Function plan](/intl.en-US/Pricing/Function plan.md). |
    |**Domains**|Specify the number of domain names that the instance can protect. Values must be multiples of 10. Minimum value: 50, which is the default value. Maximum value: 200. The domains specified for the instance can be subdomains and wildcard domains. The number of unique top-level domains that corresponds to the subdomains and wildcard domains must not exceed "**Domains**/10".

For example, the default value of the **Domains** parameter is 50. This means that the Anti-DDoS Pro instance can protect up to five different top-level domains. The sum of subdomains and wildcard domains cannot exceed 50.

If top-level domains example1.com and example2.com are specified, subdomains www.example1.com and abc.example2.com, and wildcard domain \*.example1.com are allowed.

If more than 50 domain names or 5 top-level domain names require protection, you can increase the value of **Domains**. |
    |**Clean QPS**|Select the maximum number of HTTP and HTTPS requests that the instance can concurrently process per second when the instance is not under attack. Minimum value: 3000, which is the default value.|
    |**Ports**|Specify the number of TCP and UDP ports that the instance can protect. Minimum value: 50, which is the default value.|
    |**Quantity**|Select the number of instances with the current specifications that you want to purchase.|
    |**Plan**|Select a subscription duration for the instance. If you select **Auto renewal**, the instance is automatically renewed before the subscription expires.

    -   Monthly subscription: The instance is automatically renewed for one month.
    -   Annual subscription: The instance is automatically renewed for one year. |

3.  Confirm the configurations and click **Buy Now**.

4.  Confirm your order and complete the payment.


## Purchase an insurance plan or unlimited plan for an Anti-DDoS Premium instance

1.  Go to the[Anti-DDoS Premium buy page](https://common-buy-intl.aliyun.com/?commodityCode=ddosDip_intl#/buy) and log on with your Alibaba Cloud account.

2.  Configure an Anti-DDoS Premium instance that meets your service requirements.

    ![Anti-DDoS Premium buy page](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/9632097951/p128732.png)

    |Parameter|Description|
    |---------|-----------|
    |**Product Type**|**Anti-DDoS Premium** is selected by default.|
    |**Mitigation Plan**|Select **Insurance** or **Unlimited**. For information, see [Billing methods of Insurance Plan and Unlimited Plan](/intl.en-US/Pricing/Anti-DDoS premium billing methods/Billing methods of Insurance Plan and Unlimited Plan.md).

**Note:**

    -   For more information about how to purchase an MCA plan, see [Purchase an MCA plan for an Anti-DDoS Premium instance](#section_5nv_n64_68g).
    -   For more information about how to purchase an Sec-MCA plan, see [Purchase a Sec-MCA plan for an Anti-DDoS Premium instance](#section_r7p_51r_r7f). |
    |**Clean Bandwidth**|Select the clean bandwidth for normal workloads protected by the instance. Minimum value: 100 Mbit/s. Set **Clean Bandwidth** to a value that is greater than the peak value of the inbound or outbound traffic of your workloads protected by the instance, whichever is higher. For more information, see [Select the clean bandwidth](#section_5z0_b0o_n40).

**Warning:** When the volume of the traffic received or sent by your instance exceeds the clean bandwidth, packet loss and service interruptions may occur. We recommend that you increase the clean bandwidth to resolve these issues. |
    |**Function Plan**|Select a function plan for the instance. Valid values:     -   **Standard Function**
    -   **Enhanced Function**
For more information, see [Function plan](/intl.en-US/Pricing/Function plan.md). |
    |**Domains**|Specify the number of domain names that the instance can protect. Values must be multiples of 10. Minimum value: 10, which is the default value. Maximum value: 200. The domains specified for the instance can be subdomains and wildcard domains. The number of unique top-level domains that corresponds to the subdomains and wildcard domains must not exceed “**Domains**/10".

For example, the default value of the **Domains** parameter is 10. This means that the Anti-DDoS Pro instance can protect only one top-level domain. You can specify no more than 10 domains \(subdomains and wildcard domains\) for the root domain. The sum of subdomains and wildcard domains cannot exceed 10.

If top-level domain example1.com is specified, subdomain www.example1.com and wildcard domain \*.example1.com are allowed.

If more than 10 domain names or 1 top-level domain name require protection, you can increase the value of **Domains**. |
    |**Clean QPS**|Select the maximum number of HTTP and HTTPS requests that the instance can concurrently process per second when the instance is not under attack. Minimum value:     -   Insurance plan: 500, which is the default value.
    -   Unlimited plan: 1000, which is the default value. |
    |**Ports**|Specify the number of TCP and UDP ports that the instance can protect. Minimum value: 5, which is the default value.|
    |**Quantity**|Select the number of instances with the current specifications that you want to purchase.|
    |**Subscription**|Select a subscription duration for the instance. If you select **Auto renewal**, the instance is automatically renewed before the subscription expires.

    -   Monthly subscription: The instance is automatically renewed for one month.
    -   Annual subscription: The instance is automatically renewed for one year. |

3.  Confirm the configurations and click **Buy Now**.

4.  Confirm your order and complete the payment.


## Purchase an MCA plan for an Anti-DDoS Premium instance

1.  Go to the[Anti-DDoS Premium buy page](https://common-buy-intl.aliyun.com/?commodityCode=ddosDip_intl#/buy) and log on with your Alibaba Cloud account.

2.  Configure an Anti-DDoS Premium instance that meets your service requirements.

    ![Buy page of an MCA plan for an Anti-DDoS Premium instance](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/9632097951/p130853.png)

    |Parameter|Description|
    |---------|-----------|
    |**Product Type**|**Anti-DDoS Premium** is selected by default.|
    |**Mitigation Plan**|Select **MCA**.|
    |**Clean Bandwidth**|Select the clean bandwidth for normal workloads protected by the instance. Minimum value: 10 Mbit/s. Set **Clean Bandwidth** to a value that is greater than the peak value of the inbound or outbound traffic of your workloads protected by the instance, whichever is higher. For more information, see [Select the clean bandwidth](#section_5z0_b0o_n40).

**Warning:** When the volume of the traffic received or sent by your instance exceeds the clean bandwidth, packet loss and service interruptions may occur. We recommend that you increase the clean bandwidth to resolve these issues. |
    |**Quantity**|Select the number of instances with the current specifications that you want to purchase.|
    |**Subscription**|Select a subscription duration for the instance. If you select **Auto renewal**, the instance is automatically renewed before the subscription expires.

    -   Monthly subscription: The instance is automatically renewed for one month.
    -   Annual subscription: The instance is automatically renewed for one year. |

3.  Confirm the configurations and click **Buy Now**.

4.  Confirm your order and complete the payment.


## Purchase a Sec-MCA plan for an Anti-DDoS Premium instance

1.  Go to the[Anti-DDoS Premium buy page](https://common-buy-intl.aliyun.com/?commodityCode=ddosDip_intl#/buy) and log on with your Alibaba Cloud account.

2.  Configure the specifications of the Anti-DDoS Premium MCA plan based on your service requirements.

    ![Buy page of a Sec-MCA plan for an Anti-DDoS Premium instance](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/9632097951/p130854.png)

    |Parameter|Description|
    |---------|-----------|
    |**Product Type**|**Anti-DDoS Premium** is selected by default.|
    |**Mitigation Plan**|Select **Sec-MCA**.|
    |**Clean Bandwidth**|Select the clean bandwidth for normal workloads protected by the instance. Minimum value: 10 Mbit/s. Set **Clean Bandwidth** to a value that is greater than the peak value of the inbound or outbound traffic of your workloads protected by the instance, whichever is higher. For more information, see [Select the clean bandwidth](#section_5z0_b0o_n40).

**Warning:** When the volume of the traffic received or sent by your instance exceeds the clean bandwidth, packet loss and service interruptions may occur. We recommend that you increase the clean bandwidth to resolve these issues. |
    |**Function Plan**|Select a function plan for the instance. Valid values:     -   **Standard Function**
    -   **Enhanced Function**
For more information, see [Function plan](/intl.en-US/Pricing/Function plan.md). |
    |**Domains**|Specify the number of domain names that the instance can protect. Values must be multiples of 10. Minimum value: 10, which is the default value. Maximum value: 200. The domains specified for the instance can be subdomains and wildcard domains. The number of unique top-level domains that corresponds to the subdomains and wildcard domains must not exceed “**Domains**/10".

For example, the default value of the **Domains** parameter is 10. This means that the Anti-DDoS Pro instance can protect only one top-level domain. You can specify no more than 10 domains \(subdomains and wildcard domains\) for the root domain. The sum of subdomains and wildcard domains cannot exceed 10.

If top-level domain example1.com is specified, subdomain www.example1.com and wildcard domain \*.example1.com are allowed.

If more than 10 domain names or 1 top-level domain name require protection, you can increase the value of **Domains**. |
    |**Clean QPS**|Select the maximum number of HTTP and HTTPS requests that the instance can concurrently process per second when the instance is not under attack. Minimum value:     -   Insurance plan: 500, which is the default value.
    -   Unlimited plan: 1000, which is the default value. |
    |**Ports**|Specify the number of TCP and UDP ports that the instance can protect. Minimum value: 5, which is the default value.|
    |**Quantity**|Select the number of instances with the current specifications that you want to purchase.|
    |**Subscription**|Select a subscription duration for the instance. If you select **Auto renewal**, the instance is automatically renewed before the subscription expires.

    -   Monthly subscription: The instance is automatically renewed for one month.
    -   Annual subscription: The instance is automatically renewed for one year. |

3.  Confirm the configurations and click **Buy Now**.

4.  Confirm your order and complete the payment.


## Select the clean bandwidth

You can select an appropriate clean bandwidth value based on the daily inbound and outbound traffic peaks of your workloads that are protected or to be protected by the instance. Make sure that the clean bandwidth of the instance is greater than the peak bandwidth of the inbound or outbound traffic, whichever is higher.

**Note:** In most cases, the peak bandwidth of the outbound traffic is higher than that of the inbound traffic.

You can estimate the actual bandwidth usage based on the traffic statistics collected in the Elastic Compute Service \(ECS\) console or by using other monitoring tools on your origin server. The traffic described here refers to the normal traffic generated by your workloads.

For example, you use Anti-DDoS Pro or Anti-DDoS Premium to protect your website. If no attacks are launched against your website, Anti-DDoS Pro or Anti-DDoS Premium forwards user traffic to the origin server. However, if your website is under attack, Anti-DDoS Pro or Anti-DDoS Premium blocks malicious traffic and forwards only user traffic to the origin server. Therefore, the ECS console displays only statistics about inbound and outbound user traffic that flows through the origin server. If your workloads are deployed on multiple origin servers, you must calculate the sum of the traffic volumes on all origin servers.

![Normal traffic](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/9632097951/p38045.png)

For example, you want to connect three websites to an Anti-DDoS Pro or Anti-DDoS Premium instance. The peak of the outbound user traffic on each website is 50 Mbit/s or lower. The total bandwidth required by the three websites is 150 Mbit/s or lower. In this case, make sure that the clean bandwidth of the purchased instance is higher than 150 Mbit/s.

## References

-   [Anti-DDoS Pro billing methods](/intl.en-US/Pricing/Anti-DDoS Pro billing methods.md)
-   [Billing methods of Insurance Plan and Unlimited Plan](/intl.en-US/Pricing/Anti-DDoS premium billing methods/Billing methods of Insurance Plan and Unlimited Plan.md)
-   [Mainland China Acceleration billing methods](/intl.en-US/Pricing/Anti-DDoS premium billing methods/Mainland China Acceleration billing methods.md)
-   [Sec-MCA billing methods](/intl.en-US/Pricing/Anti-DDoS premium billing methods/Sec-MCA billing methods.md)

