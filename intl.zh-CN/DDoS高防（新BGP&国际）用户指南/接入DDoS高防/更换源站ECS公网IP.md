# 更换源站ECS公网IP

如果您的源站ECS实例的公网IP已不慎暴露，建议您更换ECS实例的公网IP，防止黑客绕过DDoS高防直接攻击源站。您可以在DDoS高防控制台更换ECS实例的公网IP。每个阿里云账号最多可以更换10次。

1.  登录[DDoS高防控制台](https://yundun.console.aliyun.com/?p=ddoscoo)。

2.  在顶部菜单栏左上角处，选择服务所在地域：

    -   **中国内地**：选择该地域将跳转到**DDoS高防（新BGP）**控制台。
    -   **非中国内地**：选择该地域将跳转到**DDoS高防（国际）**控制台。
    您可以通过切换地域分别管理和配置DDoS高防（新BGP）和DDoS高防（国际）实例。在使用DDoS高防服务时，请确认您已选择正确的地域。

3.  在左侧导航栏，选择**接入管理** \> **域名接入**。

4.  在**域名接入**页面右上方，单击**更换ECS IP**。

5.  在**更换ECS IP**对话框，单击**知道了，下一步**。

    **说明：** 更换ECS IP会使您的业务暂时中断几分钟，建议您在操作前先备份好数据。

    ![更换ECS IP](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/7865147061/p189933.png)

6.  停止ECS实例。

    更换ECS IP需要停止ECS实例。如果您已经停止了需要更换IP的ECS实例，请直接执行下一步。

    如果您还没有停止ECS实例，则可以在**更换ECS IP**对话框，单击**前往ECS**，并在[ECS控制台](https://ecs.console.aliyun.com/)停止需要更换IP的ECS实例。关于停止ECS实例的具体操作，请参见[停止实例](/intl.zh-CN/实例/管理实例/停止实例.md)。

    ![前往ECS](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/7865147061/p189934.png)

7.  在**更换ECS IP**对话框，输入**ECS实例ID**，并单击**下一步**。

8.  成功释放原IP后，单击**下一步**，为ECS实例自动分配新的IP。

9.  ECS IP更换成功后，单击**确认**。

    **说明：** 更换IP成功后，请将新的IP隐藏在DDoS高防后面，不要对外暴露。


