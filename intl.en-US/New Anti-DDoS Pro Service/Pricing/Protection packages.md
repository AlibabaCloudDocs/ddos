# Protection packages {#concept_490664 .concept}

The new Anti-DDoS Pro provides two protection packages: standard and enhanced. The enhanced package includes all features of the standard package and provides the following exclusive features: static page caching, non-standard ports support, and geo-blocking. You can select the protection package based on your business needs.

When you purchase Anti-DDoS Pro instances, the standard package is selected by default. You can choose the enhanced package for advanced DDoS protection capabilities. For each instance, Anti-DDoS Pro charges additional RMB 8,000 per month for the enhanced package.

If you have already purchased Anti-DDoS Pro instances of the standard package, you can [Upgrade Anti-DDoS Pro instance configurations](reseller.en-US/New Anti-DDoS Pro Service/Pricing/Upgrade Anti-DDoS Pro instance configurations.md#).

**Note:** After you purchased the enhanced package or upgraded your instance, you need to modify domain configurations to enable the enhanced capabilities.

## Comparison of the standard and enhanced package {#section_k52_8uh_xdr .section}

The enhanced package offers advanced protection capabilities and supports non-standard ports.

|Category|Feature|Description|Standard package|Enhanced package|
|--------|-------|-----------|----------------|----------------|
|Protection algorithm|Protection against DDoS attacks|Supports protection against common DDoS attacks such as malformed packet attacks and flood attacks.|![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/394975/156747975748605_en-US.png)

|![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/394975/156747975748605_en-US.png)

|
|Protection against resource exhaustion attacks|Supports protection against common HTTP flood attacks, such as HTTP GET floods and HTTP POST floods. For more information, see [Configure HTTP flood protection](reseller.en-US/New Anti-DDoS Pro Service/User Guide/Configure layer 7 protection/Configure HTTP flood protection.md#).

 |![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/394975/156747975748605_en-US.png)

|![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/394975/156747975748605_en-US.png)

|
|Intelligent protection| -   Supports intelligent protection against application layer floods and effectively mitigates HTTP flood attacks.
-   Supports intelligent protection against transport layer floods and effectively mitigates TCP flood attacks.

 For more information, see [Enable intelligent protection](reseller.en-US/New Anti-DDoS Pro Service/User Guide/Configure layer 7 protection/Enable intelligent protection.md#).|![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/394975/156747975748605_en-US.png)

|![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/394975/156747975748605_en-US.png)

|
|Protection rule|Blacklist and whitelist|For each protected domain, the blacklist and whitelist can each contain a maximum of 200 IP addresses or CIDR blocks. For more information, see [Configure the blacklist and whitelist](reseller.en-US/New Anti-DDoS Pro Service/User Guide/Configure layer 7 protection/Configure the blacklist and whitelist.md#).

 |![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/394975/156747975748605_en-US.png)

|![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/394975/156747975748605_en-US.png)

|
|Accurate access control|Supports fine-grained access control based on HTTP fields. For more information, see [Configure fine-grained access control rules](reseller.en-US/New Anti-DDoS Pro Service/User Guide/Configure layer 7 protection/Configure fine-grained access control rules.md#).

 |For each protected domain, a maximum of five rules can be configured based on the following fields: IP, URL, Referer, and User-Agent.|For each protected domain, a maximum of 10 rules can be configured.|
|Geo-blocking|Supports blocking traffic based on geographical locations. For more information, see [Block requests from specific regions](reseller.en-US/New Anti-DDoS Pro Service/User Guide/Configure layer 7 protection/Block requests from specific regions.md#).

 |![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/394975/156747975848606_en-US.png)

|![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/394975/156747975748605_en-US.png)

|
|Connection method|Standard HTTP ports \(80, 8080\) and HTTPS ports \(443, 8443\).|Supports DDoS protection based on standard HTTP ports \(80, 8080\) and HTTPS ports \(443, 8443\).|![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/394975/156747975748605_en-US.png)

|![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/394975/156747975748605_en-US.png)

|
|Non-standard HTTP and HTTPS ports.|Supports DDoS protection based on non-standard HTTP and HTTPS ports. **Note:** For each instance, the associated domains can use a maximum of 10 ports.

 |![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/394975/156747975848606_en-US.png)

|![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/394975/156747975748605_en-US.png)

|
|Other|Static page caching|Supports static page caching to reduce page loading time. **Note:** Currently, static page caching is in preview stage. For each protected domain, a maximum of three rules can be configured.

 For more information, see [Configure static page caching rules](reseller.en-US/New Anti-DDoS Pro Service/User Guide/Configure layer 7 protection/Configure static page caching rules.md#).|![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/394975/156747975848606_en-US.png)

|![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/394975/156747975748605_en-US.png)

|

