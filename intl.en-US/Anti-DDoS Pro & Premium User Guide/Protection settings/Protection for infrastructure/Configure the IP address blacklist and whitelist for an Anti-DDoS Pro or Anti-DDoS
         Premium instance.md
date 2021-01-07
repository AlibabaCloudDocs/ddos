# Configure the IP address blacklist and whitelist for an Anti-DDoS Pro or Anti-DDoS Premium instance

This topic describes how to configure the blacklist and whitelist. The blacklist blocks requests from specified source IP addresses to access an Anti-DDoS Pro or Anti-DDoS Premium instance, and the whitelist allows the requests. You can add IP addresses to or remove them from the blacklist or whitelist based on your business requirements.

An Anti-DDoS Pro or Anti-DDoS Premium instance is purchased. For more information, see [Purchase mitigation plans for Anti-DDoS Pro and Anti-DDoS Premium](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Purchase mitigation plans for Anti-DDoS Pro and Anti-DDoS Premium.md).

The blacklist and whitelist configurations take effect only for individual instances.

Requests from the IP addresses in the blacklist are blocked by the Anti-DDoS Pro or Anti-DDoS Premium instance. The following list contains further details about blocking periods of IP addresses:

-   When you add an IP address to the blacklist, you can specify a blocking period from 5 minutes to 7 days.
-   Intelligent protection algorithms mark IP addresses as malicious. Then, these IP addresses are added to the blacklist. Intelligent protection algorithms dynamically calculate the blocking periods of the malicious IP addresses. The blocking period can be from 5 minutes to 1 hour. If attacks are frequently launched from a malicious IP address, the system automatically increases the blocking period of the malicious IP address.

Requests from the IP addresses in the whitelist are allowed by an Anti-DDoS Pro or Anti-DDoS Premium instance. The IP addresses in the whitelist remain valid unless you manually remove them.

If an IP address is added to both the whitelist and blacklist, the whitelist takes effect in a higher priority. If an IP address is in the whitelist, the IP address cannot be added to the blacklist. If you want to add the IP address to the blacklist, you must first remove the IP address from the whitelist.

1.  Log on to the [Anti-DDoS Pro console](https://yundun.console.aliyun.com/?p=ddoscoo).

2.  In the top navigation bar, select the region where your instance resides.

    -   **Mainland China**: If you select this region, the **Anti-DDoS Pro console** appears.
    -   **Outside Mainland China**: If you select this region, the **Anti-DDoS Premium console** appears.
    You can switch the region to configure and manage Anti-DDoS Pro or Anti-DDoS Premium instances. Make sure that you select the required region when you use Anti-DDoS Pro or Anti-DDoS Premium.

3.  In the left-side navigation pane, choose **Mitigation Settings** \> **General Policies**.

4.  On the **Protection for Infrastructure** tab, select the instance that you want to manage from the left-side list.

    You can search for instances based on instance IDs or descriptions.

5.  In the **Blacklist and Whitelist \(Instance IP\)** section, click **Change Settings**.

    ![Blacklist and Whitelist](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/2297449951/p36905.png)

6.  In the Blacklist and Whitelist Settings panel, click **Blacklist** or **Whitelist** to manage the blacklist or whitelist.

    ![Blacklist and Whitelist Settings](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/2297449951/p72934.png)

    -   For more information about blacklist management, see [Step 7](#step_3n4_8jj_8fq).
    -   For more information about whitelist management, see [Step 8](#step_6d5_urp_2lv).
7.  Manage the blacklist.

    You can perform the following operations:

    -   Add an IP address to the blacklist.

        1.  Click **Manually Add**.

            You can add up to 2,000 IP addresses to the blacklist. If you enter more than one IP address, separate them with spaces or line breaks.

        2.  In the Blacklist Setting dialog box, enter the IP address and set **Blocking Time**.

            ![Blocking period](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/2297449951/p130719.png)

            You can select a blocking period from the **Blocking Time** drop-down list. The blocking period can be from 5 minutes to 7 days. You can also customize a blocking period in seconds.

        3.  Click **Add**.
        After the IP address is added to the blacklist, requests from this IP address are blocked during the specified blocking period. After the specified blocking period expires, this IP address is removed from the blacklist and is no longer blocked. If you want to drop the requests from this IP address, add the IP address to the blacklist again.

    -   Search for IP addresses in the blacklist: Enter a keyword in the search box to search for IP addresses that contain the keyword.
    -   Clear the blacklist: Click **Clear Blacklist** to remove all IP addresses from the blacklist. You can also click **Delete** next to an IP address to remove it from the blacklist.
    -   Download the blacklist.

        1.  Click **Download** to start a download task.
        2.  In the message that appears, click **OK**.

            ![Start the download task](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/2297449951/p69619.png)

        3.  Close the Blacklist and Whitelist Settings panel.
        4.  In the upper-right corner of the page, click the ![Task icon](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/2297449951/p69825.png) icon to expand the task list.
        5.  Find the download task. After the **Status** of the task becomes **Exported**, click **Download** in the Actions column.

            ![Download task in the list](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/2297449951/p69620.png)

        After you download the blacklist to a TXT file, you can open the TXT file and view details about the blacklist.

8.  Manage the whitelist.

    You can perform the following operations:

    -   Add an IP address to the whitelist.

        1.  Click **Manually Add**.
        2.  In the Whitelist Setting dialog box, enter the IP address to be allowed to the whitelist.

            **Note:** You can add up to 2,000 IP addresses to the whitelist. If you enter more than one IP address, separate them with spaces or line breaks.

            ![Whitelist Setting](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/2297449951/p69623.png)

        3.  Click **Add**.
        After the IP address is added to the whitelist, requests from this IP address are directly forwarded to the origin server. The IP addresses in the whitelist remain valid unless you manually remove them.

    -   Search for IP addresses in the whitelist: Enter a keyword in the search box to search for IP addresses that contain the keyword.
    -   Clear the whitelist: Click **Clear Whitelist** to remove all IP addresses from the whitelist. You can also click **Delete** next to an IP address to remove it from the whitelist.
    -   Download the whitelist.

        1.  Click **Download** to start a download task.
        2.  In the message that appears, click **OK**.

            ![Start the download task](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/2297449951/p69619.png)

        3.  Close the Blacklist and Whitelist Settings panel.
        4.  In the upper-right corner of the page, click the ![Task icon](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/2297449951/p69825.png) icon to expand the task list.
        5.  Find the download task. After the **Status** of the task becomes **Exported**, click **Download** in the Actions column.

            ![Download task in the list](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/2297449951/p69620.png)

        After you download the whitelist to a TXT file, you can open the TXT file and view details about the whitelist.


