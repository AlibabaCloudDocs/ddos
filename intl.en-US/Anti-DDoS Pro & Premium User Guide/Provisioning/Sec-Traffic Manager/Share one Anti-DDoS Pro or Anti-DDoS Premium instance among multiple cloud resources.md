# Share one Anti-DDoS Pro or Anti-DDoS Premium instance among multiple cloud resources

This topic describes how to associate IP addresses of multiple cloud resources to one Anti-DDoS Pro or Anti-DDoS Premium instance in cloud service interaction and tiered protection scenarios. If one of the cloud resources is attacked, service traffic of this cloud resource is switched to Anti-DDoS Pro or Anti-DDoS Premium.

## Cloud service interaction

1.  Configure Sec-Traffic Manager.

    For example, you have three cloud resources. Add an interaction rule for the IP address of each resource and associate the three rules with the IP address of the Anti-DDoS Pro or Anti-DDoS Premium instance. For more information, see [Create a cloud service interaction rule](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Sec-Traffic Manager/Create a cloud service interaction rule.md).

2.  Modify the DNS records.

    Add three CNAME records for your domain name and set the record values to the CNAME addresses in the three rules created in Step 1. For more information, see [Modify the CNAME record to reroute traffic by using Sec-Traffic Manager](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Provisioning settings/Modify the CNAME record to reroute traffic by using Sec-Traffic Manager.md).

3.  Verify the DNS records. Open a DNS test website to verify that the CNAME records added in Step 2 take effect.


## Tiered protection

1.  Purchase an Anti-DDoS Origin Enterprise instance.

    Add the three cloud resources to Anti-DDoS Origin Enterprise for protection. For more information, see [Add a protection target](/intl.en-US/Anti-DDoS Origin User Guide/Instances/Add a protection target.md).

2.  Configure Sec-Traffic Manager.

    Create a tiered protection rule for the IP address of each cloud resource and associate the three rules with the IP address of the Anti-DDoS Pro or Anti-DDoS Premium instance. For more information, see [Create a tiered protection rule](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Sec-Traffic Manager/Create a tiered protection rule.md).

3.  Modify the DNS records.

    Add three CNAME records for your domain name and set the record values to the CNAME addresses in the three rules created in Step 2. For more information, see [Modify the CNAME record to reroute traffic by using Sec-Traffic Manager](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Provisioning settings/Modify the CNAME record to reroute traffic by using Sec-Traffic Manager.md).

4.  Verify the DNS records. Open a DNS test website to verify that the CNAME records added in Step 3 take effect.


