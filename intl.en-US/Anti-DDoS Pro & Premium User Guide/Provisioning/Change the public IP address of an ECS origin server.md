# Change the public IP address of an ECS origin server

If the IP address of your origin server is exposed, we recommend that you change the public IP address of your Elastic Compute Service \(ECS\) instance to prevent attackers from bypassing Anti-DDoS Pro or Anti-DDoS Premium to attack the origin server. You can change the public IP address of an ECS instance in the Anti-DDoS Pro or Anti-DDoS Premium console up to 10 times.

1.  Log on to the [Anti-DDoS Pro console](https://yundun.console.aliyun.com/?p=ddoscoo).

2.  In the top navigation bar, select the region where your instance resides.

    -   **Mainland China**: If you select this region, the **Anti-DDoS Pro console** appears.
    -   **Outside Mainland China**: If you select this region, the **Anti-DDoS Premium console** appears.
    You can switch the region to configure and manage Anti-DDoS Pro or Anti-DDoS Premium instances. Make sure that you select the required region when you use Anti-DDoS Pro or Anti-DDoS Premium.

3.  In the left-side navigation pane, choose **Provisioning** \> **Website Config**.

4.  In the upper-right corner of the **Website Config** page, click **Change ECS IP**.

5.  In the **Change ECS IP** dialog box, read the tips and click **Next**.

    **Note:** If you change the public IP address of an ECS instance, your service is interrupted for a few minutes. We recommend that you back up your data before you perform this operation.

    ![Change ECS IP dialog box](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/3337168061/p189933.png)

6.  Stop your ECS instance.

    To change the IP address of your ECS instance, you must stop the instance. If you have stopped your ECS instance, go to the next step.

    If you do not stop your ECS instance, click **Go to ECS** in the **Change ECS IP** dialog box. Then, stop your ECS instance in the [ECS console](https://ecs.console.aliyun.com/). For more information about how to stop an ECS instance, see [Stop an instance](/intl.en-US/Instance/Manage instances/Stop an instance.md).

    ![Go to ECS](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/3337168061/p189934.png)

7.  Return to the **Change ECS IP** dialog box, specify **ECS Instance ID**, and then click **Next**.

8.  After the IP address is released, click **Next**. Anti-DDoS Pro or Anti-DDoS Premium automatically assigns a new IP address to the ECS instance.

9.  Click **OK**.

    **Note:** After you change the IP address of an ECS origin server, set up Anti-DDoS Pro or Anti-DDoS Premium and do not expose the new IP address.


