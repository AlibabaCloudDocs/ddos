# 为遭受攻击的IP开通DDoS防护包 {#task1424 .task}

阿里云默认为您购买的所有具备公网IP的产品（例如，ECS云服务器、SLB负载均衡、EIP弹性公网IP、Web应用防火墙等）提供DDoS基础防护服务。当这些产品的公网IP遭受超过默认防护能力的DDoS攻击时，您可以立即付费开通DDoS防护包，利用该公网IP所在地域的最大DDoS攻击防护能力防护攻击，保障您的业务免受攻击影响。

在您购买开通DDoS防护包前，您应确认以下信息：

-   遭受攻击的IP地址。
-   遭受攻击的IP所在地域。

    **说明：** 目前，DDoS防护包尚未在所有地域开通。因此您需要确认遭受攻击的IP所在的地域已开通DDoS防护包服务。

-   遭受的攻击流量类型（IPv4或IPv6）。

确认您正遭受攻击的IP所在的地域已开通DDoS防护包服务，参考以下操作步骤，购买DDoS防护包并为该IP配置防护。

**注意事项**：

DDoS防护包企业版提供全力防护的弹性防护能力。当遭受攻击时，自动调度该企业版DDoS防护包实例所在地域的阿里云最大DDoS防护能力提供全力防护。

DDoS防护包的弹性防护将消耗抗D流量包中的流量，不会产生任何后付费。在您购买DDoS防护包实例时，您将获赠包含一定流量的抗D流量包用于抵扣DDoS防护包所消耗的弹性防护流量。当抗D流量包中的流量耗尽后，DDoS防护包实例的弹性阈值将自动下调为保底防护带宽的20G，您需要单独[购买抗D流量包](cn.zh-CN/DDoS防护包/产品定价/购买抗D流量包.md#)后重新恢复DDoS防护包的弹性防护能力。

1.  登录[阿里云DDoS防护包购买页面](https://common-buy.aliyun.com/?commodityCode=ddosbgp#/buy)。
2.  参考[购买DDoS防护包](cn.zh-CN/DDoS防护包/产品定价/购买DDoS防护包.md#)中的操作步骤，选择**防护包类型**、**地域**、**IP类型**，购买DDoS防护包。 

    **说明：** 您所选择的DDoS防护包的地域应与您需要防护的ECS、SLB、EIP等产品实例所在的地域一致。

3.  购买DDoS防护包实例并完成支付后，登录[云盾DDoS防护管理控制台](https://yundunnext.console.aliyun.com/?p=ddosbgp)。
4.  定位到**防护包** \> **实例** 页面，参考[添加防护对象IP](cn.zh-CN/DDoS防护包/用户指南/添加防护对象IP.md#)将需要防护的IP添加至已购买的DDoS防护包实例中进行防护。

防护IP添加成功后，该IP即可享受所绑定的DDoS防护包实例的防护能力。在[云盾DDoS防护管理控制台](https://yundunnext.console.aliyun.com/?p=ddosnext)的**基础防护** \> **实例**页面，您可以查看到该IP的防护阈值已经提升为所绑定的DDoS防护包实例的防护能力。

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79483/155930745634780_zh-CN.png)

