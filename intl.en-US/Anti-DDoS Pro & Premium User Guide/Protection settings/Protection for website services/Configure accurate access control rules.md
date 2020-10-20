# Configure accurate access control rules

Both Anti-DDoS Pro and Anti-DDoS Premium allow you to create accurate access control rules for website services that they protect. After you enable Accurate Access Control, you can customize access control rules. These rules allow you to filter access requests based on commonly used HTTP fields, such as IP, URI, Referer, User-Agent, and Params. You can allow, block, or verify requests that match the rules. Accurate Access Control supports custom rules for different scenarios, such as hotlink protection and protection of the website management system.

-   The domain name of your website is added to Anti-DDoS Pro or Anti-DDoS Premium. For more information, see [Add a website](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Use domains/Add a website.md).
-   Protection settings are enabled in Anti-DDoS Pro or Anti-DDoS Premium.

After you add your website service to Anti-DDoS Pro or Anti-DDoS Premium, you can enable Accurate Access Control and create accurate access control rules to manage requests that have specific characteristics. Each accurate access control rule consists of one or more conditions and one action.

-   Conditions specify the HTTP fields, logic operators, and field values to be matched. The following table describes the HTTP fields supported by accurate access control rules.

    **Note:** Different HTTP fields support different logical operators. For example, the source IP field supports the Is Part Of and Is Not Part Of logical operators. The URI field supports the Contains and Does Not Contain logical operators. For more information, see the Logical operator column in the following table.

    |Field|Field description|Supported logical operator|
    |-----|-----------------|--------------------------|
    |IP|The source IP address of the request.|Is Part Of and Is Not Part Of|
    |URI|The request URI.|Contains, Does Not Contain, Equals, Does Not Equal, Is Shorter Than, Has a Length Of, and Is Longer Than|
    |User-Agent|The information about the client browser that sends the request.|Contains, Does Not Contain, Equals, Does Not Equal, Is Shorter Than, Has a Length Of, and Is Longer Than|
    |Cookie|The cookie in the request.|Contains, Does Not Contain, Equals, Does Not Equal, Is Shorter Than, Has a Length Of, Is Longer Than, and Does Not Exist|
    |Referer|The source URL of the request, that is, the page from which the access request is redirected.|Contains, Does Not Contain, Equals, Does Not Equal, Is Shorter Than, Has a Length Of, Is Longer Than, and Does Not Exist|
    |Content-Type|The HTTP content type of the response specified by the request, that is, MIME type information.|Contains, Does Not Contain, Equals, Does Not Equal, Is Shorter Than, Has a Length Of, and Is Longer Than|
    |X-Forwarded-For|The actual client IP address of the request.|Contains, Does Not Contain, Equals, Does Not Equal, Is Shorter Than, Has a Length Of, Is Longer Than, and Does Not Exist|
    |Content-Length|The number of bytes in the request body.|Value Less Than, Value Equals, and Value More Than|
    |Post-Body|The content of the request.|Contains, Does Not Contain, Equals, and Does Not Equal|
    |Http-Method|The request method. Valid values: GET, POST, DELETE, PUT, OPTIONS, CONNECT, HEAD, and TRACE.|Equals and Does Not Equal|
    |Header|The request header that is used to customize the HTTP header fields and values.|Contains, Does Not Contain, Equals, Does Not Equal, Is Shorter Than, Has a Length Of, Is Longer Than, and Does Not Exist|
    |Params|The parameters in the request URI. The parameters follows a question mark \(`?`\) in the URI. For example, the URI `www.abc.com/index.html? action=login` contains a parameter `action=login`.|Contains, Does Not Contain, Equals, Does Not Equal, Is Shorter Than, Has a Length Of, and Is Longer Than|

-   An action defines how a request is handled when it meets the conditions. Supported actions are Clear, Blocked, and JS Challenge. The JS Challenge action verifies source IP addresses by using JavaScript plug-ins.

## Limits

The following table describes the limits on Accurate Access Control based on the function plan of an Anti-DDoS Pro or Anti-DDoS Premium instance.

