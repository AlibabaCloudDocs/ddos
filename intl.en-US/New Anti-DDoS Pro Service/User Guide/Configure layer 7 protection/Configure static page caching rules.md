# Configure static page caching rules {#task_727366 .task}

Integrated with Web caching techniques, Anti-DDoS Pro provides a scrubbing center that protects your website from DDoS attacks and also reduces page loading time.

Before you enable the static page caching feature, make sure that your domain is associated with an Anti-DDoS Pro instance of the enhanced package.

You can use the static page caching feature to speed up your website and configure custom rules to reduce the loading time of specific pages.

1.  Log on to the [new Anti-DDoS Pro console](https://partners-yundun.console.aliyun.com/?p=ddoscoo&__consolePageCode=ddoscoo).
2.  In the left-side navigation pane, choose **Protection** \> **Protection Settings** \> **Web Acceleration Policies**.
3.  Select a domain and click the Status toggle to enable Static Page Caching for the selected domain.
4.  Select the cache mode. 

    -   **Standard**: This mode will only cache requests that access static resources on the website, such as CSS, JS, and TXT files.
    -   **Enhanced**: This mode will try to cache all requests to the website.
    -   **No Cache**: This mode will not cache any request to the website.
    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/583052/156747934349578_en-US.png)

5.  Click **Change Settings** to configure custom rules for specific pages on the website. 
    1.  Click **Create Rule**.
    2.  In the **Create Rule** dialog box, specify the URI of the page to be cached, select the cache mode, and specify the time when the cache expires. 

        **Note:** Do not enter parameters or wildcard characters in the URI field. For example, /a/ indicates all pages under path `www.a.com/a/`.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/583052/156747934349577_en-US.png)


