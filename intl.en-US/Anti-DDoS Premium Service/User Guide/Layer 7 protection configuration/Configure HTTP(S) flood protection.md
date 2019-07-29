# Configure HTTP\(S\) flood protection {#concept_72210_zh .concept}

Anti-DDoS Premium provides four protection modes to help you prevent HTTP\(S\) flood attacks.

-   **Normal:** The default HTTP\(S\) flood protection mode. You can use this mode when there are no apparent traffic exceptions to the website.

    This mode prevent typical HTTP\(S\) flood attacks and does not block normal requests.

-   **Emergency:** You can switch to the Emergency mode when you discover exceptions in metrics such as website response, traffic, CPU, and memory usage.

    This mode has relatively strict policies. Compared with the Normal mode, the Emergency mode can prevent more complicated and sophisticated HTTP\(S\) flood attacks. However, it may block some normal requests.

-   **Strict:** This mode uses strict protection policies. The mode implements CAPTCHA verification for all access requests to the protected website. Only verified visitors are allowed to access the website.

    **Note:** With the implementation of global CAPTCHA verification in Strict mode, all requests from real visitors through browsers are responded to normally. However, if the protected website provides API or native application services, requests to the website cannot pass the verification and will fail to access the services provided by the website.

-   **Super Strict:** This mode uses the strictest protection policies. The mode implements CAPTCHA verification for all access requests to the protected website. Only verified visitors are allowed to access the website.

    Compared with the Strict mode, the Super Strict mode combines the global CAPTCHA verification with anti-debugging techniques and anti-machine verification to enhance the protection of your website.

    **Note:** With the implementation of global CAPTCHA verification in Super Strict mode, all requests from real visitors through browsers are responded to normally. Exceptions may occur in some browsers and cause the website to be inaccessible. In this situation, you can restart the browser and revisit the website. However, if the protected website provides API or native application services, requests to the website cannot pass the verification and will fail to access the services provided by the website.


## Procedure {#section_cyy_rj3_kgb .section}

By default, your domain protected by the Anti-DDoS Premium instance uses the Normal HTTP\(S\) flood protection mode. You can adjust the protection mode as needed.

1.  Log on to the [Anti-DDoS Premium console](https://yundun.console.aliyun.com/?p=ddosdip).
2.  In the left-side navigation pane, choose **Provisioning** \> **Website**. On the page that appears, select a domain, and click **Web Mitigation Settings**.
3.  On the **HTTP Flood Protection Policies** tab, select a mode in the **HTTP Flood Protection** section .

    **Note:** You can click Status to disable the HTTP\(S\) flood protection.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79692/156436742036922_en-US.png)


## Custom rules {#section_2ny_mc7_9oj .section}

The HTTP\(S\) flood protection feature also allows you to create custom rules to prevent HTTP\(S\) flood attacks. You can create custom rules for specific URLs.

In the left-side navigation pane, click Mitigation Settings. On the **HTTP Flood Protection Policies** page that appears, turn on Custom Rule in the **HTTP Flood Protection** section, and click **Change Settings**.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79692/156436742036923_en-US.png)

## Best practices for HTTP\(S\) flood protection {#section_07s_2yj_lna .section}

The levels of protection provided by different protection modes are as follows: Super Strict \> Strict \> Emergency \> Normal. The chances of false positives when you use these protection modes are as follows: Super Strict \> Strict \> Emergency \> Normal.

We recommend that you use the Normal mode for your protected website. This mode only blocks IP addresses that frequently send requests to your website. We recommend that you switch to the Emergency or Strict mode when your website is overwhelmed by HTTP\(S\) flood attacks and the Normal mode fails to protect your website.

**Note:** If your website provides API or native application services and the Strict or Super Strict mode is enabled, requests to the website cannot pass the verification. Therefore, these two modes are not suitable to protect this kind of websites. You must create custom HTTP\(S\) flood protection rules for specific URLs.