|Limit|Standard function plan|Enhanced function plan|
|-----|----------------------|----------------------|
|Number of custom rules|≤ 5|≤ 10|
|Supported match fields|IP, URI, Referer, and User-Agent|All fields that support matching|

## Procedure

1.  Log on to the [Anti-DDoS Pro console](https://yundun.console.aliyun.com/?p=ddoscoo).

2.  In the top navigation bar, select the region where your services are deployed.

    -   **Mainland China**: Anti-DDoS Pro
    -   **Outside Mainland China**: Anti-DDoS Premium
3.  In the left-side navigation pane, choose **Mitigation Settings** \> **General Policies**.

4.  On the General Policies page, click the **Protection for Website Services** tab. Select the required domain name from the list on the left side.

5.  In the **Accurate Access Control** section, click **Change Settings**.

    ![Accurate Access Control](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/8297449951/p69862.png)

6.  Create an accurate access control rule for the domain name.

    ![Accurate access control rule](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/8297449951/p70065.png)

    -   Create a rule

        1.  Click **Create Rule**.

            **Note:** If the number of custom rules reaches the upper limit, the **Create Rule** button is not displayed.

        2.  In the Create Rule dialog box, specify the required parameters and click **OK**.

            ![Create Rule](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/8297449951/p44279.png)

            |Parameter|Description|
            |---------|-----------|
            |**Name**|The name of the rule. The name can be up to 128 characters in length and can contain letters, digits, and underscores \(\_\).|
            |**Match Conditions**|The match condition of the rule. To add match conditions for a rule, click **Add Condition**. Each condition consists of **Field Name**, **Logical Relation**, and **Field Value**.             -   Specify Field Name and Logical Relation based on the [Supported match fields](#table_byt_4od_5pn).
            -   Specify Field Value based on Field Name. Field Value is case sensitive. This filed does not support regular expressions, but can be left empty.
You can add multiple match conditions. If multiple conditions are specified, a request matches the rule only when all the conditions are met. |
            |**Action**|The operation that is performed when a request meets the match conditions. Valid values:             -   **Blocked**: Requests that meet match conditions are blocked.
            -   **Clear**: Requests that meet match conditions are allowed.
            -   **JS Challenge**: Source IP addresses of requests that meet the match conditions are verified by using JavaScript plug-ins. |
            |**Validity**|The validity period of the rule. You can set this parameter to 5 Minutes, 10 Minutes, 30 Minutes, 60 Minutes, 90 Minutes, 120 Minutes, or Permanent.|

            In this example, if a request is sent to a page that contains `/login` and the User-Agent field of the request contains `chrome`, the source IP address is verified. The rule remains valid 120 minutes after it is created.

            You can create multiple rules as required.

            **Note:**

            -   If you create multiple rules, the priority of a rule depends on its rank in the rule list. The higher the rank, the higher the priority. The system matches a request against rules in sequence based on their priorities. The higher the rule priority, the earlier the rule is matched.
            -   If a request meets match conditions of multiple rules, the action of the rule with the highest priority takes effect.
        Examples:

        -   Block specific requests.

            In most cases, the root directory of a website does not receive POST requests. If an HTTP flood attack occurs, your website may receive a large number of POST requests that access the root directory. We recommend that you check whether these requests are normal. If these requests are suspicious, you can use accurate access control rules to block them. The following figure shows the example configuration.

            ![Block specific requests](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/8297449951/p44280.png)

        -   Block web crawlers.

            If your website receives a large number of crawler requests within a period of time, an HTTP flood attack may be initiated from bots that simulate crawlers. You can use accurate access control rules to block these requests. The following figure shows the example configuration.

            ![Block web crawlers](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/8297449951/p44281.png)

    -   Edit a rule.
        1.  In the rule list, find the rule that you want to edit and click **Edit** in the Actions column.
        2.  In the Edit Rule dialog box, modify the rule settings and click **OK**. Configure the rule settings the same way as you create a rule. You cannot change the value of **Name**.
    -   Delete a rule.
        1.  In the rule list, find the rule that you want to delete and click **Delete** in the Actions column.
        2.  In the message that appears, click **OK**.
7.  Go back to the **Accurate Access Control** section and turn on **Status** to apply the rules.


