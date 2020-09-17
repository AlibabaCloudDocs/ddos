# Configure Anti-DDoS Premium MCA

An Anti-DDoS Premium Mainland China Acceleration \(MCA\) instance can be used with an Anti-DDoS Premium Insurance Plan or Unlimited Plan instance to accelerate access to your services that are deployed outside mainland China.

An Anti-DDoS Premium instance is created.

**Note:** Only Anti-DDoS Premium supports MCA. Anti-DDoS Pro does not support MCA.

After you configure an Anti-DDoS Premium MCA instance that is used with an Anti-DDoS Premium Insurance Plan or Unlimited Plan instance, the instance protects your services. If no DDoS attacks are launched, the Anti-DDoS Premium MCA instance accelerates web access to your services. Otherwise, the Anti-DDoS Premium Insurance Plan or Unlimited Plan instance automatically takes over to mitigate DDoS attacks against your services.

For more information about the scenarios to which MCA applies, see [Scenarios of Anti-DDoS Premium]().

![Anti-DDoS Premium](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/0886328951/p35306.png)

You can configure an Anti-DDoS Premium MCA instance for a domain name \(Layer 7\) or service port \(Layer 4\).

After you purchase Anti-DDoS Premium MCA and Insurance Plan or Unlimited Plan instances, add your domain name or service port to the instances in the Anti-DDoS Premium console. Then, configure a Sec-Traffic Manager rule to enable the auto-switching between an Anti-DDoS Premium MCA instance and an Anti-DDoS Premium Insurance Plan or Unlimited Plan instance. This rule forwards non-attack traffic to the origin server of your web service.

1.  Log on to the [Anti-DDoS Pro console](https://yundun.console.aliyun.com/?p=ddoscoo).

2.  In the top navigation bar, select **Outside Mainland China**.

3.  Add your website or non-website services to both the Anti-DDoS Premium Insurance Plan or Unlimited Plan instance and the Anti-DDoS Premium MCA instance.

    **Note:** In this step, you do not need to change the DNS record.

    -   For information about how to add a website service to an Anti-DDoS Premium instance, see [Add a website](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Use domains/Add a website.md). When you add the website service and select dedicated IP addresses of Anti-DDoS Premium, select the dedicated IP addresses of both your Insurance Plan or Unlimited Plan and MCA instances.
    -   For information about how to add a service port to an Anti-DDoS Premium instance, see [Create forwarding rules](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Use ports/Create forwarding rules.md). Create forwarding rules for the Anti-DDoS Premium MCA instance and the Anti-DDoS Premium Insurance Plan or Unlimited Plan instance for your non-website services.

        **Note:** Before you add your non-website services to the Anti-DDoS Premium MCA instance, make sure that the services can be accessed by using domain names. This ensures that traffic can be automatically redirected to the Anti-DDoS Premium MCA instance. If your services are accessed by using IP addresses, traffic cannot be automatically redirected.

4.  Navigate to the Sec-Traffic Manager page, click the General tab, and click **Create Rule**.

    ![Sec-Traffic Manager](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/1471097951/p65412.png)

5.  On the Create Rule page, configure the required parameters and click **Next**.

    -   **Interaction Scenario**: Select **Network Acceleration**.
    -   **Name**: Enter the name of the rule.
    -   **Anti-DDoS Instance IP**: Select the dedicated IP address of the Anti-DDoS Premium Insurance Plan or Unlimited Plan instance.
    -   **Acceleration IP**: Select the dedicated IP address of the Anti-DDoS Premium MCA instance.
    ![Create a rule](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/0886328951/p35312.png)

    After the rule is created, the system uses the Anti-DDoS Premium MCA instance to accelerate web access if no DDoS attacks are launched. If DDoS attacks are launched, Sec-Traffic Manager automatically redirects traffic to the Anti-DDoS Premium Insurance Plan or Unlimited Plan instance for traffic scrubbing.

    After you create a port forwarding rule, the system generates a CNAME address. You only need to change the DNS record to map the domain name to the CNAME address.

    **Note:** When you add your services, make sure that you have selected the dedicated IP addresses of both the Anti-DDoS Premium Insurance Plan or Unlimited Plan instance and the Anti-DDoS Premium MCA instance.

6.  Change the DNS record for the domain name at your DNS service provider.

    After you map your domain name to the CNAME address generated in Sec-Traffic Manager, the traffic is automatically redirected to Sec-Traffic Manager.

    **Note:** Automatic traffic redirection is achieved based on the CNAME address. Therefore, you must use the CNAME record.


