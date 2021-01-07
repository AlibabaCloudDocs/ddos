# List of operations by function

The following tables list API operations available for use in Anti-DDoS Pro and Anti-DDoS Premium.

**Note:** Operations described in this topic apply only to Anti-DDoS Pro and Anti-DDoS Premium.

-   Before you call the following operations, make sure that you have purchased an Anti-DDoS Pro or Anti-DDoS Premium instance.

    For more information, see [Purchase mitigation plans for Anti-DDoS Pro and Anti-DDoS Premium](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Purchase mitigation plans for Anti-DDoS Pro and Anti-DDoS Premium.md).

-   Unless otherwise specified, the following operations apply to both Anti-DDoS Pro and Anti-DDoS Premium. If some operations apply to only one of them, extra descriptions are provided.

    For more information about the differences between Anti-DDoS Pro and Anti-DDoS Premium, see [Differences between the features of Anti-DDoS Pro and Anti-DDoS Premium](/intl.en-US/Product Introduction on Alibaba DDoS Protection/What are Anti-DDoS Pro and Anti-DDoS Premium?.md).

-   For more information, visit [OpenAPI Explorer](https://api.aliyun.com).

## Instances

|Operation|Description|
|---------|-----------|
|[DescribeInstanceIds](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Instances/DescribeInstanceIds.md)|Queries the IDs of all Anti-DDoS Pro or Anti-DDoS Premium instances.|
|[DescribeInstances](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Instances/DescribeInstances.md)|Queries the detailed information about one or more Anti-DDoS Pro or Anti-DDoS Premium instances, such as traffic forwarding status, expiration status, and overdue payment status.|
|[DescribeInstanceStatus](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Instances/DescribeInstanceStatus.md)|Queries the status of a specified Anti-DDoS Pro or Anti-DDoS Premium instance. The status includes normal, expired, overdue, and released.|
|[DescribeInstanceDetails](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Instances/DescribeInstanceDetails.md)|Queries the IP addresses and Internet service provider \(ISP\) line information about one or more specified Anti-DDoS Pro or Anti-DDoS Premium instances.|
|[DescribeInstanceSpecs](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Instances/DescribeInstanceSpecs.md)|Queries the specifications of one or more specified Anti-DDoS Pro or Anti-DDoS Premium instances.|
|[DescribeInstanceStatistics](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Instances/DescribeInstanceStatistics.md)|Queries the statistics on one or more specified Anti-DDoS Pro or Anti-DDoS Premium instances, such as the numbers of protected domain names and ports.|
|[ModifyInstanceRemark](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Instances/ModifyInstanceRemark.md)|Modifies the description of an Anti-DDoS Pro or Anti-DDoS Premium instance.|
|[DescribeElasticBandwidthSpec](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Instances/DescribeElasticBandwidthSpec.md)|Queries the available burstable protection bandwidth of a specified Anti-DDoS Pro instance.|
|[ModifyElasticBandWidth](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Instances/ModifyElasticBandWidth.md)|Modifies the burstable protection bandwidth of a specified Anti-DDoS Pro instance.|
|[DescribeDefenseCountStatistics](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Instances/DescribeDefenseCountStatistics.md)|Queries the information about mitigation sessions of an Anti-DDoS Premium instance, such as the numbers of available and used advanced mitigation sessions.|
|[ReleaseInstance](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Instances/ReleaseInstance.md)|Releases an Anti-DDoS Pro or Anti-DDoS Premium instance that has expired.|

## Website configuration

|Operation|Description|
|---------|-----------|
|[DescribeDomains](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Website configuration/DescribeDomains.md)|Queries the domain names that are added to one or more Anti-DDoS Pro or Anti-DDoS Premium instances.|
|[DescribeWebRules](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Website configuration/DescribeWebRules.md)|Queries the forwarding rules of a website.|
|[CreateWebRule](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Website configuration/CreateWebRule.md)|Creates a forwarding rule for a website.|
|[ModifyWebRule](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Website configuration/ModifyWebRule.md)|Modifies the forwarding rule of a website.|
|[DeleteWebRule](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Website configuration/DeleteWebRule.md)|Deletes the forwarding rule of a website.|
|[DescribeWebInstanceRelations](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Website configuration/DescribeWebInstanceRelations.md)|Queries the information about Anti-DDoS Pro or Anti-DDoS Premium instances to which the websites are added.|
|[AssociateWebCert](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Website configuration/AssociateWebCert.md)|Associates an SSL certificate with the forwarding rule of a website.|
|[ModifyTlsConfig](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Website configuration/ModifyTlsConfig.md)|Modifies the Transport Layer Security \(TLS\) policy configuration for the forwarding rule of a website.|
|[DescribeWebCustomPorts](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Website configuration/DescribeWebCustomPorts.md)|Queries the supported custom ports of a website.|
|[DescribeWebAccessMode](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Website configuration/DescribeWebAccessMode.md)|Queries the access mode settings of a website.|
|[ModifyWebAccessMode](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Website configuration/ModifyWebAccessMode.md)|Modifies the access mode settings of a website.|
|[DescribeCerts](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Website configuration/DescribeCerts.md)|Queries the certificate information about a website.|
|[DescribeCnameReuses](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Website configuration/DescribeCnameReuses.md)|Queries the CNAME reuse information about a website.|
|[ModifyCnameReuse](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Website configuration/ModifyCnameReuse.md)|Enables or disables CNAME reuse for a website.|
|[ModifyHttp2Enable](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Website configuration/ModifyHttp2Enable.md)|Enables or disables HTTP/2 for the forwarding rule of a website.|
|[DescribeL7RsPolicy](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Website configuration/DescribeL7RsPolicy.md)|Queries the back-to-origin policies for the forwarding rule of a website.|
|[ConfigL7RsPolicy](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Website configuration/ConfigL7RsPolicy.md)|Configures a back-to-origin policy for the forwarding rule of a website.|

## Port configuration

|Operation|Description|
|---------|-----------|
|[DescribeNetworkRules](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Port configuration/DescribeNetworkRules.md)|Queries port forwarding rules.|
|[CreateNetworkRules](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Port configuration/CreateNetworkRules.md)|Creates a port forwarding rule.|
|[ConfigNetworkRules](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Port configuration/ConfigNetworkRules.md)|Modifies a port forwarding rule.|
|[DeleteNetworkRule](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Port configuration/DeleteNetworkRule.md)|Deletes a port forwarding rule.|
|[DescribeHealthCheckList](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Port configuration/DescribeHealthCheckList.md)|Queries the Layer 4 or Layer 7 health check configurations of a port forwarding rule.|
|[ModifyHealthCheckConfig](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Port configuration/ModifyHealthCheckConfig.md)|Modifies the Layer 4 or Layer 7 health check configurations of a port forwarding rule.|
|[DescribeHealthCheckStatus](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Port configuration/DescribeHealthCheckStatus.md)|Queries the health status of an origin server.|

## Sec-Traffic Manager

|Operation|Description|
|---------|-----------|
|[DescribeSchedulerRules](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Sec-Traffic manager/DescribeSchedulerRules.md)|Queries the scheduling rules that are created for Sec-Traffic Manager.|
|[CreateSchedulerRule](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Sec-Traffic manager/CreateSchedulerRule.md)|Creates a scheduling rule for Sec-Traffic Manager.|
|[ModifySchedulerRule](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Sec-Traffic manager/ModifySchedulerRule.md)|Modifies the scheduling rule of Sec-Traffic Manager.|
|[DeleteSchedulerRule](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Sec-Traffic manager/DeleteSchedulerRule.md)|Deletes the scheduling rule of Sec-Traffic Manager.|

## Protection for infrastructure

|Operation|Description|
|---------|-----------|
|[DescribeAutoCcListCount](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Protection for infrastructure/DescribeAutoCcListCount.md)|Queries the numbers of IP addresses in the whitelist and blacklist of an Anti-DDoS Pro or Anti-DDoS Premium instance.|
|[DescribeAutoCcBlacklist](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Protection for infrastructure/DescribeAutoCcBlacklist.md)|Queries IP addresses in the blacklist of an Anti-DDoS Pro or Anti-DDoS Premium instance.|
|[AddAutoCcBlacklist](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Protection for infrastructure/AddAutoCcBlacklist.md)|Adds IP addresses to the blacklist of an Anti-DDoS Pro or Anti-DDoS Premium instance.|
|[DeleteAutoCcBlacklist](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Protection for infrastructure/DeleteAutoCcBlacklist.md)|Removes IP addresses from the blacklist of an Anti-DDoS Pro or Anti-DDoS Premium instance.|
|[EmptyAutoCcBlacklist](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Protection for infrastructure/EmptyAutoCcBlacklist.md)|Clears the blacklist of an Anti-DDoS Pro or Anti-DDoS Premium instance.|
|[DescribeAutoCcWhitelist](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Protection for infrastructure/DescribeAutoCcWhitelist.md)|Queries IP addresses in the whitelist of an Anti-DDoS Pro or Anti-DDoS Premium instance.|
|[AddAutoCcWhitelist](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Protection for infrastructure/AddAutoCcWhitelist.md)|Adds IP addresses to the whitelist of an Anti-DDoS Pro or Anti-DDoS Premium instance.|
|[DeleteAutoCcWhitelist](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Protection for infrastructure/DeleteAutoCcWhitelist.md)|Removes IP addresses from the whitelist of an Anti-DDoS Pro or Anti-DDoS Premium instance.|
|[EmptyAutoCcWhitelist](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Protection for infrastructure/EmptyAutoCcWhitelist.md)|Clears the whitelist of an Anti-DDoS Pro or Anti-DDoS Premium instance.|
|[DescribeUnBlackholeCount](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Protection for infrastructure/DescribeUnBlackholeCount.md)|Queries the total and remaining quotas that you can deactivate blackhole filtering.|
|[DescribeBlackholeStatus](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Protection for infrastructure/DescribeBlackholeStatus.md)|Queries the blackhole filtering status of one or more Anti-DDoS Pro or Anti-DDoS Premium instances.|
|[ModifyBlackholeStatus](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Protection for infrastructure/ModifyBlackholeStatus.md)|Deactivates blackhole filtering.|
|[DescribeNetworkRegionBlock](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Protection for infrastructure/DescribeNetworkRegionBlock.md)|Queries the blocked regions that are configured for an Anti-DDoS Pro or Anti-DDoS Premium instance.|
|[ConfigNetworkRegionBlock](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Protection for infrastructure/ConfigNetworkRegionBlock.md)|Configures blocked regions for an Anti-DDoS Pro or Anti-DDoS Premium instance.|
|[DescribeBlockStatus](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Protection for infrastructure/DescribeBlockStatus.md)|Queries the Diversion from Origin Server configurations of one or more Anti-DDoS Pro instances.|
|[ModifyBlockStatus](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Protection for infrastructure/ModifyBlockStatus.md)|Modifies the Diversion from Origin Server configurations of an Anti-DDoS Pro instances.|
|[DescribeUnBlockCount](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Protection for infrastructure/DescribeUnBlockCount.md)|Queries the remaining quota that you can use the Diversion from Origin Server policy.|

## Protection for website services

|Operation|Description|
|---------|-----------|
|[DescribeWebCcProtectSwitch](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Protection for website services/DescribeWebCcProtectSwitch.md)|Queries the status of each protection policy for websites.|
|[ModifyWebAIProtectSwitch](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Protection for website services/ModifyWebAIProtectSwitch.md)|Enables or disables the Intelligent Protection policy for a website.|
|[ModifyWebAIProtectMode](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Protection for website services/ModifyWebAIProtectMode.md)|Modifies the mode settings of the Intelligent Protection policy for a website.|
|[ModifyWebIpSetSwitch](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Protection for website services/ModifyWebIpSetSwitch.md)|Enables or disables the Black Lists and White Lists \(Domain Names\) policy for a website.|
|[ConfigWebIpSet](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Protection for website services/ConfigWebIpSet.md)|Configures the IP address whitelist and blacklist for a website.|
|[EnableWebCC](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Protection for website services/EnableWebCC.md)|Enables the Frequency Control policy for a website.|
|[DisableWebCC](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Protection for website services/DisableWebCC.md)|Disables the Frequency Control policy for a website.|
|[ConfigWebCCTemplate](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Protection for website services/ConfigWebCCTemplate.md)|Modifies the settings of the Frequency Control policy for a website.|
|[EnableWebCCRule](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Protection for website services/EnableWebCCRule.md)|Turns on Custom Rule of the Frequency Control policy for a website.|
|[DisableWebCCRule](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Protection for website services/DisableWebCCRule.md)|Turns off Custom Rule of the Frequency Control policy for a website.|
|[DescribeWebCCRules](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Protection for website services/DescribeWebCCRules.md)|Queries the custom frequency control rules that are created for a website.|
|[CreateWebCCRule](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Protection for website services/CreateWebCCRule.md)|Creates a custom frequency control rule for a website.|
|[ModifyWebCCRule](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Protection for website services/ModifyWebCCRule.md)|Modifies the custom frequency control rule of a website.|
|[DeleteWebCCRule](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Protection for website services/DeleteWebCCRule.md)|Deletes the custom frequency control rule of a website.|
|[ModifyWebPreciseAccessSwitch](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Protection for website services/ModifyWebPreciseAccessSwitch.md)|Enables or disables the Accurate Access Control policy for a website.|
|[DescribeWebPreciseAccessRule](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Protection for website services/DescribeWebPreciseAccessRule.md)|Queries the accurate access control rules that are created for websites.|
|[ModifyWebPreciseAccessRule](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Protection for website services/ModifyWebPreciseAccessRule.md)|Modifies the accurate access control rules that are created for a website.|
|[DeleteWebPreciseAccessRule](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Protection for website services/DeleteWebPreciseAccessRule.md)|Deletes the accurate access control rules that are created for a website.|
|[ModifyWebAreaBlockSwitch](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Protection for website services/ModifyWebAreaBlockSwitch.md)|Enables or disables the Blocked Regions \(Domain Names\) policy for a website.|
|[DescribeWebAreaBlockConfigs](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Protection for website services/DescribeWebAreaBlockConfigs.md)|Queries the Blocked Regions \(Domain Names\) configurations for websites.|
|[ModifyWebAreaBlock](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Protection for website services/ModifyWebAreaBlock.md)|Modifies the blocked regions that are configured in the Blocked Regions \(Domain Names\) policy for a website.|

## Protection for non-website services

|Operation|Description|
|---------|-----------|
|[DescribePortAutoCcStatus](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Protection for non-website services/DescribePortAutoCcStatus.md)|Queries the Intelligent Protection configurations for non-website services.|
|[ModifyPortAutoCcStatus](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Protection for non-website services/ModifyPortAutoCcStatus.md)|Modifies the Intelligent Protection configurations for non-website services.|
|[DescribeNetworkRuleAttributes](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Protection for non-website services/DescribeNetworkRuleAttributes.md)|Queries the mitigation settings of the port forwarding rule for a non-website service. The mitigation settings include session persistence and DDoS mitigation policies.|
|[ModifyNetworkRuleAttribute](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Protection for non-website services/ModifyNetworkRuleAttribute.md)|Modifies the session persistence policy of the port forwarding rule for a non-website service.|

## Scenario-specific policies

|Operation|Description|
|---------|-----------|
|[DescribeSceneDefensePolicies](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Custom scenario policy/DescribeSceneDefensePolicies.md)|Queries details about scenario-specific policies.|
|[CreateSceneDefensePolicy](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Custom scenario policy/CreateSceneDefensePolicy.md)|Creates a scenario-specific custom policy.|
|[ModifySceneDefensePolicy](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Custom scenario policy/ModifySceneDefensePolicy.md)|Modifies a scenario-specific custom policy.|
|[DeleteSceneDefensePolicy](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Custom scenario policy/DeleteSceneDefensePolicy.md)|Deletes a scenario-specific custom policy.|
|[DescribeSceneDefenseObjects](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Custom scenario policy/DescribeSceneDefenseObjects.md)|Queries the protection objects of a scenario-specific custom policy.|
|[AttachSceneDefenseObject](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Custom scenario policy/AttachSceneDefenseObject.md)|Adds a protection object to a scenario-specific custom policy.|
|[DetachSceneDefenseObject](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Custom scenario policy/DetachSceneDefenseObject.md)|Removes a protection object from a scenario-specific custom policy.|
|[EnableSceneDefensePolicy](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Custom scenario policy/EnableSceneDefensePolicy.md)|Enables a scenario-specific custom policy.|
|[DisableSceneDefensePolicy](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Custom scenario policy/DisableSceneDefensePolicy.md)|Disables a scenario-specific custom policy.|

## Attack analysis

|Operation|Description|
|---------|-----------|
|[DescribeDDosEventMax]()|Queries the peaks of volumetric attacks \(bit/s\), connection flood attacks \(CPS\), and resource exhaustion attacks on websites \(QPS\) within a specific period.|
|[DescribeDDosAllEventList]()|Queries attack events.|
|[DescribeDDosEventArea]()|Queries source regions from which a volumetric attack is initiated.|
|[DescribeDDosEventAttackType]()|Queries the details of a volumetric attack type.|
|[DescribeDDosEventIsp]()|Queries the ISP of a volumetric attack.|
|[DescribeDDosEventSrcIp]()|Queries the source IP addresses from which a volumetric attack is initiated.|

## Monitoring reports

|Operation|Description|
|---------|-----------|
|[DescribeDDoSEvents](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Monitoring reports/DescribeDDoSEvents.md)|Queries the attack events launched against one or more Anti-DDoS Pro or Anti-DDoS Premium instances.|
|[DescribePortFlowList](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Monitoring reports/DescribePortFlowList.md)|Queries the traffic data of one or more Anti-DDoS Pro or Anti-DDoS Premium instances.|
|[DescribePortConnsList](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Monitoring reports/DescribePortConnsList.md)|Queries the connections established over the ports of one or more Anti-DDoS Pro or Anti-DDoS Premium instances.|
|[DescribePortConnsCount](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Monitoring reports/DescribePortConnsCount.md)|Queries the statistics on the connections established over the ports of one or more Anti-DDoS Pro or Anti-DDoS Premium instances.|
|[DescribePortMaxConns](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Monitoring reports/DescribePortMaxConns.md)|Queries the maximum number of connections that can be established over the ports of one or more Anti-DDoS Pro or Anti-DDoS Premium instances.|
|[DescribePortAttackMaxFlow](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Monitoring reports/DescribePortAttackMaxFlow.md)|Queries the peak bandwidth and peak packet rates of attack traffic on one or more Anti-DDoS Pro or Anti-DDoS Premium instances within a specific period.|
|[DescribePortViewSourceCountries](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Monitoring reports/DescribePortViewSourceCountries.md)|Queries the areas and countries from which requests are sent to one or more Anti-DDoS Pro or Anti-DDoS Premium instances within a specific period.|
|[DescribePortViewSourceProvinces](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Monitoring reports/DescribePortViewSourceProvinces.md)|Queries the administrative regions inside China from which requests are sent to one or more Anti-DDoS Pro or Anti-DDoS Premium instances within a specific period.|
|[DescribePortViewSourceIsps](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Monitoring reports/DescribePortViewSourceIsps.md)|Queries the ISPs from which requests are sent to one or more Anti-DDoS Pro or Anti-DDoS Premium instances within a specific period.|
|[DescribeDomainAttackEvents](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Monitoring reports/DescribeDomainAttackEvents.md)|Queries the attack events launched against a website.|
|[DescribeDomainQPSList](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Monitoring reports/DescribeDomainQPSList.md)|Queries the statistics on the queries per second \(QPS\) of a website.|
|[DescribeDomainQpsWithCache](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Monitoring reports/DescribeDomainQpsWithCache.md)|Queries the QPS information about a website, such as the total QPS, QPS when protection policies are triggered, and cache hit ratio.|
|[DescribeDomainOverview](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Monitoring reports/DescribeDomainOverview.md)|Queries the attack overview of a website, such as the peak traffic of HTTP and HTTPS traffic.|
|[DescribeDomainStatusCodeList](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Monitoring reports/DescribeDomainStatusCodeList.md)|Queries the statistics on response status codes of a website.|
|[DescribeDomainStatusCodeCount](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Monitoring reports/DescribeDomainStatusCodeCount.md)|Queries the statistics on response status codes of a website within a specific period.|
|[DescribeDomainTopAttackList](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Monitoring reports/DescribeDomainTopAttackList.md)|Queries the peak QPS information about a website, such as the attack QPS and total QPS, within a specific period.|
|[DescribeDomainViewSourceCountries](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Monitoring reports/DescribeDomainViewSourceCountries.md)|Queries the areas and countries from which requests are sent to a website within a specific period.|
|[DescribeDomainViewSourceProvinces](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Monitoring reports/DescribeDomainViewSourceProvinces.md)|Queries the administrative regions inside China from which requests are sent to a website within a specific period.|
|[DescribeDomainViewTopCostTime](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Monitoring reports/DescribeDomainViewTopCostTime.md)|Queries the top N URLs that require the longest time to respond to requests within a specific period.|
|[DescribeDomainViewTopUrl](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Monitoring reports/DescribeDomainViewTopUrl.md)|Queries the top N URLs that receive the most requests within a specific period.|

## Log analysis

|Operation|Description|
|---------|-----------|
|[DescribeSlsOpenStatus](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Log analysis/DescribeSlsOpenStatus.md)|Checks whether Alibaba Cloud Log Service is activated.|
|[DescribeSlsAuthStatus](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Log analysis/DescribeSlsAuthStatus.md)|Checks whether Anti-DDoS Pro or Anti-DDoS Premium is authorized to access Log Service.|
|[DescribeLogStoreExistStatus](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Log analysis/DescribeLogStoreExistStatus.md)|Checks whether a Logstore is created for Anti-DDoS Pro or Anti-DDoS Premium.|
|[DescribeSlsLogstoreInfo](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Log analysis/DescribeSlsLogstoreInfo.md)|Queries the Logstore information about Anti-DDoS Pro or Anti-DDoS Premium, such as the log storage capacity and duration.|
|[ModifyFullLogTtl](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Log analysis/ModifyFullLogTtl.md)|Modifies the full log storage duration for Anti-DDoS Pro or Anti-DDoS Premium.|
|[DescribeWebAccessLogDispatchStatus](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Log analysis/DescribeWebAccessLogDispatchStatus.md)|Checks whether the Log Analysis feature is enabled for all domain names.|
|[DescribeWebAccessLogStatus](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Log analysis/DescribeWebAccessLogStatus.md)|Queries the information about the Log Analysis feature for a website, such as the feature status, and the Log Service project and Logstore that are used.|
|[EnableWebAccessLogConfig](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Log analysis/EnableWebAccessLogConfig.md)|Enables the Log Analysis feature for a website.|
|[DisableWebAccessLogConfig](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Log analysis/DisableWebAccessLogConfig.md)|Disables the Log Analysis feature for a website.|
|[DescribeWebAccessLogEmptyCount](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Log analysis/DescribeWebAccessLogEmptyCount.md)|Queries the remaining quota that you can clear the Logstore.|
|[EmptySlsLogstore](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Log analysis/EmptySlsLogstore.md)|Clears the Logstore of Anti-DDoS Pro or Anti-DDoS Premium.|

## Tag management

|Operation|Description|
|---------|-----------|
|[DescribeTagKeys](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Tag/DescribeTagKeys.md)|Queries all tag keys.|
|[DescribeTagResources](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Tag/DescribeTagResources.md)|Queries the tags that are bound to resources.|
|[CreateTagResources](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Tag/CreateTagResources.md)|Binds tags to resources.|
|[DeleteTagResources](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Tag/DeleteTagResources.md)|Unbinds tags from resources.|

## Static page caching

|Operation|Description|
|---------|-----------|
|[DescribeWebCacheConfigs](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Static page caching/DescribeWebCacheConfigs.md)|Queries the Static Page Caching configurations of websites.|
|[ModifyWebCacheSwitch](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Static page caching/ModifyWebCacheSwitch.md)|Enables or disables the Static Page Caching policy for a website.|
|[ModifyWebCacheMode](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Static page caching/ModifyWebCacheMode.md)|Modifies the cache mode settings of the Static Page Caching policy for a website.|
|[ModifyWebCacheCustomRule](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Static page caching/ModifyWebCacheCustomRule.md)|Modifies the custom rule of the Static Page Caching policy for a website.|
|[DeleteWebCacheCustomRule](/intl.en-US/API reference/Anti-DDoS Pro & Premium/Static page caching/DeleteWebCacheCustomRule.md)|Deletes the custom rules of the Static Page Caching policy for a website.|

## System configurations and logs

|Operation|Description|
|---------|-----------|
|[DescribeStsGrantStatus](/intl.en-US/API reference/Anti-DDoS Pro & Premium/System configuration and logs/DescribeStsGrantStatus.md)|Checks whether Anti-DDoS Pro or Anti-DDoS Premium is authorized to access other cloud services.|
|[DescribeBackSourceCidr](/intl.en-US/API reference/Anti-DDoS Pro & Premium/System configuration and logs/DescribeBackSourceCidr.md)|Queries the back-to-origin Classless Inter-Domain Routing \(CIDR\) blocks of Anti-DDoS Pro or Anti-DDoS Premium.|
|[DescribeOpEntities](/intl.en-US/API reference/Anti-DDoS Pro & Premium/System configuration and logs/DescribeOpEntities.md)|Queries the operations logs of Anti-DDoS Pro.|
|[DescribeDefenseRecords](/intl.en-US/API reference/Anti-DDoS Pro & Premium/System configuration and logs/DescribeDefenseRecords.md)|Queries the advanced mitigation logs of Anti-DDoS Premium.|
|[DescribeAsyncTasks](/intl.en-US/API reference/Anti-DDoS Pro & Premium/System configuration and logs/DescribeAsyncTasks.md)|Queries details about asynchronous export tasks, such as the IDs, start time, end time, status, parameters, and results.|
|[CreateAsyncTask](/intl.en-US/API reference/Anti-DDoS Pro & Premium/System configuration and logs/CreateAsyncTask.md)|Creates an asynchronous export task to export business forwarding rules for websites, port forwarding rules, session persistence and health check configurations, DDoS mitigation policies, the IP address blacklist, or the IP address whitelist.|
|[DeleteAsyncTask](/intl.en-US/API reference/Anti-DDoS Pro & Premium/System configuration and logs/DeleteAsyncTask.md)|Deletes an asynchronous export task.|

