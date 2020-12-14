# 修改CNAME解析接入流量调度器

通过流量调度器添加调度规则后，您必须更新域名的DNS解析（CNAME记录），将网站业务流量切换至流量调度器，才能使调度规则生效。本文以网站域名解析托管在阿里云云解析DNS为例，介绍了手动修改域名解析（CNAME记录）以接入流量调度器的操作方法。

已通过流量调度器添加调度规则。更多信息，请参见[概述](/cn.zh-CN/DDoS高防（新BGP&国际）用户指南/接入DDoS高防/流量调度器/概述.md)。

通过流量调度器添加调度规则后，流量调度器会为规则生成一个CNAME地址。修改CNAME解析接入流量调度器时，您需要将网站域名的解析（CNAME记录）设置为流量调度器生成的CNAME地址。

以下操作描述建立在您的域名DNS托管在[阿里云云解析DNS](https://wanwang.aliyun.com/domain/dns)。

如果您使用其他DNS服务商的域名解析服务，请登录服务商系统修改网站域名的解析记录，下文内容仅供参考。

假设调度规则对应的网站域名为`bgp.gftest.top`。以下操作示例描述了在云解析DNS控制台修改、新增域名解析的具体操作。

1.  登录[阿里云云解析DNS控制台](https://dns.console.aliyun.com)。

2.  在域名解析页面，定位到要操作的域名（本示例中为`gftest.top`），单击其操作列下的**解析设置**。

    ![解析设置](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/0707947061/p45866.png)

3.  在解析设置页面，定位到要修改的解析记录（本示例中对应主机记录为**bgp**的A记录或CNAME记录），单击其操作列下的**修改**。

    **说明：** 如果要操作的解析记录不在记录列表中，您可以单击**添加记录**。

    ![修改记录](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/0707947061/p45867.png)

4.  在修改记录（或添加记录）对话框，选择**记录类型**为**CNAME**，并将**记录值**修改为流量调度器的CNAME地址。

    ![修改记录](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/0707947061/p45868.png)

    您可以登录[DDoS高防控制台](https://yundun.console.aliyun.com/?p=ddoscoo)，在**接入管理** \> **流量调度器**页面，查询流量调度器的CNAME地址。

    ![通用联动](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/9017947061/p89082.png)

5.  单击**确认**，等待修改后的解析设置生效。

6.  使用浏览器测试网站访问是否正常。

    如果网站访问出现异常，请参见[业务接入高防后存在卡顿、延迟、访问不通等问题]()。


