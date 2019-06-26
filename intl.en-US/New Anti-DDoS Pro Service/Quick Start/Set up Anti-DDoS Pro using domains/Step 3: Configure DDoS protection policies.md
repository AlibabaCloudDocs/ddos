# Step 3: Configure DDoS protection policies {#task_221019 .task}

After you set up an Anti-DDoS Pro instance to protect your service, Anti-DDoS Smart Defense is enabled by default. You can modify DDoS protection policies based on your needs.

You have added your website in the Anti-DDoS Pro console. For more information, see [Step 1: Add a website](reseller.en-US/New Anti-DDoS Pro Service/Quick Start/Set up Anti-DDoS Pro using domains/Step 1: Add a website.md#).

You can modify the following DDoS protection policies:

|DDoS protection policy|Description|
|----------------------|-----------|
|Scrubbing mode|Smart Defense bases its decisions on historical traffic data. If this is the first time that you set up an Anti-DDoS Pro instance to protect your service, note that it takes Smart Defense about three days to learn your traffic pattern to provide the best protection. If attacks are launched against your service within these three days, you can mitigate attacks by limiting the number of new connections from specific IP addresses. If Smart Defense fails to meet your needs under the normal mode, you can set the mode to strict to enable the most rigorous protection.|
|Blacklist and whitelist|For IP addresses that send a large number of malicious requests to your server, you can add them to the blacklist to block their requests. You can add the following IP addresses to the whitelist to allow their requests without further inspection: internal CIDR blocks, service interface IP addresses, and verified IP addresses.|
|Deactivate black holes|After you set up an Anti-DDoS Pro instance to protect your site, incoming traffic to your site is forwarded to a black hole when the peak attack bandwidth exceeds your basic or burstable bandwidth. To restore your service, you can deactivate the black hole in the Anti-DDoS Pro console.|
|Block traffic|We recommend that you block traffic when your service is experiencing DDoS attacks and the peak attack bandwidth is likely to exceed your burstable bandwidth. You can block overseas traffic transmitted through China Telecom and China Unicom networks to mitigate attacks.|

1.   Log on to the [Anti-DDoS Pro console](https://partners-yundunnext.console.aliyun.com/?p=ddoscoo#/domain). 
2.   In the left-side navigation pane, choose **Management** \> **Websites**. 
3.   In the websites list, select a domain and click **Protection Settings**.![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/188492/156154085945987_en-US.png)

  
4.   On the Protection Settings page, click Anti-DDoS Protection Policies and perform the following steps based on your needs: 
    -    **Scrubbing Mode** 

        Select an Anti-DDoS Pro instance and click **Modify Smart Defense Mode** in the Actions column. In the Modify Smart Defense Mode dialog box, select a scrubbing mode. Anti-DDoS Pro supports the following scrubbing modes:

        -    **Low**: This mode scrubs traffic that displays common attack patterns. The mode provides moderate protection capabilities and has a low false positive rate.
        -    **Normal**: This mode scrubs traffic that displays common and likely attack patterns. The mode maintains an optimal balance between protection and false positives.
        -    **Strict**: This mode provides the most rigorous protection against malicious traffic and may cause a certain number of false positives.
        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/188492/156154085945943_en-US.png)

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/188492/156154085945944_en-US.png)

    -    **Blacklist and Whitelist** 

        **Note:** The configurations of the blacklist and whitelist are effective for individual domains, not Anti-DDoS Pro instances.

        You can click **Manually Add** to add IP addresses to the blacklist or whitelist. For more information, see [Configure the blacklist and whitelist](reseller.en-US/New Anti-DDoS Pro Service/User Guide/Configure layer 7 protection/Configure the blacklist and whitelist.md#).

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/188492/156154085945949_en-US.png)

    -    **Deactivate Blackhole Status** 

        You can click **Deactivate** in the Actions column to deactivate the black hole when your Anti-DDoS Pro instance is in the Black Hole status. For more information, see [Deactivate the black hole status](reseller.en-US/New Anti-DDoS Pro Service/User Guide/Configure layer 4 protection/Deactivate the black hole status.md#).

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/188492/156154085945950_en-US.png)

    -    **Block Flow** 

        Select an Anti-DDoS Pro instance, and click **Blocked** in the Actions column to block overseas traffic transmitted through China Telecom and China Unicom networks. For more information, see [Block traffic flow](reseller.en-US/New Anti-DDoS Pro Service/User Guide/Configure layer 4 protection/Block traffic flow.md#).

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/188492/156154085945951_en-US.png)


