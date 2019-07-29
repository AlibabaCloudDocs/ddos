# Configure fine-grained access control rules {#task_183113 .task}

Fine-grained access control allows you to customize access control rules. You can filter access requests based on a combination of criteria of commonly used HTTP fields, such as IP address, URL, Referer, User-Agent, and Params. For requests that meet the criteria, you can allow, block, or verify their access. This feature applies to custom business scenarios, such as hotlink protection and website administration console protection.

Each fine-grained access control rule consists of one or more match conditions and an action. When creating a rule, you can define match conditions by setting the field name, logical relation, and field value. Then, select an action to be triggered for access requests that meet the match conditions.

**Match conditions**

Match conditions consist of the field name, logical relation, and field value. The field value does not support regular expressions, but can be set to null.

**Action**

The fine-grained access control rule supports the following actions:

-   Block: blocks the access request that meets the match conditions.
-   Allow: allows the access request that meets the match conditions.
-   Challenge: uses the CAPTCHA algorithm to verify the source IP address of the access request that meets the match conditions.

**Rule matching order**

If multiple rules are configured, access requests are matched based on the order of the fine-grained access control rules. The rule with the higher ranking is matched first.

**Precautions** 

-   There are limits to the number of fine-grained access control rules.
    -   **Standard function instance:** A maximum of five rules can be configured for each website domain. Only IP address, URL, Referer, and User-Agent fields can be used as the criteria to match requests.
    -   **Enhanced function instance:** A maximum of 10 rules can be configured for each website domain.
-   Access requests are matched based on the display order of fine-grained access control rules in the rule list. The upper the display order, the higher the priority. If a request meets the match conditions of multiple rules, the action of the rule that takes the highest priority is taken.

1.  Log on to the [Anti-DDoS Premium console](https://yundun.console.aliyun.com/?p=ddosdip).
2.  In the left-side navigation pane, choose **Mitigation Settings** \> **HTTP Flood Protection Policies**.
3.  Select the domain \(example.aliyundemo.com is used as an example\) for which you want to configure fine-grained access control rules. Turn on Accurate Access Control.![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/156910/156436726344278_en-US.png)


4.  In the Accurate Access Control section, click **Change Settings** to configure rules. You can configure a rule as shown in the following figure. After the rule is configured, any request that contains MSIE in the User-Agent field to access the /index.php page will be blocked.![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/156910/156436726344279_en-US.png)

 

    **Supported fields** 

    **Note:** Anti-DDoS Premium instances with the standard function plan only support using IP address, URL, Referer, and User-Agent fields as the criteria to match requests.

    |Field|Description|Applicable logical relation|
    |-----|-----------|---------------------------|
    |IP|The source IP address in the access request.|     -   Is Part Of
    -   Is Not Part Of
 |
    |URI|The URI in the access request.|     -   Contains
    -   Does Not Contain
    -   Equals
    -   Does Not Equal
    -   Is Shorter Than
    -   Has a Length Of
    -   Is Longer Than
 |
    |User-Agent|The information about the client that initiates the access request, such as the identifiers of the browser.|     -   Contains
    -   Does Not Contain
    -   Equals
    -   Does Not Equal
    -   Is Shorter Than
    -   Has a Length Of
    -   Is Longer Than
 |
    |Cookie|The cookie information in the access request.|     -   Contains
    -   Does Not Contain
    -   Equals
    -   Does Not Equal
    -   Is Shorter Than
    -   Has a Length Of
    -   Is Longer Than
    -   Does Not Exist
 |
    |Referer|The source URL of the access request. This URL indicates the address of the webpage from which the access request is redirected.|     -   Contains
    -   Does Not Contain
    -   Equals
    -   Does Not Equal
    -   Is Shorter Than
    -   Has a Length Of
    -   Is Longer Than
    -   Does Not Exist
 |
    |Content-Type|The HTTP content type \(MIME\) specified in the response to the access request.|     -   Contains
    -   Does Not Contain
    -   Equals
    -   Does Not Equal
    -   Is Shorter Than
    -   Has a Length Of
    -   Is Longer Than
 |
    |X-Forwarded-For|The originating IP address of the client that initiates the access request.|     -   Contains
    -   Does Not Contain
    -   Equals
    -   Does Not Equal
    -   Is Shorter Than
    -   Has a Length Of
    -   Is Longer Than
    -   Does Not Exist
 |
    |Content-Length|The number of bytes in the access request.|     -   Is Smaller Than
    -   Has a Value Of
    -   Is Larger Than
 |
    |Post-Body|The content of the access request.|     -   Contains
    -   Does Not Contain
    -   Equals
    -   Does Not Equal
 |
    |Http-Method|The method of the access request, such as GET and POST.|     -   Equals
    -   Does Not Equal
 |
    |Header|The header of the access request. You can customize the HTTP header fields and field values to be matched.|     -   Contains
    -   Does Not Contain
    -   Equals
    -   Does Not Equal
    -   Is Shorter Than
    -   Has a Length Of
    -   Is Longer Than
    -   Does Not Exist
 |
    |Params|The parameter in the URL of the access request. It is the part following the question mark \(?\) in the URL. For example, in the www.abc.com/index.html? action=login, action=login is the parameter.|     -   Contains
    -   Does Not Contain
    -   Equals
    -   Does Not Equal
    -   Is Shorter Than
    -   Has a Length Of
    -   Is Longer Than
 |

    **Other configuration examples**

    You can configure fine-grained access control rules based on the following configuration examples.

    -   Intercept malicious requests

        In most cases, clients do no initiate POST requests to the root directory. During HTTP flood attacks, a large number of POST requests to the root directory are initiated by the client. The validity of these attacks can be evaluated. If the requests are identified as abnormal, you can use fine-grained access control rules to intercept the request. A configuration example is as follows:

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/156910/156436726344280_en-US.png)

    -   Intercept access requests of crawlers within a period of time

        If the website traffic are used by a large number of crawler requests within a certain period of time, which may be HTTP flood attacks initiated by bots by simulating crawlers, you can intercept the crawler requests.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/156910/156436726444281_en-US.png)

5.  After the configuration is complete, click **OK** to make the configuration take effect.

