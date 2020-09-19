# Alibaba Cloud black hole policies

This topic explains the black hole policy of Alibaba Cloud Security.

## What is a black hole?

When the attack traffic to a server exceeds the black hole threshold configured for the server room, the server is thrown into a black hole to block external network access to the server. Once a server is thrown into a black hole, it become unavailable during the black hole duration. After that, the system determines that the attack traffic stops, and the black hole status is automatically lifted.

The black hole is a service that Alibaba Cloud purchases from the operator who imposes strict restrictions on the time and frequency to lift the black hole. The black hole state cannot be manually deactivated. Thus, you must patiently wait for the system to auto unban the server.

## Why enact the black hole policy? Why can not help users resist the attack for an unlimited period of time?

DDoS attacks severely impair not only victims, but also the entire cloud network. Besides, DDoS defense costs a lot, the biggest among which is the bandwidth cost.

Alibaba Cloud purchases bandwidth from ISPs. ISPs will not clean out DDoS attack traffic when calculating the bandwidth cost, but will directly charge Alibaba Cloud on the consumed bandwidth.

Alibaba Cloud Security potentially defends against DDoS attacks for Alibaba Cloud users free of charge at a limited cost, but when the attacking traffic exceeds the threshold, Alibaba Cloud will block the traffic to the IP address under attack.

如果您的IP遭受的攻击流量超出阈值触发黑洞时，您可以通过购买[DDoS防护包](/intl.en-US/Product Introduction on Alibaba DDoS Protection/Anti-DDoS Origin/What is Anti-DDoS Origin.md)将防御能力提升至该IP所属地域的最高防御水平，同时您将获得立即解除黑洞状态的机会。

## How to view the black hole threshold and duration?

See [Anti-DDoS Basic black hole threshold](/intl.en-US/Anti-DDoS Origin User Guide/Black hole policies/View black hole triggering thresholds in Anit-DDoS Origin Basic.md) to check the current DDoS mitigation capacity of your ECS, SLB, or EIP instances.

See [View the black hole duration](/intl.en-US/Anti-DDoS Origin User Guide/Black hole policies/View the duration of a black hole.md) to check how long it takes before your IP becomes accessible during a black hole event.

## How to improve the black hole threshold?

Join up our Security Credibility plan for free to get an extra DDoS mitigation capacity based on your security credibility score. By improving your credibility score, you can get more extra DDoS mitigation capacity.

## What to do if the black hole threshold is not enough?

参考以下方案，轻松解决DDoS流量攻击困扰，保障服务器的正常运行。

-   购买[DDoS防护包](https://common-buy.aliyun.com/?commodityCode=ddosbgp#/buy)，获取最高可达100G防御能力且无需修改业务IP。
-   购买[DDoS高防IP服务](https://yundun.console.aliyun.com/buy?id=ddos#/postpay)，获取最高可达T级别防御能力，需将流量切换至高防IP。

You can purchase the [Anti-DDoS Pro](https://common-buy-intl.aliyun.com/?spm=a3c0i.8100444.364928.1.5x29Xw&commodityCode=ddosBag_intl#/buy) service to easily prevent DDoS attacks and safeguard normal operation of servers. Anti-DDoS Pro is designed to help users defend against DDoS attacks, with clear commitment on the protection capability and defense performance.

## What is the difference between the Security Credibility plan and Anti-DDoS Pro?

The Security Credibility plan helps users with good credit records to increase the protection capability against the first attack. The black hole threshold is adjusted as the credibility score changes, with no fixed protection capability warranted.

Anti-DDoS Pro service is designed to help users defend against DDoS attacks, with clear commitment on the protection capability and defense performance.

## Black hole triggering thresholds for various regions

The default black hole triggering thresholds offered by basic protection feature of Anti-DDoS Basic in various regions are as follows \(Unit: bps\):

**Note:** The triggering thresholds apply to Alibaba Cloud ECS, Server Load Balancer, VPC, and other products.

|Region|1-core CPU classic-network ECS|2-core CPU classic-network ECS|4-core \(or later\) CPU classic-network ECS|Server Load Balancer and VPC|
|------|------------------------------|------------------------------|-------------------------------------------|----------------------------|
|China East 1|500 M|1G|5 G|5 G|
|China East 2|500 M|1G|2 G|2 G|
|China North 1|500 M|1G|5 G|5 G|
|China North 2|500 M|1G|2 G|2 G|
|China North 3|500 M|1G|2 G|2 G|
|China North 5|500 M|1G|2 G|2 G|
|China South 1|500 M|1G|2 G|2 G|
|Hong Kong|500 M|500 M|500 M|500 M|
|US West 1|500 M|1G|2 G|2 G|
|US East 1|500 M|500 M|500 M|500 M|
|Tokyo|500 M|500 M|500 M|500 M|
|Singapore|500 M|500 M|500 M|500 M|
|Sydney|500 M|500 M|500 M|500 M|
|Kuala Lumpur|500 M|500 M|500 M|500 M|
|Mumbai|500 M|1G|1G|1G|
|Frankfurt|500 M|500 M|500 M|500 M|
|Dubai|500 M|500 M|500 M|500 M|

## Black hole duration

The default black hole duration is 2.5 hours and the server cannot be unbanned during this period. The actual black hole duration depends on the attack situation and may range from 30 minutes to 24 hours. The duration of the black hole is mainly influenced by the following factors:

-   Whether the attack persists. The black hole duration keeps extending, if the attack continues. The black hole duration is re-calculated from the time of extension.
-   Whether the attack is frequent. If a user is attacked for the first time, the black hole duration will be automatically shortened. On the contrary, the black hole duration for a user under frequent attacks will be automatically extended as the user is more likely to be attacked again.

    **Note:** For users suffering overly frequent black holes, Alibaba Cloud reserves the right to extend the black hole duration and reduce the black hole threshold. You can go to the console to view the specific black hole threshold and duration.


如果有疑问，请联系[售后技术支持](https://selfservice.console.aliyun.com/ticket/createIndex.htm)。

