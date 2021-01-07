# Edit forwarding rules

You can edit forwarding rules and change the origin server IP addresses in the rules. This topic describes how to edit one or more forwarding rules.

Forwarding rules are created for your Anti-DDoS Pro or Anti-DDoS Premium instance. For more information, see [Create forwarding rules](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Use ports/Create forwarding rules.md).

## Limits

-   You can change the IP addresses of origin servers only for forwarding rules that are manually created. Automatically generated rules do not support this operation.
-   If the forwarding protocol and port of a rule are changed, we recommend that you create a forwarding rule.

## Edit a forwarding rule

1.  Log on to the [Anti-DDoS Pro console](https://yundun.console.aliyun.com/?p=ddoscoo).

2.  In the top navigation bar, select the region where your instance resides.

    -   **Mainland China**: If you select this region, the **Anti-DDoS Pro console** appears.
    -   **Outside Mainland China**: If you select this region, the **Anti-DDoS Premium console** appears.
    You can switch the region to configure and manage Anti-DDoS Pro or Anti-DDoS Premium instances. Make sure that you select the required region when you use Anti-DDoS Pro or Anti-DDoS Premium.

3.  In the left-side navigation pane, choose **Provisioning** \> **Port Config**.

4.  On the **Port Config** page, select the instance that you want to manage.

5.  Find the rule that you want to edit, and click **Edit** in the Actions column.

    **Note:** If you use an Anti-DDoS Pro instance, you can edit more than one rule at a time. For more information, see [Edit more than one forwarding rule at a time](#section_ri4_j41_ii8).

6.  In the **Edit Rule** dialog box, change the value of **Origin Server IP** and click **OK**.

    ![Edit Rule](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/7331000161/p67664.png)

    After you change the IP addresses of the origin servers, Anti-DDoS Pro or Anti-DDoS Premium forwards traffic based on the new rule.


## Edit more than one forwarding rule at a time

**Note:** Only Anti-DDoS Pro allows you to edit more than one forwarding rule at a time. When you modify more than one rule, you can change only the IP addresses of the origin servers.

1.  Log on to the [Anti-DDoS Pro console](https://yundun.console.aliyun.com/?p=ddoscoo).

2.  In the top navigation bar, select **Mainland China**.

    If you select this region, the **Anti-DDoS Pro console** appears.

3.  In the left-side navigation pane, choose **Provisioning** \> **Port Config**.

4.  On the **Port Config** page, select the instance that you want to manage and choose **Batch Operations** \> **Edit Rule**.

    ![Edit Rule](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/8831000161/p190185.png)

5.  In the Edit Rule dialog box, enter the information as shown in the sample file and click **OK**.

    ![Batch Operations](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9097449951/p67639.png)

    You can create a rule based on the following requirements.

    -   Each line represents a rule.
    -   From left to right, the fields in each rule indicate the following parameters: forwarding protocol, forwarding port, origin server port, and IP address of the origin server. Fields are separated by spaces. For more information about the parameters, see [Rule parameters](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Use ports/Create forwarding rules.mdtable_cmg_aw2_bd3).
6.  Confirm the entered information, select the rules that you want to apply, and then click **OK**.

7.  Close the Edit Rule dialog box.


