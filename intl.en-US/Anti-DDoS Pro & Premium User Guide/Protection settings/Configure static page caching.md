# Configure static page caching

Anti-DDoS Pro and Anti-DDoS Premium provide scrubbing centers that are integrated with web caching techniques to protect your website services against DDoS attacks and reduce page load time.

Your website is added to an Anti-DDoS Pro or Anti-DDoS Premium instance that uses the Enhanced function plan. For more information, see [Add a website](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Use domains/Add a website.md).

After your website is added to an Anti-DDoS Pro or Anti-DDoS Premium instance, you can enable the static page caching feature for the website. After the feature is enabled, the Anti-DDoS Pro or Anti-DDoS Premium instance automatically detects whether the web pages that a client requests contain the resource types that are defined in the caching policy. If the web pages contain the resource types that are defined in the caching policy, the web pages are cached. The next time the client requests the same page, the Anti-DDoS Pro or Anti-DDoS Premium instance directly returns the pages. This accelerates client access.

You can customize caching rules for a specific page.

1.  Log on to the [Anti-DDoS Pro console](https://yundun.console.aliyun.com/?p=ddoscoo).

2.  In the top navigation bar, select the region where your instance resides.

    -   **Mainland China**: If you select this region, the **Anti-DDoS Pro console** appears.
    -   **Outside Mainland China**: If you select this region, the **Anti-DDoS Premium console** appears.
    You can switch the region to configure and manage Anti-DDoS Pro or Anti-DDoS Premium instances. Make sure that you select the required region when you use Anti-DDoS Pro or Anti-DDoS Premium.

3.  In the left-side navigation pane, choose **Anti-DDoS Lab** \> **Website Acceleration**.

4.  In the upper part of the page that appears, select the required domain name.

    **Note:** You can enable the static page caching feature only for the domain names that are associated with an Anti-DDoS Pro or Anti-DDoS Premium instance that uses the Enhanced function plan.

5.  In the **Static Page Caching** section, configure the **Mode** parameter and turn on **Status**.

    Valid values of the Mode parameter:

    -   **Standard**: If the requested page contains static resources such as CSS, JavaScript, or TXT files, the page is cached.
    -   **Enhanced**: All requested pages are cached.
    -   **No Cache**: No requested pages are cached.
    ![Static Page Caching](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/4397449951/p49578.png)

    After you enable the static page caching feature for the domain name, the caching policy takes effect on all URIs in the domain name.

    If you want to enable the static page caching feature for only a specific URI, we recommend that you set the **Mode** parameter to **No Cache** and perform the following steps to configure a custom caching rule.

6.  Configure a custom caching rule for a specific URI.

    1.  In the **Static Page Caching** section, click **Change Settings**.

    2.  Click **Create Rule**.

        **Note:** You can create a maximum of three custom caching rules.

        ![Create Rule ](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/7392712161/p73065.png)

    3.  In the **Create Rule** dialog box, configure the parameters and click **OK**.

        ![Create Rule](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/4397449951/p49577.png)

        |Parameter|Description|
        |---------|-----------|
        |**Name**|The name of the caching rule. The name can contain letters, digits, and underscores \(\_\). The name can be up to 128 characters in length. |
        |**URI**|The URI of the page to be cached. Request parameters and wildcards are not allowed in the **URI** field.

For example, `/a/` represents all pages in the path `<Domain name>/a/`. |
        |**Mode**|The mode for the caching policy. Valid values: **Standard**, **Enhanced**, and **No Cache**. For more information about these values, see [Step 5](#step_pls_iu0_06r). |
        |**Cache Expires In**|The validity period of the cached resources. Default value: **Use Origin Server Settings**. This value indicates that the validity period of the cached resources configured for the origin server is used. You can also select **1Hour\(s\)**, **1 Days**, **10 Days**, or **30 Days**.|

        After you create the custom caching rule for the specific URI, the custom caching rule preferentially takes effect over the caching policy of the domain name. You can view created rules and click **Modify** or **Delete** to manage the rules in the rule list. You can also click **Clear Cache** to manually refresh the cache of the page.


