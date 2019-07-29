# Accelerate access to a static page {#task_727366 .task}

In addition to protection against DDoS attacks, Anti-DDoS Premium integrates the Web caching technology with its scrubbing center to provide a static page caching feature for access to your website.

Before enabling the static page caching feature, make sure that your website domain has been associated with an Anti-DDoS Premium instance that has the enhanced function plan.

You can use the static page caching feature to accelerate the access to your website domain that has been associated with Anti-DDoS Premium. You can also create custom rules to set caching policies for specified pages linked to the website domain.

1.  Log on to the [Anti-DDoS Premium console](https://yundun.console.aliyun.com/?p=ddosdip).
2.  In the left-side navigation pane, choose **Mitigation Settings** \> **Web Acceleration Policies**.
3.  Select the domain for which you want to configure the static page caching feature. Turn on Static Page Caching.
4.  Select a static page caching mode. 

    -   **Standard:** Only requests to access static files \(.css, .js, and .txt\) of the website domain are cached.
    -   **Enhanced:** All requests to access the website domain are cached.
    -   **No Cache:** No requests to access the website domain are cached.
    ![](../DNDDOSBASIC18101206/images/49578_en-US.png)

5.  Click **Change Settings** to create custom rules for specified pages linked to the website domain. 
    1.  Click **Add Rule**.
    2.  In the **Add Rule** dialog box that appears, enter the URI of the specified page, select a cache mode, and set the validity period of the page cache. 

        **Note:** When setting a page caching rule, no parameters are required for URIs. However, the URI cannot contain wildcards. For example, when you enter /a/, all pages in the `www.a.com/a/` path are specified.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/583052/156436752149577_en-US.png)


