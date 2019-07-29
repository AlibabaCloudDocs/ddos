# Configure the blacklist and whitelist {#concept_72218_zh .concept}

Anti-DDoS Premium allows you to configure a blacklist and whitelist to control access to your website domain.

-   If you have configured a whitelist for a website domain, access requests from IP addresses or IP address ranges that are included in the whitelist are directly allowed without further inspection.
-   If you have configured a blacklist for a website domain, access requests from IP addresses or IP address ranges that are included in the blacklist are directly blocked.

**Note:** The whiltelist and blacklist apply to an individual domain, not all domains associated with the Anti-DDoS Premium instance. For each domain, you can add up to 200 entries to the blacklist and whitelist, respectively. You can enter either IP addresses or IP address ranges to the blacklist and whitelist.

To block IP addresses that send large numbers of malicious requests to your server, you can add them to the blacklist. Meanwhile, you can add IP address ranges of intranet, business interface IP addresses, and verified IP addresses to the whitelist so that requests from these IP addresses are allowed.

1.  Log on to the [Anti-DDoS Premium console](https://yundun.console.aliyun.com/?p=ddosdip).
2.  In the left-side navigation pane, choose **Provisioning** \> **Website**. On the page that appears, select a domain, and click **Web Mitigation Settings**.
3.  On the **HTTP Flood Protection Policies** tab, click **Change Settings** in the **Blacklist and Whitelist** section.

    **Note:** To configure the blacklist and whitelist, you must enable HTTP Flood Protection.

    -   Click the **Blacklist** tab, enter the IP addresses or IP address ranges that you want to block, and click **OK**.
    -   Click the **Whitelist** tab, enter the IP addresses or IP address ranges that you want to allow access the website domain, and click **OK**.
    **Note:** You can enter up to 200 entries in the blacklist and whitelist, respectively. Each entry can be an IP address or IP address range. Separate multiple entries with commas \(,\).

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79693/156436720236925_en-US.png)


**Note:** 

-   The blacklist and whitelist feature is only available in domain configurations.
-   The blacklist and whitelist take effect immediately after they are configured.

    **Notice:** In some situations, it may take some access traffic and time for the configurations to take effect. If the blacklist and whitelist do not take effect immediately, wait a few minutes.

-   You can add 0.0.0.0/0 to the blacklist to block requests from all IP addresses except the ones listed in the whitelist.
-   After the blacklist and whitelist are configured, they apply to all Anti-DDoS Premium instances that are associated with the specified domain.

