# Enable intelligent protection {#task_183121 .task}

Based on Alibaba Cloud's big data capabilities, intelligent protection utilizes an analysis engine to learn the traffic pattern of your business and adjust protection schemes accordingly. This feature can timely detect and block malicious attacks, such as bot attacks and HTTP flood attacks.

**Note:** After intelligent protection is enabled, you cannot delete rules that are automatically created by the system. If you find that the automatically created rules do not suit your business needs, we recommend that you disable intelligent protection. After intelligent protection is disabled, these rules will be deleted instantly.

1.  Log on to the [new Anti-DDoS Pro console](https://yundun.console.aliyun.com/?p=ddoscoo&__consolePageCode=ddoscoo).
2.  In the left-side navigation pane, choose **Protection** \> **Protection Settings** \> **HTTP Flood Protection Policies**.
3.  Select a domain, for example, example.aliyundemo.com. In the Intelligent Protection section, click the Status toggle to enable Intelligent Protection for the selected domain. 

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/156918/156747965944284_en-US.png)


The system displays the following message: "The operation is successful", indicating that intelligent protection has been enabled.

When intelligent protection is enabled, your Anti-DDoS Pro instance automatically creates protection rules when attacks are detected. You can view these rules in the Accurate Access Control section. The name of these rules all start with string "smartcc\_", as shown in the following figure:

![](images/44285_en-US.png)

**Note:** Each rule have an expiration time. Once expired, the rule will be invalid and automatically deleted.

