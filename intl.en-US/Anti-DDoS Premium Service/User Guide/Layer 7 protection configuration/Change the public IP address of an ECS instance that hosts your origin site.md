# Change the public IP address of an ECS instance that hosts your origin site {#task673 .task}

If the IP address of your origin site has been exposed, we recommend that you change the public IP address of the Alibaba Cloud ECS instance to prevent attackers from bypassing Anti-DDoS Premium and directly attacking the origin site. You can change the IP address of the back-end ECS instance in the Anti-DDoS Premium console. Each Alibaba Cloud account can change this IP address 10 times at most.

**Note:** You can only change the IP address of an ECS instance that uses the public IP address on the classic network.

1.  Log on to the [Anti-DDoS Premium console](https://yundun.console.aliyun.com/?p=ddosdip).
2.  In the left-side navigation pane, choose **Provisioning** \> **Website**.
3.  Click **Change ECS IP**. 

    **Notice:** During the IP change process, the business on your ECS instance is interrupted for several minutes. We recommend that you back up your data before performing this operation.

4.  Stop the ECS instance before changing its IP address. Click **Go to ECS** in the Change ECS IP dialog box. In the ECS console, stop the ECS instance whose IP address needs to be changed. 

    **Note:** If you have stopped the ECS instance whose IP address needs to be changed, skip this step.

    1.  Find the target ECS instance in the instance list and click its ID.
    2.  On the instance details page, click **Stop**.
    3.  Select a stop mode and click **OK**. 

        **Notice:** Exercise caution when you stop ECS instances. To ensure security, you must enter the verification code sent to your mobile phone.

    4.  Wait until the ECS instance status changes to **Stopped**.
5.  Return to the Change ECS IP dialog box, enter **ECS Instance ID**, and click **Next**.
6.  Confirm that the current ECS instance information is correct \(especially the ECS IP address\). Click **Release IP Address**.
7.  After the IP address of the ECS instance is released, click **Next**. A new IP address is automatically assigned to the ECS instance.
8.  After the IP address of the ECS instance is changed, click **OK** to make the configurations take effect. 

    **Note:** After the IP address is changed, you must associate the new IP address with Anti-DDoS Premium.


