# Add a website

Anti-DDoS Pro and Anti-DDoS Premium protect a website only after you add the website to Anti-DDoS Pro or Anti-DDoS Premium and complete forwarding settings. You can add more than one website at a time. This topic describes how to add a website and how to import the configurations of more than one website to Anti-DDoS Pro or Anti-DDoS Premium at a time.

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

5.  Configure the **Add Domain** wizard.

    1.  Enter site information. Configure the parameters and click **Add**.

        ![Website configurations](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/4561757061/p45722.png)

        |Parameter|Applicable instance type|Description|
        |---------|------------------------|-----------|
        |**Function Plan**|Anti-DDoS Pro and Anti-DDoS Premium|The function plan of the Anti-DDoS Pro or Anti-DDoS Premium instance that you want to use. Valid values: **Standard** and **Enhanced**.You can move the pointer over the ![Function plan description](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/5561757061/p185233.png) icon next to **Function Plan** to view the differences between Standard and Enhanced function plans.

![Function plan](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/5561757061/p185869.png) |
        |**Instance**|Anti-DDoS Pro and Anti-DDoS Premium|The Anti-DDoS Pro or Anti-DDoS Premium instance that you want to use. You can associate a maximum of eight instances with a domain name. The instances associated with the domain name must have the same function plan.Available instances appear after you configure **Function Plan**. If no instances appear, no instances use the function plan that you select. In this case, you can purchase an instance or upgrade the Standard function plan to the Enhanced function plan. For more information, see [Upgrade the specifications of an Anti-DDoS Pro or Anti-DDoS Premium instance](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Resource management/Upgrade the specifications of an Anti-DDoS Pro or Anti-DDoS Premium instance.md). |
        |**Domain**|Anti-DDoS Pro and Anti-DDoS Premium|The domain name of the website that you want to protect. The domain name must meet the following requirements:        -   It can contain letters, digits, and hyphens \(-\). It must start with a letter or a digit.
        -   It can be a wildcard domain name, such as `*.aliyun.com`. If you enter a wildcard domain name, Anti-DDoS Pro or Anti-DDoS Premium protects all subdomains of the wildcard domain name.
        -   If you configure a wildcard domain name and an exact domain name, the forwarding rules and protection policies of the exact match domain take precedence. For example, if you configure `*.aliyun.com` and `www.aliyun.com`, the forwarding rules and protection policies of `www.aliyun.com` take precedence. |
        |**Protocol**|Anti-DDoS Pro and Anti-DDoS Premium|The type of the protocol that the website uses. Valid values:        -   **HTTP**: By default, this protocol is selected.
        -   **HTTPS**: By default, this protocol is selected. If the website uses HTTPS, you must select HTTPS and upload an HTTPS certificate file after you save the website configurations. For more information, see [Upload an HTTPS certificate](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Use domains/Upload an HTTPS certificate.md).
        -   **Websocket**
        -   **Websockets**
If you select **HTTPS**, you can click **Advanced Settings** to display the following options.

![Advanced settings](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/5561757061/p185236.png)

        -   **Enforce HTTPS Routing**: If the website supports both HTTP and HTTPS, this feature is available. If you enable this feature, all HTTP requests to access the website are redirected to HTTPS requests on the standard port 443.

**Note:**

            -   You must select **HTTP** before you enable the feature.
            -   If you select **Websocket**, this feature is unavailable.
            -   If you access the website over HTTP on a non-standard port and enable this feature, all HTTP requests are redirected to HTTPS requests on the standard port 443.
        -   **Enable HTTP**: If the website does not support HTTPS, this feature is available. If this feature is enabled, all HTTPS requests are redirected to HTTP requests and forwarded to origin servers. This feature can redirect WebSockets requests to WebSocket requests. Requests are redirected over the standard port 80.

**Note:**

            -   If the website does not support HTTPS, turn on Enable HTTP.
            -   If you access the website over HTTPS on a non-standard port and enable this feature, all HTTPS requests are redirected to HTTP requests on the standard port 80.
        -   **Enable HTTP/2**: After you turn on the switch, the protocol type is HTTP/2. |
        |**Server IP**|Anti-DDoS Pro and Anti-DDoS Premium|The address type of the origin server. You must enter the address of the origin server. The following types are supported:        -   **Origin Server IP**: the IP address of the origin server. You can enter a maximum of 20 IP addresses. If you enter more than one IP address, separate them with commas \(,\).

