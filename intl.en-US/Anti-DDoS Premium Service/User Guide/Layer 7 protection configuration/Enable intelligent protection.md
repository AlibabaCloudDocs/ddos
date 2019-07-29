# Enable intelligent protection {#task_183121 .task}

Intelligent protection is based on the big data processing capabilities of Alibaba Cloud. Through the intelligent analysis engine, it can learn business traffic baselines and dynamically adjust protection models to help you detect and block attacks in a timely manner, such as malicious bots and HTTP flood attacks.

**Note:** When intelligent protection is enabled, the automatically issued intelligent rules cannot be manually deleted. If the intelligent protection rules are not suitable for your business scenarios, we recommend that you disable intelligent protection. After intelligent protection is disabled, the automatically issued intelligent rules are cleared instantly.

1.  Log on to the [Anti-DDoS Premium console](https://yundun.console.aliyun.com/?p=ddosdip).
2.  In the left-side navigation pane, choose **Mitigation Settings** \> **HTTP Flood Protection Policies**.
3.  Select the domain \(example.aliyundemo.com is used as an example\) for which you want to enable intelligent protection. Turn on Intelligent Protection. 

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/156918/156436749344284_en-US.png)


If "The operation is successful" is displayed, this feature has been enabled.

After the intelligent protection feature is enabled, Anti-DDoS Premium instances automatically issue intelligent rules when attacks are detected. You can view specific rule entries in the Accurate Access Control section. The rule name starts with "smartcc\_."

**Note:** Each rule issued by intelligent protection has a validity period. If the validity period ends, the protection rule will automatically expire and be cleared.

