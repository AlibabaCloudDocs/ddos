# Blackhole filtering policy of Alibaba Cloud

If a server suffers from a volumetric DDoS attack that exceeds the protection capability of your Anti-DDoS instance, blackhole filtering is triggered to block Internet access to the server. This avoids effects on other users in the Alibaba Cloud network and ensures network availability and stability.

## Duration of blackhole filtering

The default duration of blackhole filtering is 2.5 hours. The actual duration varies from 30 minutes to 24 hours based on the attack status. The duration of blackhole filtering is affected by the following factors:

-   The duration of attacks. If an attack lasts for a long time, blackhole filtering may be triggered again, so its duration is extended.
-   The frequency of attacks. When an asset encounters an attack for the first time, the duration of blackhole filtering is shortened. If the asset is frequently attacked, it may suffer from continuous attacks. In this case, the duration of blackhole filtering is extended.

    **Note:** If an asset triggers blackhole filtering too frequently, Alibaba Cloud may further extend the duration of blackhole filtering and lower the threshold to trigger blackhole filtering for the asset. You can view the actual duration and threshold of blackhole filtering in the console.

-   The volume of attack traffic. If the volume of attack traffic is overwhelmingly large, the duration of blackhole filtering is extended.

For information about the time when blackhole filtering is deactivated, see [View the duration of a blackhole](/intl.en-US/Anti-DDoS Origin User Guide/Black hole policies/View the duration of a black hole.md).

## How do I deactivate blackhole filtering?

Internet service providers \(ISPs\) have strict restrictions on the time and frequency to deactivate blackhole filtering. If Alibaba Cloud detects that the attack traffic that triggered blackhole filtering stops on a server, blackhole filtering is automatically deactivated.

If you want to recover your service before blackhole filtering is automatically deactivated, use the solutions in the following table.

|Anti-DDoS instance|Solution|Description|
|------------------|--------|-----------|
|Anti-DDoS Origin Enterprise|-   Deactivate blackhole filtering in the Anti-DDoS Origin console.

For more information, see [Deactivate a black hole](/intl.en-US/Anti-DDoS Origin User Guide/Black hole policies/Deactivate a black hole.md).

-   Call the [DeleteBlackhole](/intl.en-US/API reference/Anti-DDoS Origin/API reference (2018-07-20)/Protection/DeleteBlackhole.md) operation to deactivate blackhole filtering.


|You can deactivate blackhole filtering up to 100 times per month. If blackhole filtering is triggered again immediately after you deactivate it, we recommend that you increase the protection threshold.|
|Anti-DDoS Pro|-   Deactivate blackhole filtering in the Anti-DDoS Pro console.

For more information, see [Deactivate a black hole](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Protection settings/Protection for infrastructure/Deactivate a black hole.md).

-   Call the [ModifyBlackholeStatus](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Protection for infrastructure/ModifyBlackholeStatus.md) operation to deactivate blackhole filtering.


|You can deactivate blackhole filtering up to five times per day.|
|Anti-DDoS Origin Basic \(You have not purchased Anti-DDoS instances.\)|-   Wait for blackhole filtering to be automatically deactivated.

[View the duration of a black hole](/intl.en-US/Anti-DDoS Origin User Guide/Black hole policies/View the duration of a black hole.md). If you confirm that blackhole filtering will be deactivated soon or within an acceptable time period, you can wait for the automatic deactivation.

-   Change the public IP address of your server or resolve your domain name to an SLB instance. For more information, see [Change the public IP address of an ECS instance](/intl.en-US/Network/Change IPv4 addresses/Change the public IP address of an ECS instance.md).
-   Purchase an Anti-DDoS Pro instance to defend against attacks. For more information, see [What are Anti-DDoS Pro and Anti-DDoS Premium?](/intl.en-US/Product Introduction on Alibaba DDoS Protection/What are Anti-DDoS Pro and Anti-DDoS Premium?.md).

|The duration of blackhole filtering is estimated and may vary based on changes of attack traffic on your server.|

## Why is blackhole filtering triggered? Why cannot Alibaba Cloud defend against volumetric DDoS attacks free of charge?

DDoS attacks not only affect attacked servers, but also affect other users in the Alibaba Cloud network. The attacks may even paralyze the entire cloud network.

Protection against DDoS attacks requires a large number of bandwidth resources. Alibaba Cloud needs to purchase bandwidth resources from ISPs, such as China Telecom, China Unicom, and China Mobile. DDoS attacks bring heavy bandwidth costs to Alibaba Cloud. Alibaba Cloud defends against DDoS attacks for users free of charge within [the threshold of Anti-DDoS Origin Basic](/intl.en-US/DDoS Protection Guide/Product Introduction/View black hole triggering thresholds in Anit-DDoS Origin Basic.md). However, if the attack traffic exceeds the threshold, Alibaba Cloud blocks all traffic to the attacked IP address to avoid extra costs.

## How do I increase the threshold to trigger blackhole filtering?

You can join Security Credibility free of charge. Security Credibility determines the threshold to trigger blackhole filtering based on multiple aspects. If you have a qualified security credit score, you can obtain extra capabilities to defend against DDoS attacks without extra fees.

For more information about how to view the threshold, see [View blackhole triggering thresholds in Anti-DDoS Origin Basic](/intl.en-US/DDoS Protection Guide/Product Introduction/View black hole triggering thresholds in Anit-DDoS Origin Basic.md).

You can also increase the threshold by using one of the following methods:

-   Purchase an [Anti-DDoS Origin](https://common-buy-intl.alibabacloud.com/?commodityCode=ddos_ddosbgp_public_intl) instance to enable [unlimited protection](/intl.en-US/DDoS Protection Guide/Terms.md) without changing your service IP address.
-   Purchase an [Anti-DDoS Pro or Anti-DDoS Premium](https://common-buy-intl.alibabacloud.com/?commodityCode=ddosDip_intl) instance and switch your service traffic to the IP address of Anti-DDoS Pro or Anti-DDoS Premium. This allows you to obtain up to Tbit/s of protection capabilities. Anti-DDoS Pro and Anti-DDoS Premium defend your service against DDoS attacks with a committed protection capability and defense effect.

## What is the difference between Security Credibility and Anti-DDoS Pro or Anti-DDoS Premium in terms of protection threshold increase?

Security Credibility increases the protection capability against the first attack for users with a qualified credit score. The threshold to trigger blackhole filtering is adjusted as the credibility score changes. Security Credibility does not promise a fixed protection capability.

Anti-DDoS Pro and Anti-DDoS Premium help users defend against DDoS attacks with a committed protection capability and defense effect.

