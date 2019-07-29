# Block access requests from IP addresses in specific regions {#task_183076 .task}

Geo-blocking allows you to block all access requests from source IP addresses in specified regions \(Mainland China, Hong Kong Special Administrative Region \(SAR\), Macao SAR, Taiwan, and other continents\) with a single click. This feature is available only to specified domains.

Before enabling Geo-blocking, make sure that your website domain has been associated with an Anti-DDoS Premium instance that has the enhanced function plan.

Assume that normal requests to access example.aliyundemo.com are from China \(including Hong Kong SAR, Macao SAR, and Taiwan\). You can configure Geo-blocking for example.aliyundemo.com to block access requests from outside China regions.

**Precautions** 

-   Geo-blocking takes effect at the domain level. If you want to block multiple domains, you need to configure them separately.
-   Geo-blocking uses Anti-DDoS Premium to identify and filter source IP addresses based on their regions. This method does not prevent DDoS attacks from sending traffic.

1.  Log on to the [Anti-DDoS Premium console](https://yundun.console.aliyun.com/?p=ddosdip).
2.  In the left-side navigation pane, choose **Mitigation Settings** \> **HTTP Flood Protection Policies**.
3.  Select the domain \(example.aliyundemo.com is used as an example\) for which you want to set Geo-blocking. Turn on Geo-blocking.![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/156896/156436723044273_en-US.png)


4.  In the Geo-blocking section, click **Change Settings**. In the dialog box that appears, select the regions to be blocked. You can configure Geo-blocking as shown in the following figure. After the configuration takes effect, traffic from outside China regions cannot access example.aliyundemo.com.![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/156896/156436723044274_en-US.png)


5.  After selecting regions, click **OK** to make the configuration take effect.

