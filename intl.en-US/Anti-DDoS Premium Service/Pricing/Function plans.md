# Function plans {#concept_490664 .concept}

Anti-DDoS Premium provides two function plans: standard function and enhanced function. In addition to the features provided by the standard function plan, the enhanced function plan also provides enhanced features such as website acceleration, non-standard service ports, and geo-blocking. These features enable Anti-DDoS Premium to be associated with more businesses and provide stronger protection against DDoS attacks. You can select an appropriate function plan based on your business conditions and security requirements.

When you purchase an Anti-DDoS Premium instance, the standard function is the default function plan. You can select the enhanced function to associate more businesses with Anti-DDoS Premium and increase the protection against DDoS attacks. The enhanced function plan costs an extra 8,000 RMB per month. This cost is added to the price of the standard function plan for the instance.

You can upgrade the instances that have the standard function plan to activate the enhanced function plan.

**Note:** After purchasing or upgrading to an enhanced function plan, you must edit the domain configuration to associate the domain with the Anti-DDoS Premium instance that has the enhanced function plan. This way, the enhanced features are available to the website.

## Comparison between the standard and enhanced function plans {#section_k52_8uh_xdr .section}

Compared with the standard function plan, the enhanced function plan allows you to associate more businesses and increases protection against attacks.

|Category|Feature|Description|Standard function|Enhanced function|
|--------|-------|-----------|-----------------|-----------------|
|Protection algorithm|Protection against DoS attacks|Supports protection against common DDoS attacks, including malformed packet attacks and various HTTP flood attacks.|![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/394975/156436699548605_en-US.png)

|![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/394975/156436699548605_en-US.png)

|
|Protection against resource exhaustion attacks|Supports protection against common Layer 4 or Layer 7 resource exhaustion attacks, such as HTTP GET flood and HTTP POST flood attacks. For more information, see [Configure HTTP\(S\) flood protection](reseller.en-US/Anti-DDoS Premium Service/User Guide/Layer 7 protection configuration/Configure HTTP(S) flood protection.md#).

 |![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/394975/156436699548605_en-US.png)

|![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/394975/156436699548605_en-US.png)

|
|Intelligent protection| -   Supports intelligent protection against Layer 7 HTTP flood attacks at the application layer.
-   Supports intelligent protection against Layer 4 HTTP flood attacks and mitigates TCP connection exhaustion attacks.

 For more information, see [Enable intelligent protection](reseller.en-US/Anti-DDoS Premium Service/User Guide/Layer 7 protection configuration/Enable intelligent protection.md#).|![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/394975/156436699548605_en-US.png)

|![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/394975/156436699548605_en-US.png)

|
|Protection rule|Blacklist and whitelist|You can configure a whitelist and a blacklist for each domain associated with Anti-DDoS Premium. Each list can contain a maximum of 200 IP addresses or IP address ranges. For more information, see [Configure the blacklist and whitelist](reseller.en-US/Anti-DDoS Premium Service/User Guide/Layer 7 protection configuration/Configure the blacklist and whitelist.md#).

 |![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/394975/156436699548605_en-US.png)

|![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/394975/156436699548605_en-US.png)

|
|Accurate access control|Supports accurate matching of HTTP protection rules. For more information, see [Configure fine-grained access control rules](reseller.en-US/Anti-DDoS Premium Service/User Guide/Layer 7 protection configuration/Configure fine-grained access control rules.md#).

 |A maximum of five rules can be configured for each domain associated with Anti-DDoS Premium, and only the IP, URL, Referer, and User-Agent field are supported.|A maximum of 10 rules can be configured for each domain associated with Anti-DDoS Premium.|
|Geo-blocking|Supports the blocking of access traffic of each domain based on geographical locations. For more information, see [Block access requests from IP addresses in specific regions](reseller.en-US/Anti-DDoS Premium Service/User Guide/Layer 7 protection configuration/Block access requests from IP addresses in specific regions.md#).

 |![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/394975/156436699648606_en-US.png)

|![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/394975/156436699548605_en-US.png)

|
|Connection method|Standard HTTP \(80 or 8080\) and HTTPS \(443 or 8443\) ports forwarding|Supports Anti-DDoS protection for HTTP \(80 or 8080\) and HTTPS \(443 or 8443\) ports.|![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/394975/156436699548605_en-US.png)

|![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/394975/156436699548605_en-US.png)

|
|Non-standard HTTP and HTTPS ports forwarding|Supports Anti-DDoS protection for non-standard HTTP and HTTPS ports \(not limited to ports 80, 8080, 443, and 8443\). **Note:** Each instance can be configured with 10 distinguished non-standard ports for forwarding.

 |![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/394975/156436699648606_en-US.png)

|![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/394975/156436699548605_en-US.png)

|
|Others|Static page caching|Supports static page website acceleration. **Note:** The custom cache rule function is under public review. You can configure a maximum of three rules for each domain associated with Anti-DDoS Premium.

 For more information, see [Accelerate access to a static page](reseller.en-US/Anti-DDoS Premium Service/User Guide/Layer 7 protection configuration/Accelerate access to a static page.md#).|![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/394975/156436699648606_en-US.png)

|![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/394975/156436699548605_en-US.png)

|

