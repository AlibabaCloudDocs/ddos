# Mark back-to-origin requests

After you add your website to Anti-DDoS Pro or Anti-DDoS Premium, you can turn on the Getting source port from the real customer switch to obtain your actual source ports of clients. You can also mark the back-to-origin requests that Anti-DDoS Pro or Anti-DDoS Premium forwards to the origin server by using custom HTTP headers. This allows the backend servers to perform statistical analysis on the back-to-origin requests in a more convenient manner. This topic describes how to mark the back-to origin requests that Anti-DDoS Pro or Anti-DDoS Premium forwards to your origin server.

Your website is added to Anti-DDoS Pro or Anti-DDoS Premium. For more information, see [Add a website](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Use domains/Add a website.md).

## Procedure

1.  Log on to the [Anti-DDoS Pro console](https://yundun.console.aliyun.com/?p=ddoscoo).

2.  In the top navigation bar, select the region where your instance resides.

    -   **Mainland China**: If you select this region, the **Anti-DDoS Pro console** appears.
    -   **Outside Mainland China**: If you select this region, the **Anti-DDoS Premium console** appears.
    You can switch the region to configure and manage Anti-DDoS Pro or Anti-DDoS Premium instances. Make sure that you select the required region when you use Anti-DDoS Pro or Anti-DDoS Premium.

3.  In the left-side navigation pane, choose **Provisioning** \> **Website Config**.

4.  Find the website whose configurations you want to edit and click **Edit** in the **Actions** column.

5.  On the page that appears, find the **Traffic mark** section and configure the following parameters.

    |Parameter|Description|
    |---------|-----------|
    |**Getting source port from the real customer**|If you want to obtain the actual source port of a client, turn on this switch.After you turn on the switch, Anti-DDoS Pro or Anti-DDoS Premium records the actual source port of the client in the `X-Forwarded-ClientSrcPort` field when Anti-DDoS Pro or Anti-DDoS Premium forwards the back-to origin requests to the origin server. To obtain the actual source port of the client, you can parse the `X-Forwarded-ClientSrcPort` field in the back-to-origin requests. The specific procedures to obtain the actual source ports of clients are similar to how the actual source IP addresses of clients are obtained. For more information, see [Obtain the actual source IP addresses of requests](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Best practices/Obtain the actual source IP addresses of requests.md). |
    |**Custom Header**|If you want to create custom HTTP headers, you must specify field names and values.After you create custom HTTP headers, Anti-DDoS Pro or Anti-DDoS Premium adds the custom HTTP headers to the back-to-origin requests. This way, the backend servers can perform statistical analysis on the back-to-origin requests.

When you create a custom HTTP header, take note of the following points:

    -   Do not use the following default HTTP headers as custom HTTP headers:
        -   `X-Forwarded-ClientSrcPort`: This field is used to obtain the actual source ports of clients that access Anti-DDoS Pro or Anti-DDoS Premium \(a Layer 7 proxy\).
        -   `X-Forwarded-ProxyPort`: This field is used to obtain the ports of listeners that access Anti-DDoS Pro or Anti-DDoS Premium \(a Layer 7 proxy\).
    -   Do not use standard HTTP headers such as User-Agent. If you use standard HTTP headers, the original header fields may be overwritten.
    -   You can create up to five custom HTTP headers. |

6.  Click **OK**.


## References

[Obtain the actual source IP addresses of requests](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Best practices/Obtain the actual source IP addresses of requests.md)

