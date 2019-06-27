# Add Anti-DDoS Pro back-to-origin CIDR blocks to the whitelist {#task_221713 .task}

When you use Anti-DDoS Pro to protect your site, we recommend that you add back-to-origin CIDR blocks to the whitelist so that traffic from Anti-DDoS Pro is not mistakenly blocked by security software on your origin server.

After you set up Anti-DDoS Pro to protect your site, all traffic to your site is directed to Anti-DDoS Pro first, which filters out malicious traffic and then forwards the traffic back to the origin server. The process whereby an Anti-DDoS Pro instance forwards traffic back to the origin server is called back-to-origin.

Anti-DDoS Pro acts as a reverse proxy and supports Full NAT mode.

Before Anti-DDoS Pro is used to protect the origin server, client IP addresses are widely distributed. The number of requests from each client IP address is relatively small under normal circumstances.

After Anti-DDoS Pro is used, a limited number of back-to-origin CIDR blocks are used to forward traffic to the origin server. For the origin server, all incoming requests originate from these back-to-origin CIDR blocks. The number of requests from each back-to-origin IP address can be quite large, which makes it appear that these IP addresses are attacking the origin server. If other DDoS protection policies are configured on the origin server, these back-to-origin CIDR blocks may be blocked or subject to bandwidth limits.

For example, the most commonly found 502 error indicates that when Anti-DDoS Pro forwards requests to the origin server, the server is not responding. The reason may be that the back-to-origin IP address is blocked by the firewall on the origin server.

Therefore, we recommend that you disable the firewall and other security software on the origin server after you configure forwarding rules. This ensures that Anti-DDoS back-to-origin CIDR blocks are not affected by the protection policies on the origin server. Alternatively, you can use the following steps to find the back-to-origin CIDR blocks used by Anti-DDoS Pro and add them to the whitelist of the security software on the origin server. We recommend that you create security groups or use whitelists to protect your origin server. For more information, see [Protect origin servers](reseller.en-US/Anti-DDoS Pro Service/Best Practice/Protect origin sites that use Anti-DDoS Pro.md#).

1.   Log on to the [Anti-DDoS Pro console](https://partners-yundunnext.console.aliyun.com/?p=ddoscoo#/domain). 
2.   In the left-side navigation pane, choose **Management** \> **Websites**. 
3.   On the Websites page, click **View Back-to-origin CIDR Blocks** on the top of the page.![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/188989/156160011945878_en-US.png)

  
4.   In the Back-to-origin CIDR Block dialog box, copy the back-to-origin CIDR blocks used by Anti-DDoS Pro.![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/188989/156160011945879_en-US.png)

  
5.   Modify the whitelist of the security software on your origin server and add these back-to-origin CIDR blocks to the whitelist. 

