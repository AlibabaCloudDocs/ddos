# Add a website

Anti-DDoS Pro or Anti-DDoS Premium protects a website only after you add the website to Anti-DDoS Pro or Anti-DDoS Premium and complete forwarding settings. You can add more than one website at a time. This topic describes how to add a website and how to import the configurations of more than one website to Anti-DDoS Pro or Anti-DDoS Premium at a time.

An Anti-DDoS Pro or Anti-DDoS Premium instance is purchased. For more information, see [Purchase mitigation plans for Anti-DDoS Pro and Anti-DDoS Premium](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Purchase mitigation plans for Anti-DDoS Pro and Anti-DDoS Premium.md).

## Add a website

1.  Log on to the [Anti-DDoS Pro console](https://yundun.console.aliyun.com/?p=ddoscoo).

2.  In the top navigation bar, select the region where your instance resides.

    -   **Mainland China**: If you select this region, the **Anti-DDoS Pro console** appears.
    -   **Outside Mainland China**: If you select this region, the **Anti-DDoS Premium console** appears.
    You can switch the region to configure and manage Anti-DDoS Pro or Anti-DDoS Premium instances. Make sure that you select the required region when you use Anti-DDoS Pro or Anti-DDoS Premium.

3.  In the left-side navigation pane, choose **Provisioning** \> **Website Config**.

4.  On the **Website Config** page, click **Add Domain**.

    You can also import the configurations of more than one website at a time. For more information, see [Import the configurations of more than one website at a time](#section_yoj_x9u_7sv).

5.  Complete the **Add Domain** wizard.

    1.  **Enter Site Information**. Configure the following parameters and click **Add**.

        ![Website configurations](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/4561757061/p45722.png)

        |Parameter|Applicable instance type|Description|
        |---------|------------------------|-----------|
        |**Function Plan**|Anti-DDoS Pro and Anti-DDoS Premium|The function plan of the Anti-DDoS Pro or Anti-DDoS Premium instance that you want to use. Valid values: **Standard** and **Enhanced**.You can move the pointer over the ![Function plan description](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/5561757061/p185233.png) icon next to **Function Plan** to view the differences between Standard and Enhanced function plans.

![Function plan](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/5561757061/p185869.png) |
        |**Instance**|Anti-DDoS Pro and Anti-DDoS Premium|The Anti-DDoS Pro or Anti-DDoS Premium instance that you want to use. You can select up to eight instances for a domain name. The instances associated with the domain name must have the same function plan.Available instances appear after you set **Function Plan**. If no instances appear, no instances use the function plan that you select. In this case, you can purchase an instance or upgrade the Standard function plan to the Enhanced function plan. For more information, see [Upgrade the specifications of an Anti-DDoS Pro or Anti-DDoS Premium instance](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Resource management/Upgrade the specifications of an Anti-DDoS Pro or Anti-DDoS Premium instance.md). |
        |**Domain**|Anti-DDoS Pro and Anti-DDoS Premium|The domain name of the website that you want to protect. The domain name must meet the following requirements:        -   It can contain letters, digits, and hyphens \(-\). It must start with a letter or a digit.
        -   It can be a wildcard domain name, such as `*.aliyun.com`. If you enter a wildcard domain name, Anti-DDoS Pro or Anti-DDoS Premium protects all subdomains of the wildcard domain name.
        -   If you configure both a wildcard domain name, such as `*.aliyun.com`, and an exact match domain, such as `www.aliyun.com`, the forwarding rules and protection policies of the exact match domain take precedence. |
        |**Protocol**|Anti-DDoS Pro and Anti-DDoS Premium|The type of the protocol that the website uses. Valid values: **HTTP**, **HTTPS**, **Websocket**, and **Websockets**. By default, HTTP and HTTPS are selected.**Note:** If the website uses HTTPS, you must select **HTTPS**. You must also upload an HTTPS certificate file after you save the website configurations. This way, HTTPS requests can be redirected to Anti-DDoS Pro or Anti-DDoS Premium for protection. For more information, see [Upload an SSL certificate](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Use domains/Upload an SSL certificate.md).

If you select **HTTPS**, you can click **Advanced Settings** to display the following options.

![Advanced settings](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/5561757061/p185236.png)

        -   **Enforce HTTPS Routing**: If the website supports both HTTP and HTTPS, this feature is available. If you enable the feature, all HTTP requests to access the website are redirected to HTTPS requests on the standard port 443.

**Note:**

            -   You must select **HTTP** before you enable the feature.
            -   If you select **Websocket**, this feature is unavailable.
            -   For example, if you access the website over HTTP on a non-standard port and enable this feature, all HTTP requests are redirected to HTTPS requests on the standard port 443.
        -   **Enable HTTP**: If the website does not support HTTPS, this feature is available. If this feature is enabled, all HTTPS requests are redirected to HTTP requests and forwarded to origin servers. The feature can also redirect WebSockets requests to WebSocket requests. All requests are redirected over the standard port 80.

**Note:**

            -   If the website does not support HTTPS, turn on Enable HTTP.
            -   For example, if you access the website over HTTPS on a non-standard port and enable this feature, all HTTPS requests are redirected to HTTP requests on the standard port 80.
        -   **Enable HTTP/2** |
        |**Server IP**|Anti-DDoS Pro and Anti-DDoS Premium|The address type of the origin server. You must enter the address of the origin server. The following types are supported:        -   **Origin Server IP**: the IP address of the origin server.

You can add a maximum of 20 IP addresses. If you enter more than one IP address, Anti-DDoS Pro or Anti-DDoS Premium uses IP Hash load balancing to forward website traffic to the origin servers. After you save the website configurations, you can modify the load balancing algorithm. For more information, see [Back to the origin settings](#li_w9r_2nf_ha2) in this topic.

For example, if the origin server is hosted on an Alibaba Cloud ECS instance, enter the public IP address of the instance. If the ECS instance is associated with an SLB instance, enter the public IP address of the SLB instance. If your origin server is not deployed on Alibaba Cloud, enter the public IP address that you obtain when you ping the domain name.

        -   **Origin Server Domain**: Select this option when you deploy a proxy service, such as WAF, between the origin server and Anti-DDoS Pro or Anti-DDoS Premium. You must also enter the address of the proxy, such as a CNAME.

For example, if you want to use both Anti-DDoS Pro or Anti-DDoS Premium and WAF, select **Origin Server Domain** and enter the CNAME that is assigned by your WAF instance. This provides enhanced protection for the website. For more information, see [Deploy WAF and Anti-DDoS Pro together](/intl.en-US/Website Access/Connect cloud services to WAF/Deploy WAF and Anti-DDoS Pro together.md). |
        |**Server Port**|Anti-DDoS Pro and Anti-DDoS Premium|The server port that you specify based on the selected protocol. **Note:** The forwarding port must be the same as the port of the origin server.

        -   If you select **HTTP** or **Websocket**, port 80 is used by default.
        -   If you select **HTTPS** or **Websockets**, port 443 is used by default.

**Note:** HTTP/2 uses the same port as HTTPS.

To add custom ports, you can click **Custom** and enter ports other than the default ones. To view the ports that you can enter, click View optional range.

        -   Instances that use the Standard function plan support HTTP or WebSocket ports 80 and 8080, and HTTPS or WebSockets ports 443 and 8443.
        -   Instances that use the Enhanced function plan support specific non-standard ports, in addition to standard HTTP port 80 and HTTPS port 443. For more information, see [Specify non-standard ports for protection](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Use domains/Specify non-standard ports for protection.md).
![Customize ports](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/5561757061/p45782.png) |
        |**Cname Reuse**|Anti-DDoS Premium|Specifies whether to enable CNAME reuse. If more than one website is hosted on the same server, this feature is applicable. After CNAME reuse is enabled, you need only to map the domain names hosted on the same server to the CNAME that is assigned by Anti-DDoS Premium. For more information, see [CNAME reuse](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Use domains/CNAME reuse.md).|

    2.  **Complete the configuration**. Follow the system prompts to complete the subsequent operations.

        **Note:** To enable Anti-DDoS Pro or Anti-DDoS Premium to protect the website, you must complete the subsequent operations. For more information, see [What to do next](#section_ev2_z1a_fip).

        ![Complete configuration](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/5561757061/p185271.png)

    3.  Click **Website List** to view the domain name that you added and the CNAME that is assigned by Anti-DDoS Pro or Anti-DDoS Premium in the website list.

    After you complete the **Add Domain** wizard, you can perform the following operations on the **Website Config** page:

    ![CNAME](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/5561757061/p45725.png)

    -   **Edit** or **Delete**: Modify or delete the website configurations that you added. For more information, see [Edit a website configuration](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Use domains/Edit a website configuration.md) and [Delete a website configuration](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Use domains/Delete a website configuration.md).
    -   **Configure DNS Settings**: If you purchase a paid edition of Alibaba Cloud DNS, you can enable NS Access Mode. This way, the system automatically changes the DNS record of the domain name and redirects traffic to Anti-DDoS Pro or Anti-DDoS Premium. For more information, see [Enable NS Mode Access to protect a website](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Provisioning settings/Enable NS Mode Access to protect a website.md).
    -   **Mitigation Settings**: Click the **Protection for Website Services** tab and modify the feature settings.

        After you add the website, **Intelligent protection** and **Frequency Control** are enabled by default. You can enable more features and modify protection rules for the website on the **Protection for Website Services** tab. For more information, see [.](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Protection settings/Protection for website services/Configure intelligent protection.md)

    -   **Back to the origin settings**: If the website that you added to Anti-DDoS Pro or Anti-DDoS Premium resides on more than one origin server, you can modify the load balancing algorithm for back-to-origin traffic. The following load balancing algorithms are supported:

        -   **IP hash**: redirects requests from the same IP address to the same origin server by using a hashing algorithm.
        -   **Round Robin**: redirects requests to the origin servers in turn. If you use this algorithm, you can specify a weight value for each server based on their performance.

            Valid values: **1** to **100**. Default value: **100**. A server with a higher weight value receives more requests.

        -   **Least time**: uses the intelligent DNS resolution feature to minimize the latency between Anti-DDoS Pro or Anti-DDoS Premium instances and origin servers.
        ![Back-to-origin settings](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/5561757061/p185289.png)


## What to do next

After you add the website, you must perform the following operations to enable Anti-DDoS Pro or Anti-DDoS Premium to protect the website.

-   If HTTPS services are connected to Anti-DDoS Pro or Anti-DDoS Premium, you must upload an HTTPS certificate file. This way, HTTPS requests can be redirected to Anti-DDoS Pro or Anti-DDoS Premium for protection. For more information, see [Upload an SSL certificate](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Use domains/Upload an SSL certificate.md).

    **Note:** If a website is associated with an Anti-DDoS Pro or Anti-DDoS Premium instance that uses the Enhanced function plan, you can customize a TLS security policy for the website after you upload an HTTPS certificate file. For more information, see [Create a custom TLS policy](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Use domains/Create a custom TLS policy.md).

-   If security software, such as a firewall, is installed on the origin server, you must add the back-to-origin IP addresses of the Anti-DDoS Pro or Anti-DDoS Premium instance to the whitelist of the origin server. This ensures that the traffic from Anti-DDoS Pro or Anti-DDoS Premium is not blocked by the security software on your origin server. For more information, see [Allow back-to-origin IP addresses to access the origin server](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Allow back-to-origin IP addresses to access the origin server.md).
-   If your origin server is an Alibaba Cloud ECS instance and the IP address of the ECS instance is exposed, you must change the public IP address of the ECS instance to prevent attackers from bypassing Anti-DDoS Pro or Anti-DDoS Premium to attack your origin server. For more information, see [Change the public IP address of an ECS origin server](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Change the public IP address of an ECS origin server.md).
-   Verify that the website configurations that you added to Anti-DDoS Pro or Anti-DDoS Premium are in effect on your computer. If you change the DNS record before the configurations for the website take effect, service interruptions may occur. For more information, see [Verify the forwarding configuration on your local machine](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Use domains/Verify the forwarding configuration on your local machine.md).
-   Anti-DDoS Pro or Anti-DDoS Premium assigns a CNAME to the website that you added. You must change the DNS record to map the domain name to the CNAME. You can manually change the DNS record or use the NS Access Mode feature to enable the system to automatically change the DNS record. For more information, see the following topics:
    -   [Manually change the DNS record](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Provisioning settings/Modify DNS records to protect websites.md)
    -   [Enable NS Mode Access to protect a website](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Provisioning settings/Enable NS Mode Access to protect a website.md)
-   After you add the website, **Intelligent protection** and **Frequency Control** are enabled by default. You can enable more features and modify protection rules for the website on the **Protection for Website Services** tab. For more information, see [Configure intelligent protection](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Protection settings/Protection for website services/Configure intelligent protection.md).

## Import the configurations of more than one website at a time

1.  Log on to the [Anti-DDoS Pro console](https://yundun.console.aliyun.com/?p=ddoscoo).

2.  In the top navigation bar, select the region where your instance resides.

    -   **Mainland China**: If you select this region, the **Anti-DDoS Pro console** appears.
    -   **Outside Mainland China**: If you select this region, the **Anti-DDoS Premium console** appears.
    You can switch the region to configure and manage Anti-DDoS Pro or Anti-DDoS Premium instances. Make sure that you select the required region when you use Anti-DDoS Pro or Anti-DDoS Premium.

3.  In the left-side navigation pane, choose **Provisioning** \> **Website Config**.

4.  On the **Website Config** page, click **Batch Domains Import**.

5.  In the **Add Multiple Rules** panel, enter the information of the websites that you want to add and click **Next**.

    You can edit the information of the websites that you want to add in an XML file and then copy the content into the field. For more information about the format of the file, see [Website configurations in an XML file](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Use domains/Website configurations in an XML file.md).

    ![Add Multiple Rules panel](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/8987449951/p67782.png)

    If the content of the XML file is valid, the file is parsed into the configurations of the websites that you want to add.

6.  In the **Import Rule** panel, select the websites that you want to add and click **OK**.

    ![Import Rule panel](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/0097449951/p67789.png)

7.  After the configurations are imported, close the **The rules have been created** panel.


