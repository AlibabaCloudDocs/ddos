# Step 1. Set up HTTP protection {#task769 .task}

HTTP website protection only supports TCP 80 port. If your web service needs to run on other ports, such as 8080, select layer 4 port \(non-website access\) protection.

1.  Log on to the [Anti-DDoS Pro console](https://yundun.console.aliyun.com/?p=ddospro).
2.  Go to **Access** \> **Web Service**, and then click **Add Domain** to add the domain that you want to protect.![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79522/156134108934905_en-US.png)


3.  Input **Domain Name**, and **Origin site domain** or **Origin site IP** address accordingly.![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79522/156134109034906_en-US.png)

 

    **Note:** 

    -   Domain name supports wildcard names. For example, “\*.abc.com” can be used to match “www.abc.com”, “mail.abc.com”, and “blog.abc.com”.
    -   If you enter a wildcard domain and a specific domain name, such as `*.aliyun.com` and `www.aliyun.com`, Anti-DDoS Pro will use the redirection rules and protections policies of the specific domain name.
    -   Up to 50 domain names can be added to a virtual IP address for HTTP forwarding.
    -   More than one origin IP address can be added. Multiple origin IP addresses must be separated by commas.
    -   Up to 20 origin IP addresses can be added to a domain name.
4.  Click **Next**, and then select Anti-DDoS Pro instances and ISP lines for the domain.![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79522/156134109034907_en-US.png)


5.  Click **OK**. A new domain entry will be added.
6.  Click **Setting**under the created domain, and operate the **HTTP Flood Protection** switch to enable or disable corresponding protections, which is enabled by default.

