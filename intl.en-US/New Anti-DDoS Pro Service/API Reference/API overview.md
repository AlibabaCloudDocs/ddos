# API overview {#reference3502 .reference}

This topic summarizes all callable Anti-DDoS Pro APIs. For more information about each API, see the corresponding topics.

For more information about API resources, visit [API Explorer](https://api.aliyun.com).

## Instances {#section_x7p_eul_4g8 .section}

|API|Description|
|[DescribeInstances](reseller.en-US/New Anti-DDoS Pro Service/API Reference/Instances/DescribeInstances.md#)|Query all instances.|
|[DescribeInstanceDetails](reseller.en-US/New Anti-DDoS Pro Service/API Reference/Instances/DescribeInstanceDetails.md#)|Query instance details.|
|[DescribeInstanceSpecs](reseller.en-US/New Anti-DDoS Pro Service/API Reference/Instances/DescribeInstanceSpecs.md#)|Query instance configurations.|
|[DescribeInstanceStatistics](reseller.en-US/New Anti-DDoS Pro Service/API Reference/Instances/DescribeInstanceStatistics.md#)|Query rules configured on instances.|
|[DescribeElasticBandwidthSpec](reseller.en-US/New Anti-DDoS Pro Service/API Reference/Instances/DescribeElasticBandwidthSpec.md#)|Query the burstable bandwidth of instances.|
|[ModifyElasticBandWidth](reseller.en-US/New Anti-DDoS Pro Service/API Reference/Instances/ModifyElasticBandWidth.md#)|Modify the burstable bandwidth of instances.|
|[ModifyInstanceRemark](reseller.en-US/New Anti-DDoS Pro Service/API Reference/Instances/ModifyInstanceRemark.md#)|Modify the remarks on instances.|

## Layer 4 rules {#section_z52_0a0_vst .section}

|API|Description|
|[CreateLayer4Rule](reseller.en-US/New Anti-DDoS Pro Service/API Reference/Layer 4 rules/CreateLayer4Rule.md#)|Create layer 4 forwarding rules.|
|[ConfigLayer4Rule](reseller.en-US/New Anti-DDoS Pro Service/API Reference/Layer 4 rules/ConfigLayer4Rule.md#)|Edit layer 4 forwarding rules.|
|[DeleteLayer4Rule](reseller.en-US/New Anti-DDoS Pro Service/API Reference/Layer 4 rules/DeleteLayer4Rule.md#)|Delete layer 4 forwarding rules.|
|[ConfigLayer4RuleAttribute](reseller.en-US/New Anti-DDoS Pro Service/API Reference/Layer 4 rules/ConfigLayer4RuleAttribute.md#)|Configure the attributes of layer 4 forwarding rules, including session persistence and anti-DDoS protection policies.|
|[ConfigHealthCheck](reseller.en-US/New Anti-DDoS Pro Service/API Reference/Layer 4 rules/ConfigHealthCheck.md#)|Configure layer 4 or layer 7 health check.|
|[DescribeLayer4Rules](reseller.en-US/New Anti-DDoS Pro Service/API Reference/Layer 4 rules/DescribeLayer4Rules.md#)|Query layer 4 forwarding rules.|
|[DescribeLayer4RuleAttributes](reseller.en-US/New Anti-DDoS Pro Service/API Reference/Layer 4 rules/DescribeLayer4RuleAttributes.md#)|Query the attributes of layer 4 forwarding rules, including session persistence and anti-DDoS protection policies.|
|[DescribeHealthCheckList](reseller.en-US/New Anti-DDoS Pro Service/API Reference/Layer 4 rules/DescribeHealthCheckList.md#)|Query layer 4 or layer 7 health check settings.|
|[DescribeHealthCheckStatusList](reseller.en-US/New Anti-DDoS Pro Service/API Reference/Layer 4 rules/DescribeHealthCheckStatusList.md#)|Query health check status.|

## Layer 7 rules {#section_i56_5xa_lni .section}

|API|Description|
|[DescribeDomains](reseller.en-US/New Anti-DDoS Pro Service/API Reference/Layer 7 rules/DescribeDomains.md#)|Query layer 7 forwarding rules.|
|[CreateLayer7Rule](reseller.en-US/New Anti-DDoS Pro Service/API Reference/Layer 7 rules/CreateLayer7Rule.md#)|Create layer 7 forwarding rules.|
|[ConfigLayer7Rule](reseller.en-US/New Anti-DDoS Pro Service/API Reference/Layer 7 rules/ConfigLayer7Rule.md#)|Edit layer 7 forwarding rules.|
|[DeleteLayer7Rule](reseller.en-US/New Anti-DDoS Pro Service/API Reference/Layer 7 rules/DeleteLayer7Rule.md#)|Delete layer 7 forwarding rules.|
|[ConfigLayer7Cert](reseller.en-US/New Anti-DDoS Pro Service/API Reference/Layer 7 rules/ConfigLayer7Cert.md#)|Configure certificates.|
|[ConfigLayer7BlackWhiteList](reseller.en-US/New Anti-DDoS Pro Service/API Reference/Layer 7 rules/ConfigLayer7BlackWhiteList.md#)|Configure the blacklist and whitelist.|
|[DescribleLayer7InstanceRelations](reseller.en-US/New Anti-DDoS Pro Service/API Reference/Layer 7 rules/DescribleLayer7InstanceRelations.md#)|Query instances by domain.|
|[DescribleCertList](reseller.en-US/New Anti-DDoS Pro Service/API Reference/Layer 7 rules/DescribleCertList.md#)|Query certificates.|
|[EnableLayer7CC](reseller.en-US/New Anti-DDoS Pro Service/API Reference/Layer 7 rules/EnableLayer7CC.md#)|Enable layer 7 HTTP flood protection.|
|[DisableLayer7CC](reseller.en-US/New Anti-DDoS Pro Service/API Reference/Layer 7 rules/DisableLayer7CC.md#)|Disable layer 7 HTTP flood protection.|
|[EnableLayer7CCRule](reseller.en-US/New Anti-DDoS Pro Service/API Reference/Layer 7 rules/EnableLayer7CCRule.md#)|Enable layer 7 HTTP flood protection rules.|
|[DisableLayer7CCRule](reseller.en-US/New Anti-DDoS Pro Service/API Reference/Layer 7 rules/DisableLayer7CCRule.md#)|Disable layer 7 HTTP flood protection rules.|
|[AddLayer7CCRule](reseller.en-US/New Anti-DDoS Pro Service/API Reference/Layer 7 rules/AddLayer7CCRule.md#)|Add layer 7 HTTP flood protection rules.|
|[ConfigLayer7CCRule](reseller.en-US/New Anti-DDoS Pro Service/API Reference/Layer 7 rules/ConfigLayer7CCRule.md#)|Edit layer 7 HTTP flood protection rules.|
|[DescribeLayer7CCRules](reseller.en-US/New Anti-DDoS Pro Service/API Reference/Layer 7 rules/DescribeLayer7CCRules.md#)|Query layer 7 HTTP flood protection rules.|
|[DeleteLayer7CCRule](reseller.en-US/New Anti-DDoS Pro Service/API Reference/Layer 7 rules/DeleteLayer7CCRule.md#)|Delete layer 7 HTTP flood protection rules.|
|[ConfigLayer7CCTemplate](reseller.en-US/New Anti-DDoS Pro Service/API Reference/Layer 7 rules/ConfigLayer7CCTemplate.md#)|Set the mode of layer 7 HTTP flood protection.|
|[DescribeDomainAccessMode](reseller.en-US/New Anti-DDoS Pro Service/API Reference/Layer 7 rules/DescribeDomainAccessMode.md#)|Query the modes that are used to set up instances.|
|[ConfigDomainAccessMode](reseller.en-US/New Anti-DDoS Pro Service/API Reference/Layer 7 rules/ConfigDomainAccessMode.md#)|Configure the modes that are used to set up instances.|
|[DescribeBackSourceCidr](reseller.en-US/New Anti-DDoS Pro Service/API Reference/Layer 7 rules/DescribeBackSourceCidr.md#)|Query back-to-origin CIDR blocks.|

## Tasks {#section_u81_p9f_vpm .section}

|API|Description|
|[ListAsyncTask](reseller.en-US/New Anti-DDoS Pro Service/API Reference/Tasks/ListAsyncTask.md#)|Query asynchronous tasks.|
|[CreateAsyncTask](reseller.en-US/New Anti-DDoS Pro Service/API Reference/Tasks/CreateAsyncTask.md#)|Create asynchronous tasks.|
|[DeleteAsyncTask](reseller.en-US/New Anti-DDoS Pro Service/API Reference/Tasks/DeleteAsyncTask.md#)|Delete asynchronous tasks.|

## Logs {#section_ped_unl_n72 .section}

|API|Description|
|[DescribeOpEntities](reseller.en-US/New Anti-DDoS Pro Service/API Reference/Logs/DescribeOpEntities.md#)|Query operation logs.|

