# Step 4: Configure HTTP flood protection policies {#task_221018 .task}

After you set up an Anti-DDoS Pro instance to protect your service, you can configure HTTP flood protection policies to protect your site against HTTP flood attacks.

You have added your website in the Anti-DDoS Pro console. For more information, see [Step 1: Add a website](reseller.en-US/New Anti-DDoS Pro Service/Quick Start/Set up Anti-DDoS Pro using domains/Step 1: Add a website.md#).

Anti-DDoS Pro provides the following HTTP flood protection policies:

-   Blacklist and Whitelist: You can use the blacklist to block requests from specific IP addresses, or use the whitelist to allow specific IP addresses to access your site without further inspection.
-   HTTP Flood Protection: You can enable HTTP Flood Protection to automatically detect and block flood requests. You can select default protection settings or create custom protection rules based on your needs.
    -   Default protection settings: You can select from four modes that have different protection capabilities to meet your business needs.
    -   Custom protection rules: You can create custom rules to limit the requests to specific directories on your site.

**Note:** Currently, a series of new protection policies are in preview testing. By default, Anti-DDoS Pro only provides the following features for mitigating flood attacks: Blacklist, Whitelist, and HTTP Flood Protection. If you want to use the following new features: Geo-blocking, Accurate Access Control, Intelligent Protection, and Web Acceleration, we recommend that you switch to new protection policies. For more information, see [New protection policies](reseller.en-US/New Anti-DDoS Pro Service/User Guide/New protection policies/New protection policies.md#).

1.   Log on to the [Anti-DDoS Pro console](https://partners-yundunnext.console.aliyun.com/?p=ddoscoo#/domain). 
2.   In the left-side navigation pane, choose **Management** \> **Websites**. 
3.   In the website list, select a domain and click **Protection Settings**.![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/188492/156154082845987_en-US.png)

  
4.   On the Protection Settings page, click HTTP Flood Protection Policies and perform the following steps based on your needs: 

    **Note:** HTTP flood protection policies take effect for domains. Make sure to specify the correct domain before you configure HTTP flood protection policies.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/188491/156154082946037_en-US.png)

    -   Blacklist and Whitelist

        Select **Blacklist and Whitelist,** and click **Change Settings**. In the Blacklist and Whitelist Settings dialog box, add IP addresses or CIDR blocks to the blacklist and whitelist respectively.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/188491/156154082946038_en-US.png)

        **Note:** You can enter up to 200 IP addresses or CIDR blocks in the blacklist and whitelist respectively. Separate multiple IP addresses or CIDR blocks with commas \(,\).

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/188491/156154082946040_en-US.png)

    -   HTTP Flood Protection

        Select **HTTP Flood Protection,** and click the Switch icon next to **Status** to enable HTTP Flood Protection. You can then select default protection settings or create custom rules based on your business needs.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/188491/156154082946041_en-US.png)

        -   Default protection settings

            You can select one of the following **modes** to protect your service: **Normal**, **Emergency**, **Strict**, and **Super Strict**.

            **Note:** Different modes provide different protection capabilities. Modes that offer higher protection capabilities usually have higher false positive rates. We recommend that you enable modes with higher capabilities only when the other modes fail to mitigate attacks effectively. For more information, see [Configure HTTP flood protection](reseller.en-US/New Anti-DDoS Pro Service/User Guide/Configure layer 7 protection/Configure HTTP flood protection.md#).

        -   Custom rules

            1.  Click the Switch icon next to **Custom Rule,** and click **Change Settings**.
            2.  On the Custom HTTP Flood Protection Rules page, click **Create Rule**.

                ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/188491/156154082946042_en-US.png)

            3.  In the Create Rule dialog box, specify the following parameters.

                |Parameter|Description|
                |---------|-----------|
                | **Name** |The name of the rule.|
                | **URI** |The address of the page that you want to protect.|
                | **Matching Rule** |The rule that determines whether a request is counted. Valid values:                 -    **Exact Match**: A request is counted when the requested URI is the same as the protected URI.
                -    **Prefix Match**: A request is counted when the prefix of the requested URI is the same as the protected URI.
 |
                | **Interval** |The rule that determines whether a source IP address triggers the custom rule. When the number of counted requests from an IP address exceeds the **Individual IP Visits** limit during the **Interval**, the custom rule is triggered.|
                | **Individual IP Visits** |
                | **Block Type** |The action to be performed when the custom rule is triggered.                 -    **Block**: Blocks requests from the source IP address for a specific time period.
                -    **Captcha Verification**: Redirects the request to a captcha verification page. To access your site, the user must pass the captcha verification.
 |

                ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/188491/156154082946043_en-US.png)

                In the previous example, when the number of requests to the `/login` page from an IP address exceeds 20 within 5 seconds, the IP address is blocked for 5 minutes.

            4.  Click **OK**.
            After a rule is created, it is displayed in the rule list. You can **Edit** or **Delete** rules based on your needs.

            ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/188491/156154082946044_en-US.png)


