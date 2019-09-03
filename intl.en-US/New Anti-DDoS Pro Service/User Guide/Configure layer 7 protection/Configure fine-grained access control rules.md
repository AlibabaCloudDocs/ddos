# Configure fine-grained access control rules {#task_183113 .task}

Fine-grained access control allows you to create custom rules to control access to your business. You can filter requests based on the request IP, URL, and common HTTP header fields, such as the Referer, User-Agent, and parameters. You can handle matching requests with different actions, such as clear, block, and challenge. This feature supports custom business scenarios, such as hotlinking protection and management console protection.

Each access control rule consists of one or more match conditions and an action. When you create a rule, you need to define match conditions by specifying the field name, logical relation, and field value. You also need to select an action that will be triggered when a matching request is detected.

**Match conditions**

Each match condition consists of a field name, logical relation, and field value. Currently, field values do not support regular expressions, but can be left empty.

**Actions**

The following actions are supported:

-   Block: Requests that meet match conditions are blocked.
-   Clear: Requests that meet match conditions are allowed to your website.
-   Challenge: Captcha verification is used to verify the source IP of the requests that meet match conditions.

**The order of rules**

If multiple rules are configured, requests are compared to these rules based on the order that rules are displayed in the rule list. Anti-DDoS Pro compares requests to the first rule in the list and continues in sequence from top to bottom.

**Notes** 

-   The number of access control rules is subject to a limit.
    -   **Standard package:** For each protected domain, a maximum of five rules can be configured. Only the request IP, URL, Referer, and User-Agent field can be used to create match conditions.
    -   **Enhanced package:** For each protected domain, a maximum of 10 rules can be configured.
-   The rule priority is determined by the order that rules are displayed in the rule list. The higher the rule, the higher the priority. If a request meets multiple match conditions of different rules, the action of the rule with the highest priority takes effect.

1.  Log on to the [new Anti-DDoS Pro console](https://partners-yundun.console.aliyun.com/?p=ddoscoo&__consolePageCode=ddoscoo).
2.  In the left-side navigation pane, choose **Protection** \> **Protection Settings** \> **HTTP Flood Protection Policies**.
3.  Select a domain, for example, example.aliyundemo.com. In the Accurate Access Control section, click the Status toggle to enable fine-grained access control for the selected domain.![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/156910/156747924344278_en-US.png)


4.  Click **Change Settings** to configure access control rules. In the following example, requests that attempt to access the /index.php page and contain MSIE in the User-Agent field are blocked.![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/156910/156747924344279_en-US.png)

 

    **Supported fields** 

    **Note:** Anti-DDoS Pro instances of the standard package only support the following fields: request IP, URL, Referer, and User-Agent.

    |Field|Description|Supported logical relation|
    |-----|-----------|--------------------------|
    |IP|The source IP of the request.|     -   Is Part Of
    -   Is Not Part Of
 |
    |URI|The request URI.|     -   Contains
    -   Does Not Contain
    -   Equals
    -   Does Not Equal
    -   Is Shorter Than
    -   Has a Length Of
    -   Is Longer Than
 |
    |User-Agent|The information about the browser that sent the request.|     -   Contains
    -   Does Not Contain
    -   Equals
    -   Does Not Equal
    -   Is Shorter Than
    -   Has a Length Of
    -   Is Longer Than
 |
    |Cookie|The cookie in the request.|     -   Contains
    -   Does Not Contain
    -   Equals
    -   Does Not Equal
    -   Is Shorter Than
    -   Has a Length Of
    -   Is Longer Than
    -   Does Not Exist
 |
    |Referer|The URL of the site that initiated the request. This URL indicates the page that contained the hyperlink to the currently requested URL.|     -   Contains
    -   Does Not Contain
    -   Equals
    -   Does Not Equal
    -   Is Shorter Than
    -   Has a Length Of
    -   Is Longer Than
    -   Does Not Exist
 |
    |Content-Type|The content type, or MIME type, of the returned content that is specified by the request.|     -   Contains
    -   Does Not Contain
    -   Equals
    -   Does Not Equal
    -   Is Shorter Than
    -   Has a Length Of
    -   Is Longer Than
 |
    |X-Forwarded-For|The originating IP address of the client that initiated the request.|     -   Contains
    -   Does Not Contain
    -   Equals
    -   Does Not Equal
    -   Is Shorter Than
    -   Has a Length Of
    -   Is Longer Than
    -   Does Not Exist
 |
    |Content-Length|The byte length of the HTTP body of the request.|     -   Is Smaller Than
    -   Has a Value Of
    -   Is Larger Than
 |
    |Post-Body|The content of the request.|     -   Contains
    -   Does Not Contain
    -   Equals
    -   Does Not Equal
 |
    |Http-Method|The request method, such as GET and POST.|     -   Equals
    -   Does Not Equal
 |
    |Header|The request header. You can specify an HTTP header field and value based on your needs.|     -   Contains
    -   Does Not Contain
    -   Equals
    -   Does Not Equal
    -   Is Shorter Than
    -   Has a Length Of
    -   Is Longer Than
    -   Does Not Exist
 |
    |Params|The parameters in the request URL. The parameter part in the URL usually follows a question mark \(?\). For example, in the URL www.abc.com/index.html?action=login, the parameter part is action=login.|     -   Contains
    -   Does Not Contain
    -   Equals
    -   Does Not Equal
    -   Is Shorter Than
    -   Has a Length Of
    -   Is Longer Than
 |

    **Examples**

    The following examples demonstrate how to configure fine-grained access control rules to block specific types of requests.

    -   Block specific requests

        Under most circumstances, clients do no send POST requests to the root directory of your website. In an HTTP flood attack, your website may receive a large number of POST requests to the root directory. We recommend that you check the validity of these requests. If it is confirmed that these requests are not normal requests, you can use access control rules to block them. A sample configuration is provided as follows:

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/156910/156747924344280_en-US.png)

    -   Block Web crawlers

        If your website receives a large volume of crawler traffic, the traffic may originate from malicious bots simulating crawlers, which is one of the common forms of HTTP flood attacks. You can use access control rules to block crawlers.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/156910/156747924344281_en-US.png)

5.  Click **OK** and the rule takes effect immediately.

