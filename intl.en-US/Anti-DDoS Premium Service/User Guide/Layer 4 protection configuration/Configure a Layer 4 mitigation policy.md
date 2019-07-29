# Configure a Layer 4 mitigation policy {#task1011 .task}

Anti-DDoS Premium supports protection against Layer 4 DDoS attacks and provides multiple protection settings to safeguard your business.

Anti-DDoS Premium provides protection against DDoS attacks based on IP addresses and ports for non-website business. You can set limits on parameters such as the request rate and packet length to mitigate DDoS attacks.

Anti-DDoS Premium supports the following mitigation items for you to choose from:

|Item|Description|
|----|-----------|
|False Source|Detects and blocks false source IP addresses. This setting is applicable only to TCP.|
|Empty Connection|Detects and blocks null sessions. This setting is applicable only to TCP.|
|New Connection Speed Limits for Source IP Address|The maximum number of new connections per second from a single source IP address. All new connections exceeding the limit are discarded. The actual limit on the new connection rate may be slightly different because the protection servers are deployed in clusters.|
|Concurrent Connection Speed Limits for Source IP Address|The maximum number of concurrent connections from a single source IP address. All concurrent connections exceeding the limit are discarded.|
|New Connection Speed Limits for Destination IP Address|The maximum number of new connections per second to a single destination IP address and port. All new connections exceeding the limit are discarded. The actual limit on the new connection rate may be slightly different because the protection servers are deployed in clusters.|
|Concurrent Connection Speed Limits for Destination IP Address|The maximum number of concurrent connections to a single destination IP address and port. All concurrent connections exceeding the limit are discarded.|
|Packet Length Filtering|The limit on the payload size of a packet. Unit: Byte. All packets exceeding the size limit are discarded.|

You can configure mitigation policies for a specified port on a specified IP address.

**Note:** Mitigation policies are configured based on ports.

1.  Log on to the [Anti-DDoS Premium console](https://yundun.console.aliyun.com/?p=ddosdip).
2.  In the left-side navigation pane, choose **Provisioning** \> **Non-Website**. On the page that appears, select an Anti-DDoS Premium instance. Click **Edit** in the Mitigation Policies column corresponding to an existing forwarding rule. 

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/830175/156436772250999_en-US.png)

3.  In the **Mitigation Policies** dialog box that appears, configure Mitigation Policies for the selected IP address and port.

