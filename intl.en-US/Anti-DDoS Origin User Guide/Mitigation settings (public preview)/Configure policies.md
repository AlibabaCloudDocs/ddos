# Configure policies

After you add the IP addresses of your cloud services to your Anti-DDoS Origin Enterprise instance, you can configure policies based on your business requirements to allow or deny requests that have specific characteristics. This better protects your cloud services against DDoS attacks.

-   An Anti-DDoS Origin Enterprise instance is purchased.

    For more information, see [Purchase an Anti-DDoS Origin Enterprise instance](/intl.en-US/Anti-DDoS Origin User Guide/Purchase an Anti-DDoS Origin Enterprise instance.md).

    **Note:** The Mitigation Settings feature that provides the policy configuration function is in public preview and is free of charge. It is available only if you have purchased an Anti-DDoS Origin Enterprise instance. If you want to enable this feature, submit a [ticket](https://workorder-intl.console.aliyun.com/?#/ticket/add/?productId=80).

-   The IP addresses of your cloud services are added to the Anti-DDoS Origin Enterprise instance.

    For more information, see [Add a cloud service to Anti-DDoS Origin Enterprise for protection](/intl.en-US/Anti-DDoS Origin User Guide/Instances/Add a cloud service to Anti-DDoS Origin Enterprise for protection.md).


## Procedure overview

If this is the first time for you to use the policy configuration function, perform the following steps:

1.  Create a policy template. For more information, see [Select or create a policy template](#step_hep_jau_gt0).
2.  Add cloud services to the policy template. The policy template is applied to the added cloud services. For more information, see [Add cloud services to the policy template](#step_6vt_13b_kku).
3.  Configure specific policies in the template. After you configure the policies, they take effect on the cloud services that you added in the preceding step.

    The following table describes the supported policies.

    |Policy|Description|Configuration|
    |------|-----------|-------------|
    |**ICMP Blocking**|Denies ICMP requests during traffic scrubbing. This protects the origin server against scans and helps mitigate ICMP flood attacks.|Turn on or off **Status** of **ICMP Blocking**. After you enable this policy, ICMP requests are denied.**Note:** This policy takes effect on the IP addresses in the whitelist. ICMP requests from these IP addresses are also denied.

For more information, see [Configure the ICMP Blocking policy](#step_ix7_v36_1jd). |
    |**Source Port Blocking**|Denies requests from the UDP or TCP protocol over the source or destination ports to mitigate UDP reflection attacks.|Configure the protocols and ports to deny requests. After you enable this policy, requests from the specified protocol and ports are denied.For more information, see [Configure the Source Port Blocking policy](#step_nzj_kye_q9b). |
    |**Blacklist and Whitelist**|Denies or allows requests from specific source IP addresses.|Configure the IP address blacklist and whitelist. After you enable this policy, requests from the IP addresses included in the blacklist are denied, and requests from the IP addresses included in the whitelist are allowed.For more information, see [Configure the Blacklist and Whitelist policy](#step_hrk_q19_il7). |
    |**Byte-Match Filter**|Matches bytes for the content of specific packets to limit the rates of, deny, or allow requests when the instance is scrubbing traffic.|Specify Byte-Match Filter rules to match the required bytes. If requests contain the matching bytes, the requests are denied, allowed, or limited based on the policy.For more information, see [Configure the Byte-Match Filter policy](#step_04s_c8l_sik). |


## Procedure

1.  Log on to the [Anti-DDoS console](https://yundun.console.aliyun.com/?p=ddos).

2.  In the left-side navigation pane, choose **Anti-DDoS Origin** \> **Mitigation Settings**.

3.  Click the **Policy Configuration** tab.

4.  Select or create a policy template.

    -   If you have created policy templates, click the required policy template below **Policy Template**.
    -   If you have not created policy templates, perform the following steps to create a policy template:
    1.  Click **Create Policy** next to **Policy Template**.

    2.  In the **Add** dialog box, specify **Policy Name** and click **OK**.

        ![Create a policy template](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/9187034061/p169416.png)

        After you create the policy template, it is automatically selected.

5.  Add cloud services to the policy template.

    1.  In the **Target assets** section on the right, click **Add IP Addresses**.

    2.  In the **Add IP Addresses** dialog box, select the IP addresses of the required cloud service to apply the policy template.

        ![Add IP Addresses](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/9187034061/p168904.png)

        |Parameter|Description|
        |---------|-----------|
        |**Region**|The region of the cloud service whose IP addresses you want to add to the Anti-DDoS Origin Enterprise instance.|
        |**Instance**|The Anti-DDoS Origin Enterprise instance to which you want to add the IP addresses.|
        |**IP Address**|The IP addresses of the required cloud service.**Note:** An IP address can be added to only one policy template. If an IP address is already added to a different policy template, you cannot select it. |

    3.  Click **OK**.

    After you add the IP addresses, requests from these IP addresses are processed based on the policies in this template. By default, no policies are enabled in the created policy template. You must configure specific policies to deny or allow specific requests.

    You can click **Remove** to remove the IP addresses of cloud services from the **Target assets** section.

6.  Configure the **ICMP Blocking** policy.

    To enable or disable the **ICMP Blocking** policy, perform the following steps:

    1.  On the Policy Configuration tab, turn on or off **Status** for the **ICMP Blocking** option.

        ![ICMP Blocking ](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/9187034061/p169426.png)

    2.  In the **Ok** dialog box, click **OK**.

7.  Configure the **Source Port Blocking** policy.

    To configure the Source Port Blocking policy, perform the following steps:

    1.  On the Policy Configuration tab, click **Configure** for the **Source Port Blocking** option.

        ![Source Port Blocking ](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/9187034061/p169427.png)

    2.  In the **Configure Source Port Blocking** pane, click **Add**.

        **Note:** You can add a maximum of eight port blocking rules.

    3.  In the **Add Port** dialog box, configure the following parameters.

        ![Add Port](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/9187034061/p169430.png)

        |Parameter|Description|
        |---------|-----------|
        |**Protocol**|The protocol for blocking. Valid values: **TCP** and **UDP**.|
        |**Type**|The type of port for blocking. Valid values: **Source Port** and **Destination Port**.|
        |**Port Range**|The range of ports for blocking. Valid values: 1 to 65535.**Note:** Make sure that the port ranges of two port blocking rules that have the same protocol and port type do not overlap. |
        |**Action**|The action that is triggered by requests from the specified protocol and ports. The value is fixed as **Block**.|

    4.  Click **OK**.

        After you add a port blocking rule, it automatically takes effect. Requests from the specified protocol and ports are denied. You can manage configured port blocking rules in the **Configure Source Port Blocking** pane. For example, you can click **Edit** or **Delete** to edit or delete a port blocking rule.

8.  Configure the Blacklist and Whitelist policy.

    To configure the Blacklist and Whitelist policy, perform the following steps:

    1.  On the Policy Configuration tab, click **Configure** for the **Blacklist and Whitelist** option.

        ![Blacklist and Whitelist ](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/9187034061/p169428.png)

    2.  In the **Blacklist and Whitelist** pane, click **Add IP Addresses**.

    3.  In the **Add IP Addresses** dialog box, configure the blacklist and whitelist.

        You can add a maximum of 10,000 IP addresses to the blacklist and a maximum of 10,000 IP addresses to the whitelist. Separate multiple IP addresses with spaces or line breaks.

        ![Add IP Addresses](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/9187034061/p169431.png)

    4.  Click **OK**.

        After you configure the Blacklist and Whitelist policy, it immediately takes effect. Requests from the IP addresses included in the blacklist are denied, and requests from the IP addresses included in the whitelist are allowed. You can manage the configured blacklist and whitelist in the **Blacklist and Whitelist** pane. For example, you can click **Delete** to delete an IP address or click **Clear** to clear the blacklist or whitelist.

9.  Configure the Byte-Match Filter policy.

    To configure the Byte-Match Filter policy, perform the following steps:

    1.  On the Policy Configuration tab, click **Configure** for the **Byte-Match Filter** option.

        ![Byte-Match Filter](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/9187034061/p169432.png)

    2.  In the **Configure Byte-Match Filter** pane, click **Add**.

        **Note:** You can add a maximum of eight Byte-Match Filter rules.

    3.  In the **Add Byte-Match Filter Rule** dialog box, configure the following parameters.

        ![Add Byte-Match Filter Rule](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/9187034061/p169433.png)

        |Parameter|Description|
        |---------|-----------|
        |**Protocol**|The type of the protocol. Valid values: **TCP** and **UDP**.|
        |**Source Port Range**|The range of source ports. Valid values: 1 to 65535.|
        |**Destination Port Range**|The range of destination ports. Valid values: 1 to 65535.|
        |**Packet Length Range**|The range of packet lengths. Valid values: 1 to 1500. Unit: bytes.|
        |**Offset**|The offset of bytes in UDP or TCP packets. Valid values: 0 to 1500. Unit: bytes.If you set the offset to 0, the system starts matching from the first byte. |
        |**Payload**|The matching payload of UDP or TCP packets. You must enter a hexadecimal string that starts with 0x.|
        |**Action**|The action that is triggered by the matching requests. Valid values: **Allow**, **Block**, **Limit Bandwidth of Source IP Address**, and **Limit Bandwidth of Session**.If you select **Limit Bandwidth of Source IP Address** or **Limit Bandwidth of Session**, you must set **Bandwidth**. Valid values of **Bandwidth**: 1 to 100000. |

    4.  Click **OK**.

        After you configure the Byte-Match Filter policy, it automatically takes effect. Requests that meet the rules are denied, allowed, or limited based on the policy. You can manage the Byte-Match Filter rules in the **Configure Byte-Match Filter** pane. For example, you can click **Edit**, **Delete**, Move Down, or Move Up to manage the rules.

        **Note:** You can adjust the order of rules for better management. The adjustment does not affect the rules.


