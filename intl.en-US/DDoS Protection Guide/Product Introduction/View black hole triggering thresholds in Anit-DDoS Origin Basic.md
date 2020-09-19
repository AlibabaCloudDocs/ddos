# View black hole triggering thresholds in Anit-DDoS Origin Basic

The following table lists the default thresholds at which Anti-DDoS Origin Basic automatically triggers black holes in each region. These thresholds are measured in bit/s.

**Note:**

-   Anti-DDoS Origin Basic automatically trigger black holes for Elastic Compute Service \(ECS\) instances, Server Load Balancer \(SLB\) instances, elastic IP addresses \(EIPs\), and Web Application Firewall \(WAF\) instances. This feature is available for IPv4 networks in all regions and for IPv6 networks only in specific regions. In the following table, a check sign \(√\) in the Support IPv6 column indicates that the automatic black hole triggering feature is supported for IPv6 traffic in the region and the thresholds are applicable to both IPv4 and IPv6 networks. A cross sign \(×\) indicates that the feature is not supported for IPv6 traffic in the region and the thresholds are applicable only to IPv4 networks.
-   In practice, black hole triggering thresholds for ECS instances, SLB instances, and EIPs vary based on the instance type and bandwidth that you purchase. For more information, go to the **Assets** page of the Anti-DDoS console for more details. For more information, see [Assets](/intl.en-US/Anti-DDoS Origin User Guide/Assets.md).
-   In each region, the same threshold to trigger black holes is applied to WAF instances, SLB instances, and EIPs.

|Region|Support IPv4|Support IPv6|ECS instance with one vCPU|ECS instance with two vCPUs|ECS instance with more than four vCPUs|SLB instance, EIP \(includes public IP addresses of NAT gateways\), and WAF instance|
|------|------------|------------|--------------------------|---------------------------|--------------------------------------|------------------------------------------------------------------------------------|
|China \(Hangzhou\)|√|√|500 MB|1 GB|5 GB|5 GB|
|China \(Shanghai\)|√|√|500 MB|1 GB|2 GB|2 GB|
|China \(Qingdao\)|√|×|500 MB|1 GB|5 GB|5 GB|
|China \(Beijing\)|√|√|500 MB|1 GB|2 GB|2 GB|
|China \(Zhangjiakou-Beijing Winter Olympics\)|√|√|500 MB|1 GB|2 GB|2 GB|
|China \(Hohhot\)|√|√|500 MB|1 GB|2 GB|2 GB|
|China \(Shenzhen\)|√|√|500 MB|1 GB|2 GB|2 GB|
|China \(Heyuan\)|√|√|500 MB|1 GB|2 GB|2 GB|
|China \(Chengdu\)|√|×|500 MB|1 GB|2 GB|2 GB|
|China \(Hong Kong\)|√|√|500 MB|500 MB|500 MB|500 MB|
|Singapore \(Singapore\)|√|×|500 MB|500 MB|500 MB|500 MB|
|Australia \(Sydney\)|√|×|500 MB|500 MB|500 MB|500 MB|
|Malaysia \(Kuala Lumpur\)|√|×|500 MB|500 MB|500 MB|500 MB|
|Indonesia \(Jakarta\)|√|×|500 MB|500 MB|500 MB|500 MB|
|Japan \(Tokyo\)|√|×|500 MB|500 MB|500 MB|500 MB|
|Germany \(Frankfurt\)|√|×|500 MB|500 MB|500 MB|500 MB|
|UK \(London\)|√|×|500 MB|500 MB|500 MB|500 MB|
|US \(Silicon Valley\)|√|×|500 MB|1 GB|2 GB|2 GB|
|US \(Virginia\)|√|×|500 MB|500 MB|500 MB|500 MB|
|India \(Mumbai\)|√|×|500 MB|1 GB|1 GB|1 GB|
|UAE \(Dubai\)|√|×|500 MB|500 MB|500 MB|500 MB|

The default black hole duration is 2.5 hours. During this period, blackholing is enabled and cannot be disabled. The actual black hole duration changes based on the type of attack, ranging from 30 minutes to 24 hours. The duration of a black hole changes based on the following factors:

-   The duration of attacks. If attacks continue, the black hole duration is extended. The next black hole duration is set to zero and starts at the time when the last black hole duration is extended.
-   The frequency of attacks. If an asset experiences attacks for the first time, the black hole duration automatically decreases. Otherwise, assets that experience frequent attacks have a high probability to encounter continuous attacks. In such cases, the black hole duration is automatically extended.

**Note:** If an asset triggers black holes too often, Alibaba Cloud reserves the right to extend the black hole duration and decrease the black hole threshold for the asset. The actual black hole triggering threshold and black hole duration are displayed in the Anti-DDoS console.

