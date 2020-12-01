# Full log

According to APNIC DDoS threat landscape in 2017, more than 80% of DDoS attacks mix HTTP and HTTPS flood attacks, and have a high level of concealment. Therefore, it is especially important to analyze the access and attack behavior by using logs, and apply a protection strategy.

Now, Alibaba Cloud Anti-DDoS Pro has integrated with Log Service on website access logs \(including HTTP flood attack logs\), to provide real-time analysis and reporting center features.

Log Service supports the real-time collection of Alibaba Cloud Anti-DDoS Pro website access logs, HTTP flood attack logs, and supports real-time query and analysis of collected log data. The results of the query are displayed in the form of dashboards.

## Enable the full log service

To enable the full log service for your protected website domain in Anti-DDoS Pro, follow these steps:

**Note:** The usage of Anti-DDoS Pro full log service is charged according to the charge items of the Log Service. If no log data is generated, no billing is made. Log Service is billed by resource usage and provides the FreeTier quota for DDoS Logstore.

The payment of the Anti-DDoS Pro full log service is calculated mainly based on the collected log volume and log storage period factors. The Anti-DDoS Pro full log service provides 100 GB/day log volume and 3 days log storage period as the FreeTier quota. Meanwhile, index-based query analysis, reports, and alarms are not charged.

For example, you enabled the Anti-DDoS Pro full log service for a website whose average log size is about 1600 bytes, about 60 million logs are generated per day, and the storage period is 3 days. The total log volume is about 96 GB per day, not exceeding the FreeTier quota, and no charge is generated. However, if the access log volume of your website business exceeds the FreeTier quota, extra charges can appear.

1.  Log on to the [Anti-DDoS Pro console](https://yundun.console.aliyun.com/?p=ddospro), and go to the **Log** \> **Full Log** page.
2.  Select the website for which you want to enable the Full Log service and click to turn on the Status switch.

    ![](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/79564/154692954734990_en-US.png)


After you turn on the Anti-DDoS Pro Full log service, you can query and analyze the collected logs in real time, view dashboards, and set alarms on the Full Log page.

## Use cases

By using the Anti-DDoS Pro Full log service, you can do the log analysis in the following scenarios.

-   Troubleshoot website access exceptions

    Log Service has been configured to collect Anti-DDoS Pro full logs, you can query and analyze the collected logs in real time. Using SQL statement to analyze the website access log, you can quickly check and analyze the website access exceptions, and view information such as read and write delays and operator distribution.

    For example, view the website access log by using the following statement:

    `__topic__: DDoS_access_log`

-   Track HTTP flood attack source
    -   For example, analyze the HTTP flood attack country distribution recorded in the access log by the following statement:

        `__topic__: DDoS_access_log and cc_blocks > 0| SELECT ip_to_country(if(real_client_ip='-', remote_addr, real_client_ip)) as country, count(1) as "Attack Times" group by country`

    -   For example, view the access PV by the following statement:

        `__topic__: DDoS_access_log | select count(1) as PV`

-   Website operation analysis

    Anti-DDoS Pro access log records the website access data in real time. You can perform SQL query analysis of the collected access log data to obtain real-time access status, such as determining the website popularity, the source and channel of the access, the client distribution, and assist in website operation analysis.

    For example, view the visitor traffic distribution from different network providers:

    `__topic__: DDoS_access_log | select ip_to_provider(if(real_client_ip='-', remote_addr, real_client_ip)) as provider, round(sum(request_length)/1024.0/1024.0, 3) as mb_in group by provider having ip_to_provider(if(real_client_ip='-', remote_addr, real_client_ip)) <> '' order by mb_in desc limit 10`