For example, if the origin server is hosted on an Elastic Compute Service \(ECS\) instance, enter the public IP address of the instance. If the ECS instance is associated with a Server Load Balancer \(SLB\) instance, enter the public IP address of the SLB instance. If your origin server is not deployed on Alibaba Cloud, enter the public IP address that you obtain when you ping the domain name.

        -   **Origin Server Domain**: Select this option when you deploy a proxy service, such as Web Application Firewall \(WAF\), between the origin server and Anti-DDoS Pro or Anti-DDoS Premium. You must also enter the address of the proxy, such as a CNAME. You can enter a maximum of 10 domain names. If you enter more than one domain name, separate them with line breaks.

For example, if you want to use Anti-DDoS Pro or Anti-DDoS Premium together with WAF, select **Origin Server Domain** and enter the CNAME that WAF assigns. This provides enhanced protection for the website. For more information, see [Deploy WAF and Anti-DDoS Pro together](/intl.en-US/Website Access/Connect cloud services to WAF/Deploy WAF and Anti-DDoS Pro together.md).

If you enter more than one IP address or domain name, Anti-DDoS Pro or Anti-DDoS Premium uses IP hash load balancing to forward website traffic to the origin servers. After you save the website configurations, you can modify the load balancing algorithm. For more information, see [Back to the origin settings](#li_w9r_2nf_ha2) in this topic. |
        |**Server Port**|Anti-DDoS Pro and Anti-DDoS Premium|The server port that you specify based on the selected protocol. **Note:** The forwarding port must be the same as the port of the origin server.

        -   By default, if you select **HTTP** or **Websocket**, the standard port 80 is used.
        -   By default, if you select **HTTPS** or **Websockets**, the standard port 443 is used.

**Note:** HTTP/2 uses the same port as HTTPS.

To add custom ports, you can click **Custom** and enter ports other than the default ports. To view the ports that you can enter, click View optional range.

        -   Instances that use the Standard function plan support HTTP or WebSocket ports 80 and 8080, and HTTPS or WebSockets ports 443 and 8443.
        -   Instances that use the Enhanced function plan support specific non-standard ports, in addition to the standard HTTP port 80 and HTTPS port 443. For more information, see [Specify non-standard ports for protection](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Use domains/Specify non-standard ports for protection.md).
![Custom ports](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/5561757061/p45782.png) |
        |**Cname Reuse**|Anti-DDoS Premium|Specifies whether to enable CNAME reuse. If more than one website is hosted on the same server, this feature is available. After CNAME reuse is enabled, you need only to map the domain names hosted on the same server to the CNAME that is assigned by Anti-DDoS Premium. For more information, see [Use the CNAME reuse feature](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Use domains/Use the CNAME reuse feature.md).|

    2.  Complete the subsequent operations as instructed.

        **Note:** To enable Anti-DDoS Pro or Anti-DDoS Premium to protect the website, you must complete the subsequent operations. For more information, see [What to do next](#section_ev2_z1a_fip).

        ![Complete configurations](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/5561757061/p185271.png)

    3.  Click **Websites List** to view the domain name that you added and the CNAME that is assigned by Anti-DDoS Pro or Anti-DDoS Premium in the website list.

    After you complete the **Add Domain** wizard, you can perform the following operations on the **Website Config** page:

    ![CNAME](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9658121161/p45725.png)

    -   Remarks: Click the ![Pencil icon](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/0565712161/p226624.png) icon next to **Remark** to add remarks that help identify the website configurations.
    -   **Edit** or **Delete**: Modify or delete the website configurations that you added.

        **Note:** You can click Edit in the Actions column. On the page that appears, you can turn on Getting source port from the real customer to obtain the actual source ports of clients. You can mark the back-to-origin requests that Anti-DDoS Pro or Anti-DDoS Premium forwards to the origin server by using custom HTTP headers. For more information, see [Mark back-to-origin requests](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Use domains/Mark back-to-origin requests.md).

    -   **Configure DNS Settings**: If you purchase a paid edition of Alibaba Cloud DNS, you can enable NS Access Mode. This way, the system automatically changes the DNS record of the domain name and redirects traffic to Anti-DDoS Pro or Anti-DDoS Premium. For more information, see [Enable NS Mode Access to protect a website](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Provisioning settings/Enable NS Mode Access to protect a website.md).
    -   **Mitigation Settings**: Click the **Protection for Website Services** tab and modify the feature settings.

        After you add the website, **Intelligent Protection** and **Frequency Control** are enabled by default. You can enable more features and modify protection rules for the website on the **Protection for Website Services** tab. For more information, see [Configure intelligent protection](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Protection settings/Protection for website services/Configure intelligent protection.md).

    -   **Back to the origin settings**: If the website that you add to Anti-DDoS Pro or Anti-DDoS Premium resides on more than one origin server, you can modify the load balancing algorithm for back-to-origin traffic. The following load balancing algorithms are supported:

        -   **IP hash**: redirects requests from the same IP address to the same origin server by using a hashing algorithm. This is the default algorithm.
        -   **Round Robin**: redirects requests to each of the origin servers in turn. If you use this algorithm, you can specify a weight for each server based on server performance.

            Valid values: **1** to **100**. Default value: **100**. A server with a higher weight receives more requests.

        -   **Least time**: uses the intelligent DNS resolution feature to minimize the latency when requests are forwarded from Anti-DDoS Pro or Anti-DDoS Premium instances to origin servers.
        ![Back-to-origin settings](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/5561757061/p185289.png)


## What to do next

After you add the website, you must perform the following operations to enable Anti-DDoS Pro or Anti-DDoS Premium to protect the website.

-   If HTTPS services are connected to Anti-DDoS Pro or Anti-DDoS Premium, you must upload an HTTPS certificate file. This way, HTTPS requests can be redirected to Anti-DDoS Pro or Anti-DDoS Premium for protection. For more information, see [Upload an HTTPS certificate](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Use domains/Upload an HTTPS certificate.md).

    **Note:** If a website is associated with an Anti-DDoS Pro or Anti-DDoS Premium instance that uses the Enhanced function plan, you can customize a TLS security policy for the website after you upload an HTTPS certificate file. For more information, see [Create a custom TLS policy](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Use domains/Create a custom TLS policy.md).

-   If security software, such as a firewall, is installed on the origin server, you must add the back-to-origin IP addresses of the Anti-DDoS Pro or Anti-DDoS Premium instance to the whitelist of the origin server. This ensures that the traffic from Anti-DDoS Pro or Anti-DDoS Premium is not blocked by security software on your origin server. For more information, see [Allow back-to-origin IP addresses to access the origin server](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Allow back-to-origin IP addresses to access the origin server.md).
-   If your origin server is an Alibaba Cloud ECS instance and the IP address of the ECS instance is exposed, you must change the public IP address of the ECS instance. This prevents attackers from bypassing Anti-DDoS Pro or Anti-DDoS Premium to attack your origin server. For more information, see [Change the public IP address of an ECS origin server](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Change the public IP address of an ECS origin server.md).
-   Verify that the website configurations that you added to Anti-DDoS Pro or Anti-DDoS Premium take effect on your computer. If you change the DNS record before the configurations for the website take effect, services may be interrupted. For more information, see [Verify the forwarding configuration on your local machine](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Use domains/Verify the forwarding configuration on your local machine.md).
-   Anti-DDoS Pro or Anti-DDoS Premium assigns a CNAME to the website that you added. You must change the DNS record to map the domain name to the CNAME. You can manually change the DNS record or use the NS Access Mode feature to enable the system to automatically change the DNS record. For more information, see the following topics:
    -   [Manually change the DNS record](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Provisioning settings/Change DNS records to protect website services.md)
    -   [Enable NS Mode Access to protect a website](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Provisioning settings/Enable NS Mode Access to protect a website.md)
-   After you add the website, **Intelligent Protection** and **Frequency Control** are enabled by default. You can enable more features and modify protection rules for the website on the **Protection for Website Services** tab. For more information, see [Configure intelligent protection](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Protection settings/Protection for website services/Configure intelligent protection.md).

## Import the configurations of more than one website at a time

1.  Log on to the [Anti-DDoS Pro console](https://yundun.console.aliyun.com/?p=ddoscoo).

2.  In the top navigation bar, select the region where your instance resides.

    -   **Mainland China**: If you select this region, the **Anti-DDoS Pro console** appears.
    -   **Outside Mainland China**: If you select this region, the **Anti-DDoS Premium console** appears.
    You can switch the region to configure and manage Anti-DDoS Pro or Anti-DDoS Premium instances. Make sure that you select the required region when you use Anti-DDoS Pro or Anti-DDoS Premium.

3.  In the left-side navigation pane, choose **Provisioning** \> **Website Config**.

4.  On the **Website Config** page, click **Batch Domains Import**.

5.  In the **Add Multiple Rules** panel, enter the information of the websites that you want to add and click **Next**.

    You can edit the information about the websites that you want to add in an XML file and copy the content into the field. For more information about the format of the file, see [Website configurations in an XML file](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Use domains/Website configurations in an XML file.md).

    ![Add Multiple Rules panel](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/8987449951/p67782.png)

    If the content of the XML file is valid, the file is parsed into the configurations of the websites that you want to add.

6.  In the **Import Rule** panel, select the websites that you want to add and click **OK**.

    ![Import Rule panel](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/0097449951/p67789.png)

7.  After the configurations are imported, close the **The rules have been created** panel.


