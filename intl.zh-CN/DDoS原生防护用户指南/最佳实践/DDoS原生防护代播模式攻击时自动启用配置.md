# DDoS原生防护代播模式攻击时自动启用配置

本文介绍了使用DDoS原生防护代播模式自动防御大流量DDoS攻击的最佳实践，适用于已经开通了DDoS原生防护代播模式的用户在阿里云IP资产受到攻击时，通过API接口自动启用DDoS原生防护代播模式的场景。

-   已开通DDoS原生防护企业版实例。更多信息，请参见[开通DDoS原生防护企业版](/intl.zh-CN/DDoS原生防护用户指南/开通DDoS原生防护企业版.md)。
-   已联系销售人员购买了DDoS原生防护代播版实例。
-   已在云监控服务中创建了报警联系人和联系人组。更多信息，请参见[创建报警联系人或报警联系组](/intl.zh-CN/报警服务/报警联系人/创建报警联系人或报警联系组.md)。

DDoS原生防护代播版可以为海外云下IDC、小型运营商、阿里云海外客户以及有自己BGP网络的客户提供阿里云的DDoS防护，且防护过程不需要改变原有业务IP地址和网络架构。下图描述了DDoS原生防护代播版的防护原理。

![代播模式架构图](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/6939758951/p130642.png)

原理说明：

-   正常流量或小流量攻击：流量直接访问阿里云DDoS原生防护本地机房，无额外延迟增加，可以防御小流量攻击。
-   发生DDoS攻击时：清洗中心宣告路由，流量由全球清洗中心分布式清洗，延迟略有增加，但防护能力可以增加到Tbps级别。

本文将指导您使用云监控的报警功能设置报警规则，监控DDoS原生防护本地机房的DDoS攻击；如果发生DDoS攻击，通过API接口调用开启DDoS原生防护代播实例的牵引防护，并在攻击结束后，停止牵引防护。

**说明：** 本文中所有用到API请求参数示例的地方，全部使用`<参数描述>`表示，例如要求传入原生防护代播版实例ID的地方，表示为`InstanceId=<yourOnDemandInstanceId>`。

具体操作中，请使用真实的参数值替换`<参数描述>`，例如您需要联系销售人员获取您的原生防护代播实例的ID（InstanceId），并替换`<yourOnDemandInstanceId>`。

1.  通过云监控设置DDoS原生防护黑洞事件的报警通知，监控DDoS原生防护本地清洗中心的黑洞、清洗事件。

    1.  登录[云监控控制台](https://cloudmonitor.console.aliyun.com/#/home/ecs)。

    2.  在左侧导航栏，单击**报警服务** \> **报警规则**。

    3.  单击**事件报警**页签。

    4.  单击**创建事件报警**。

    5.  在**创建/修改事件报警**页面，配置以下事件报警参数。

        ![原生防护告警监控](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/6939758951/p130616.png)

        |参数|说明|
        |--|--|
        |**报警规则名称**|为当前报警规则的命名。示例：原生防护DDoS攻击事件报警。|
        |**事件类型**|选中**系统事件**。|
        |**产品类型**|选择**DDoS防护包**。|
        |**事件等级**|选择**全部级别**。|
        |**事件名称**|选择**黑洞**和**清洗**。|
        |**资源范围**|选择**全部资源**。|
        |**报警通知**|选中**报警通知**，并选择要接收报警通知的报警**联系人组**和一种**通知方式**。|

    6.  单击**确定**。

    成功创建报警规则后，报警规则自动生效，一旦DDoS原生防护实例上发生DDoS攻击，报警规则中指定的联系人组会第一时间收到报警通知。您可以在**事件报警**规则列表中查看和管理报警规则。更多信息，请参见[创建事件报警规则](/intl.zh-CN/报警服务/报警规则/创建事件报警规则.md)。

    ![事件报警规则](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/6939758951/p130622.png)

2.  发生DDoS攻击（即收到黑洞、清洗事件报警通知）时，调用[ModifyOnDemaondDefenseStatus](/intl.zh-CN/API参考/DDoS原生防护/2017-11-20版本/代播实例/ModifyOnDemaondDefenseStatus.md)接口开启DDoS原生防护代播实例的流量牵引防护，将流量牵引至阿里云全球Anycast清洗中心。

    您需要传入以下请求参数：

    ```
    ?Action=ModifyOnDemaondDefenseStatus
    &DdosRegionId=<yourInstanceRegionId>
    &DefenseStatus=Defense
    &InstanceId=<yourOnDemandInstanceId>
    ```

3.  解除DDoS原生防护企业版实例的黑洞状态。

    -   如果DDoS原生防护企业版实例未触发黑洞状态，请忽略该步骤。
    -   如果DDoS原生防护企业版实例处于黑洞状态，您可以在开启流量牵引防护约10秒以后，调用[DeleteBlackhole](/intl.zh-CN/API参考/DDoS原生防护/2018-07-20版本/防护/DeleteBlackhole.md)接口解除DDoS原生防护企业版实例的黑洞状态。

        您需要传入以下请求参数：

        ```
        ?Action=DeleteBlackhole
        &InstanceId=<yourOnDemandInstanceId>
        &Ip=<yourOnDemandInstanceIp>
        ```

4.  调用[DescribeTopTraffic](/intl.zh-CN/API参考/DDoS原生防护/2017-11-20版本/代播实例/DescribeTopTraffic.md)接口查询DDoS攻击是否结束。

    您需要传入以下请求参数：

    ```
    ?Action=DescribeTopTraffic
    &Ipnet=<onDemandInstanceIpnetToQuery>
    &InstanceId=<yourOnDemandInstanceId>
    &StartTime=<startTimeToQuery>
    &EndTime=<endTimeToQuery>             
    ```

    如果返回的AttackBps（攻击流量大小，单位：Kbps）小于300000，并持续30分钟以上，则表示DDoS攻击已经结束。

5.  确认DDoS攻击事件结束后，在业务低峰时段调用[ModifyOnDemaondDefenseStatus](/intl.zh-CN/API参考/DDoS原生防护/2017-11-20版本/代播实例/ModifyOnDemaondDefenseStatus.md)接口停止DDoS原生防护代播实例的流量牵引防护。

    **说明：** 建议您在业务低峰时段调用停止牵引，这样可以减少流量切换带来的影响。

    您需要传入以下请求参数：

    ```
    ?Action=ModifyOnDemaondDefenseStatus
    &DdosRegionId=<yourDdosRegionId>
    &DefenseStatus=UnDefense
    &InstanceId=<yourOnDemandInstanceId>
    ```


