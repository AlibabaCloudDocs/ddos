# Best practices to add a service to Anti-DDoS Pro or Anti-DDoS Premium

After you add a service to Anti-DDoS Pro or Anti-DDoS Premium, your service traffic is redirected to Anti-DDoS Pro or Anti-DDoS Premium to ensure stability and reliability of the origin server. This avoids service unavailability when volumetric DDoS attacks occur. This topic provides best practices to add a service to Anti-DDoS Pro or Anti-DDoS Premium and configure protection policies in various scenarios.

## Scenarios to add a service to Anti-DDoS Pro or Anti-DDoS Premium

|Scenario|Configuration process|
|--------|---------------------|
|**Normal service configuration**|1.  [Analyze the service](#section_mwf_hnc_evm)
2.  [Prepare for the configuration](#section_5mo_8ni_zu6)
3.  [Add the service to Anti-DDoS Pro or Anti-DDoS Premium and configure protection policies](#section_1o4_2ds_nrh) |
|**Emergency configuration when the service is under attack**|Read [Emergency scenarios to add a service](#section_48q_22g_ldd) and then add your service based on the process for normal service configuration.|

## Step 1: Analyze the service

Before you add a service to Anti-DDoS Pro or Anti-DDoS Premium, we recommend that you analyze the service status and data.

|Item|Description|Suggestion|
|----|-----------|----------|
|**Website and service information**|
|Daily peak traffic of the website or application, such as bandwidth \(Mbit/s\) and QPS|Determine the point in time of risks.|This information is required to configure the service bandwidth and QPS of the Anti-DDoS Pro or Anti-DDoS Premium instance.|
|Major user groups, for example, the geographical locations of users|Determine attack sources.|This information is required to configure blocked regions. For more information, see [Configure blocked regions for domain names](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Protection settings/Protection for website services/Configure blocked regions for domain names.md).|
|Whether the service is deployed in the C/S architecture|If the C/S architecture is used, determine whether app clients, Windows clients, Linux clients, clients for other environments, or client callback is deployed.|None.|
|Whether the origin server is deployed in regions outside mainland China|Determine whether the Anti-DDoS Pro or Anti-DDoS Premium instance is suitable for your network architecture.|If the origin server is deployed outside mainland China, we recommend that you use Anti-DDoS Premium. For more information, see [What are Anti-DDoS Pro and Anti-DDoS Premium?](/intl.en-US/Product Introduction on Alibaba DDoS Protection/What are Anti-DDoS Pro and Anti-DDoS Premium?.md).|
|Operating system of the origin server \(Linux or Windows\) and web service middleware \(such as Apache, NGINX, and IIS\)|Determine whether access control policies are configured for the origin server. The policies may block traffic from the back-to-origin IP addresses of Anti-DDoS Pro or Anti-DDoS Premium.|If access control policies are configured, you must allow the back-to-origin IP addresses to access the origin server. For more information, see [Allow back-to-origin IP addresses to access the origin server](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Allow back-to-origin IP addresses to access the origin server.md).|
|Whether the service needs to support IPv6|None.|If your service needs to support IPv6, we recommend that you use Anti-DDoS Origin. For more information, see [What is Anti-DDoS Origin](/intl.en-US/Product Introduction on Alibaba DDoS Protection/Anti-DDoS Origin/What is Anti-DDoS Origin.md).|
|Protocol used by the service|None.|This information is required to select a protocol for your website in Anti-DDoS Pro or Anti-DDoS Premium.|
|Service ports|None.|Determine whether service ports of the origin server are supported by Anti-DDoS Pro or Anti-DDoS Premium. For more information, see [Specify non-standard ports for protection](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Use domains/Specify non-standard ports for protection.md).|
|Whether the HTTP request header contains custom fields and whether the origin server provides a verification mechanism|Determine whether Anti-DDoS Pro or Anti-DDoS Premium affects the custom fields and causes verification failures on the origin server.|If yes, [submit a ticket](https://workorder-intl.console.aliyun.com/?#/ticket/add/?productId=80) to obtain technical support.|
|Whether the origin server needs to obtain and verify the actual source IP addresses of requests|After you add the service to Anti-DDoS Pro or Anti-DDoS Premium, the actual source IP addresses of requests are changed. You must determine whether the origin server needs to obtain the actual source IP addresses to avoid service interruptions.|For more information, see [Obtain the actual source IP addresses of requests](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Best practices/Obtain the actual source IP addresses of requests.md).|
|Whether the service uses TLS 1.0 or a weak cipher suite|Determine whether the cipher suite of your service is supported.|After the service is added, you must configure TLS policies. For more information, see [Create a custom TLS policy](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Use domains/Create a custom TLS policy.md).|
|\(For HTTPS websites\) Whether the origin server uses mutual authentication|None.|Anti-DDoS Pro and Anti-DDoS Premium do not support mutual authentication. You must change the authentication method.|
|\(For HTTPS websites\) Whether the clients support SNI|None.|After you add a domain name of an HTTPS website to Anti-DDoS Pro or Anti-DDoS Premium, both the clients and servers must support SNI.|
|\(For HTTPS websites\) Whether session persistence is enabled|The default connection timeout period for HTTP and HTTPS is 120 seconds.|If your service requires persistent sessions in scenarios such as file uploading and user logon, we recommend that you use cookies to implement session persistence at Layer 7.|
|Whether the service requires transmission of empty data packets|For example, the server sends empty packets to prevent session interruption. After you add the service to Anti-DDoS Pro or Anti-DDoS Premium, the service may be affected.|If yes, [submit a ticket](https://workorder-intl.console.aliyun.com/?#/ticket/add/?productId=80) to obtain technical support.|
|Service interaction process|Determine the service interaction process and processing logic to configure suitable protection policies.|None.|
|Number of active users|Determine the severity of emergent attack events and take low-risk countermeasures.|None.|
|**Service and attack information**|
|The type and characteristics of your service \(for example, whether it is a gaming, website, or app service\)|Analyze attack characteristics to take countermeasures.|None.|
|The volume of inbound service traffic|Determine whether there is malicious traffic. For example, the average volume of daily access traffic is 100 Mbit/s. If the traffic volume exceeds 100 Mbit/s, an attack may have occurred.|None.|
|The volume of outbound service traffic|Determine whether attacks occur and whether to increase service bandwidth.|None.|
|The volume and connections of inbound traffic for individual users or IP addresses|Determine whether throttling policies can be configured for individual IP addresses.|For more information, see [Configure frequency control](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Protection settings/Protection for website services/Configure frequency control.md).|
|User sources|For example, users may visit your service from household LANs, Internet cafes, and proxy servers.|This information is required to determine whether concurrent requests are sent from a single egress IP address and prevent Anti-DDoS Pro or Anti-DDoS Premium from blocking normal service traffic.|
|Whether the service has suffered volumetric attacks and the types of the attacks|Configure targeted DDoS protection policies based on the types of historical attacks.|None.|
|The largest traffic volume of attacks suffered by the service|Select the specifications of the Anti-DDoS Pro or Anti-DDoS Premium instance based on the peak attack traffic.|For more information, see [Purchase mitigation plans for Anti-DDoS Pro and Anti-DDoS Premium](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Purchase mitigation plans for Anti-DDoS Pro and Anti-DDoS Premium.md).|
|Whether the service has suffered HTTP flood attacks|Configure preventive policies based on characteristics of historical attacks.|None.|
|The largest QPS of HTTP flood attacks suffered by the service|Configure preventive policies based on characteristics of historical attacks.|None.|
|Whether the service provides web APIs|None.|If web APIs are provided, we recommend that you do not use the frequency control feature of Anti-DDoS Pro or Anti-DDoS Premium. You can analyze API access characteristics and configure protection policies against HTTP flood attacks. This prevents normal API requests from being blocked.|
|Whether a stress test is performed for the service|Evaluate the request processing performance of the origin server and determine whether service exceptions are caused by attacks.|None.|

## Step 2: Prepare for the configuration

**Note:** We recommend that you add a service to Anti-DDoS Pro or Anti-DDoS Premium in a test environment first. After you verify that the service properly runs, perform the configuration in the production environment.

Before you add a service to Anti-DDoS Pro or Anti-DDoS Premium, make the following preparations.

|Service type|Preparation|
|------------|-----------|
|Website service|-   Prepare information of the website that you want to add, including the domain names, public IP address of the origin server, and service ports.
-   Compete ICP filing for the domain names.
-   If the website supports HTTPS, prepare the certificate and private key, including a public key file in the .crt format or certificate file in the .pem format and a private key in the .key format.
-   Obtain an administrator account of the DNS service. This account is used to modify DNS records to redirect traffic to Anti-DDoS Pro or Anti-DDoS Premium.
-   Perform a stress test before you add the website to Anti-DDoS Pro or Anti-DDoS Premium.
-   List trusted clients of the website, such as the monitoring system, APIs that are called by using a fixed IP address or CIDR block, and specific client programs. After you add the website to Anti-DDoS Pro or Anti-DDoS Premium, you must add the IP addresses of these clients to a whitelist. |
|Non-website service|-   Obtain the service port and protocol.
-   If the service is provided by using a domain name, obtain an administrator account that can change DNS records to redirect service traffic to Anti-DDoS Pro or Anti-DDoS Premium.
-   Perform a stress test before you add the service to Anti-DDoS Pro or Anti-DDoS Premium. |

## Step 3: Add the service to Anti-DDoS Pro or Anti-DDoS Premium and configure protection policies

1.  Add the service to Anti-DDoS Pro or Anti-DDoS Premium.

    **Note:** If the service is already under attack before you add it to Anti-DDoS Pro or Anti-DDoS Premium, we recommend that you change the IP address of the origin server. Before you change the IP address, check whether the code of the client or app contains the IP address. If yes, update the code before you change the IP address to avoid impacts on normal service access. For more information, see [Change the public IP address of an ECS origin server](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Change the public IP address of an ECS origin server.md).

    Add the service based on the Anti-DDoS Pro or Anti-DDoS Premium instance and your service scenario:

    -   [Add a website service to Anti-DDoS Pro or Anti-DDoS Premium](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Use domains/Add a website.md)
    -   [Add a non-website service to Anti-DDoS Pro or Anti-DDoS Premium](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Use ports/Create forwarding rules.md)
    -   [Add a website service to Anti-DDoS Pro or Anti-DDoS Premium by using NS records](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Provisioning settings/Enable NS Mode Access to protect a website.md)
2.  Configure protection for the origin server.

    To prevent attackers from bypassing Anti-DDoS Pro or Anti-DDoS Premium to attack the origin server, configure protection for the origin server. For more information, see [Configure protection for your origin server](/intl.en-US/Website Access/Website access with CNAME/Configure protection for your origin server.md).

3.  Configure protection policies.
    -   Website service provided by using domain names
        -   HTTP flood protection
            -   The service is running properly: Two or three days after you add the service to Anti-DDoS Pro or Anti-DDoS Premium, analyze service application logs, including information about URLs and the average QPS of individual source IP addresses. Based on the analysis, configure frequency control rules. This provides protection against attacks.
            -   The service is suffering from an HTTP flood attack: Go to the **Security Overview** page in the [Anti-DDoS Pro or Anti-DDoS Premium](https://yundun.console.aliyun.com/?p=ddoscoo) console to obtain information about your domain name, such as the most requested URLs and IP addresses, source IP addresses, and user agents. Based on the obtained information, configure frequency control rules and observe the protection effect. For more information, see [Check security overview](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Check security overview.md) and [Create a custom frequency control rule](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Protection settings/Protection for website services/Configure frequency control.md).

                **Note:** The **Emergency** mode of **Frequency Control** may block normal traffic of specific service types. We recommend that you do not set **Emergency** as the default mode of **Frequency Control**. If you provide the app or web API service, do not use the **Emergency** mode.

                If you use the **Normal** mode of **Frequency Control** but normal service traffic is still blocked, add the service IP addresses to a whitelist.

        -   Intelligent protection for a website service

            The **Strict** mode of intelligent protection may block normal service traffic. After you add the domain name of your website to Anti-DDoS Pro or Anti-DDoS Premium, you do not need to be concerned about Layer-4 DDoS attacks. Therefore, we recommend that you use the **Normal** mode instead of the **Strict** mode. For more information, see [Configure intelligent protection](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Protection settings/Protection for website services/Configure intelligent protection.md).

        -   Log analysis

            We recommend that you enable the log analysis feature. For more information, see [Activate Log Analysis](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Query and analysis/Log analysis/Overview.md). If the service encounters Layer-7 DDoS attacks, you can use the log analysis feature to analyze attack characteristics and configure targeted protection policies.

            **Note:** Enabling the log analysis feature incurs additional fees.

    -   **Non-website service provided by using ports**

        In most cases, you can add a non-website service to Anti-DDoS Pro or Anti-DDoS Premium and use the default protection settings. After the service runs for two or three days, you can adjust the mode of Layer-4 intelligent protection based on the service characteristics. This optimizes protection against Layer-4 HTTP flood attacks. For more information, see [Configure intelligent protection](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Protection settings/Protection for non-website services/Configure intelligent protection.md).

        **Note:** If the service provides frequently called APIs or is visited from a single IP address, such as an egress IP address of an enterprise network or a server IP address, do not enable the **Strict** mode of Intelligent Protection. If you have to use the **Strict** mode, contact Alibaba Cloud technical support to analyze the service before you enable this mode to avoid service interruptions.

        If attack traffic is transparently transmitted to the origin server, you can enable Speed Limit for Source and Speed Limit for Destination. For more information, see [Create an anti-DDoS protection policy](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Protection settings/Protection for non-website services/Create an anti-DDoS protection policy.md). At the beginning, we recommend that you set both Source New Connection Rate Limit and Source Concurrent Connection Rate Limit to 5. If normal service traffic is blocked, you can increase the limit values.

        ![Speed Limit for Source](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/6862079951/p42169.png)

        If the origin server of your service sends empty data packets, you must disable Empty Connection to avoid impacts on normal traffic. For more information, see [Create an anti-DDoS protection policy](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Protection settings/Protection for non-website services/Create an anti-DDoS protection policy.md).

        ![Empty Connection](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/6862079951/p133324.png)

4.  Test the service.

    After you complete the configuration, test the accuracy of the configurations.

    **Note:** You can modify the hosts file on a local computer to perform the test.

    |No.|Check item|
    |---|----------|
    |**Website service provided by using a domain name \(required\)**|
    |1|Check whether the added domain name is correct.|
    |2|Check whether the domain name has an ICP license.|
    |3|Check whether the configured protocol is correct.|
    |4|Check whether the configured port is correct.|
    |5|Check whether the IP address of the origin server is correct. Make sure that you do not enter the IP address of the Anti-DDoS Pro or Anti-DDoS Premium instance or another service.|
    |6|Check whether the uploaded certificate is correct.|
    |7|Check whether the certificate is valid. For example, the encryption algorithm may be invalid or you have uploaded the certificate of another domain name.|
    |8|Check whether the certificate chain is complete.|
    |9|Make sure that you know the billing method of burstable protection in Anti-DDoS Pro or Anti-DDoS Premium.|
    |10|Check whether WebSocket and WebSockets are enabled.|
    |11|Check whether the Emergency mode of Frequency Control is enabled.|
    |**Non-website service provided by using a port \(required\)**|
    |1|Check whether the service port can be accessed.|
    |2|Check whether the UDP or TCP protocol is incorrectly configured.|
    |3|Check whether the IP address of the origin server is correct. Make sure that you do not enter the IP address of the Anti-DDoS Pro or Anti-DDoS Premium instance or another service.|
    |4|Make sure that you know the billing method of burstable protection in Anti-DDoS Pro or Anti-DDoS Premium.|
    |5|Check whether the Strict mode of intelligent protection is enabled.|

    |No.|Check item|
    |---|----------|
    |1 \(required\)|Test whether the service can be normally accessed.|
    |2 \(required\)|Test whether the session persistence function for user logon properly works.|
    |3 \(required\)|\(For website services provided by using domain names\) Check the number of 4XX and 5XX status codes in returned responses and make sure that the back-to-origin IP addresses are not blocked.|
    |4 \(required\)|\(For website services provided by using domain names\) If you provide the app service, test whether HTTPS links are normal. Check whether SNI is properly configured.|
    |5 \(recommended\)|Check whether the origin server is configured to obtain the actual source IP addresses of requests.|
    |6 \(recommended\)|\(For website services provided by using domain names\) Check whether protection policies are configured for the origin server. This prevents attackers from bypassing Anti-DDoS Pro or Anti-DDoS Premium to attack the origin server.|
    |7 \(required\)|Test whether the TCP service port is accessible.|

5.  Switch service traffic to Anti-DDoS Pro or Anti-DDoS Premium.

    After you verify all check items, we recommend that you change the DNS records one by one to gradually switch the service traffic to Anti-DDoS Pro or Anti-DDoS Premium. This prevents potential service exceptions in a large scale. If an exception occurs after you switch the traffic, restore the DNS records.

    **Note:** Changes to DNS records take effect in about 10 minutes.

    After you switch the service traffic, verify the check items of service availability again to make sure that the service properly runs.

6.  Configure monitoring and alerts.

    Use Cloud Monitor to monitor availability and returned HTTP status codes \(5XX and 4XX\) for the domain names, forwarding ports, and origin server ports protected by Anti-DDoS Pro or Anti-DDoS Premium. This allows you to detect service exceptions in time. For more information, see [Create an Anti-DDoS alert rule](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Monitoring and alerting/Create an Anti-DDoS alert rule.md).

7.  Perform routine O&M.
    -   **Use burstable protection of Anti-DDoS Pro and advanced mitigation in the Insurance plan of Anti-DDoS Premium.**
        -   If you purchase an Anti-DDoS Pro instance for the first time, you can obtain three global advanced mitigation plans of 300 Gbit/s free of charge. For more information, see [Anti-DDoS packages](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Resource management/Anti-DDoS packages.md). Bind the plans to the Anti-DDoS Pro instance and set the burstable protection threshold to 300 Gbit/s. Anti-DDoS Pro then protects your service against attacks whose traffic volume does not exceed 300 Gbit/s and does not incur burstable protection fees within the day after you bind the plans.

            **Note:** If you do not want to enable burstable protection after the global advanced mitigation plans are used up or expire, change the protection threshold to the basic protection bandwidth of your Anti-DDoS Pro instance.

        -   If you want to enable burstable protection of Anti-DDoS Pro, view the billing methods to determine the costs. For more information, see [Burstable protection \(pay-as-you-go on a daily basis\)](/intl.en-US/Pricing/Anti-DDoS Pro billing methods.md).
        -   If you purchase an Anti-DDoS Premium instance with the Insurance mitigation plan, you can obtain two advanced mitigation plans \(unlimited protection\) each month free of charge. Select the mitigation plan based on your service needs.
    -   **Determine attack types.**

        If HTTP flood attacks and DDoS attacks occur, you can view attack information on the **Security Overview** page in the [Anti-DDoS Pro or Anti-DDoS Premium console](https://yundun.console.aliyun.com/?p=ddoscoo) to determine the types of attacks. For more information, see [Check security overview](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Check security overview.md).

        -   DDoS attack: On the **Instances** tab, the protection reports show attack traffic fluctuations, and traffic scrubbing is triggered. However, on the **Domains** tab, the protection reports do not show fluctuations.
        -   HTTP flood attack: On the **Instances** tab, the protection reports show attack traffic fluctuations, and traffic scrubbing is triggered. On the **Domains** tab, the protection reports also show fluctuations.
        For more information, see [How do I identify the types of attacks against an Anti-DDoS Pro or Anti-DDoS Premium instance?]().

    -   **Deal with service access latency and packet loss.**

        If the origin server is deployed outside mainland China and users of your service come from mainland China, the users may experience large latency and packet loss due to unstable links of cross-carrier network access. We recommend that you purchase an Anti-DDoS Premium instance and use the MCA mitigation plan.

    -   **Delete a domain name or port forwarding rule.**

        If you want to delete a domain name or port forwarding rule, check whether your service traffic is switched to Anti-DDoS Pro or Anti-DDoS Premium.

        -   If no, delete the domain name or port forwarding rule in the [Anti-DDoS Pro or Anti-DDoS Premium console](https://yundun.console.aliyun.com/?p=ddoscoo).
        -   If yes, go to the Alibaba Cloud DNS console to modify the DNS records to switch the traffic back to the origin server. Then, delete the domain name or port forwarding rule.
        **Note:**

        -   Before you delete the domain name or port forwarding rule, make sure that the DNS records or service traffic of the domain name is switched back to the origin server.
        -   After you delete the domain name or port forwarding rule, Anti-DDoS Pro or Anti-DDoS Premium no longer protects your service.

## Emergency scenarios to add a service

If the service is already under attack, add it to Anti-DDoS Pro or Anti-DDoS Premium based on the following scenarios:

-   The service suffers a DDoS attack.

    In most cases, you can add the service to Anti-DDoS Pro or Anti-DDoS Premium and use the default protection settings.

    If traffic of a Layer-4 HTTP flood attack is transparently transmitted to the origin server, you can enable Speed Limit for Source and Speed Limit for Destination. For more information, see [Create an anti-DDoS protection policy](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Protection settings/Protection for non-website services/Create an anti-DDoS protection policy.md).

-   Blackhole filtering is triggered for the IP address of the origin server.

    You can use an ECS or SLB instance as the origin server. If you have not added the attacked service to Anti-DDoS Pro or Anti-DDoS Premium but blackhole filtering is triggered, you must change the public IP address of the origin server. For more information, see [Change ECS IP](/intl.en-US/Anti-DDoS Pro Service (Old)/User Guide/Instance management/Change ECS IP.md). After you change the IP address, add the service to Anti-DDoS Pro or Anti-DDoS Premium as soon as possible to prevent the new IP address from being exposed.

    If you do not want to change the IP address of the origin server or the new IP address is already exposed, we recommend that you deploy an SLB instance as the origin server to connect the ECS instance and add the public IP address of the SLB instance to Anti-DDoS Pro or Anti-DDoS Premium.

    **Note:** If the service is under attack but the origin server is not deployed on Alibaba Cloud, make sure that the domain name of the service has an ICP license and contact technical support to add Alibaba Cloud as your service provider. Then, add the service to Anti-DDoS Pro or Anti-DDoS Premium.

-   The service suffers an HTTP flood attack or crawler attack.

    If the service is under an HTTP flood or crawler attack, add the service to Anti-DDoS Pro or Anti-DDoS Premium. Then, analyze HTTP access logs to identify attack characteristics and configure protection policies. For example, you can check whether request fields, such as the source IP address, URL, Referer, User-Agent, Params, and Header are correct.


