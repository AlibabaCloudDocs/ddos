# CNAME复用

如果您在一个服务器上有多个网站域名需要接入DDoS高防（国际），您可以申请开通CNAME复用，实现只添加一次高防配置，而使高防配置的CNAME地址供多个域名复用。开启CNAME复用后，您只需将同服务器上多个域名的解析指向高防CNAME地址，即可将多个域名接入高防，无需为每个域名分别添加高防配置。

## 前提条件

已提交[工单](https://workorder-intl.console.aliyun.com/?#/ticket/add/?productId=80)申请开放CNAME复用功能。本文操作描述建立在已开放CNAME复用的前提下。

**说明：** 仅DDoS高防（国际）服务支持CNAME复用。如果您使用DDoS高防（新BGP）服务，则暂时不支持使用CNAME复用。

## 使用场景

CNAME复用适用于以下场景，以避免对多个域名重复添加高防配置：

-   场景1：代理商、ISV、分销商有大量域名（大部分域名的源站是同一个服务器）需要接入DDoS高防，且域名有频繁增删。
-   场景2：同一个业务使用大量不同一级域名做推广、SEO。
-   场景3：同一个业务使用大量备用域名。

## 使用限制

下表描述了CNAME复用的使用限制。

|限制条件|说明|
|----|--|
|协议类型|支持HTTP、HTTPS协议。|
|源站|复用CNAME的一组域名必须对应同一个源站。|

## 开启CNAME复用

CNAME复用支持结合流量调度器使用，在开启CNAME复用时，您根据需要选择是否结合流量调度器。关于流量调度器的说明，请参见[概述](/intl.zh-CN/DDoS高防（新BGP&国际）用户指南/接入DDoS高防/流量调度器/概述.md)。

-   如果结合流量调度器使用，则需要关联对应的通用联动规则，且域名解析中将复用联动规则的CNAME地址。
-   如果不使用流量调度器，则域名解析中将复用高防网站配置的CNAME地址。

为便于后续操作描述，做以下假设：

-   源站服务器有两个IP：1.1.1.1、2.2.2.2。
-   源站（1.1.1.1）有三个域名：a.test、b.test、c.test。

以下操作描述了使用CNAME复用功能，将一个源站IP（1.1.1.1）下多个域名（a.test、b.test、c.test）接入DDoS防护（国际）的配置方法。

1.  在**域名接入**配置中开启Cname Reuse。

    1.  登录[DDoS高防控制台](https://yundun.console.aliyun.com/?p=ddoscoo)。

    2.  在顶部导航栏，选择**非中国内地**地域。

    3.  在左侧导航栏，单击**接入管理** \> **域名接入**。

    4.  添加一个网站配置或者编辑已有网站配置，在网站配置中开启**Cname Reuse**。关于添加网站配置的具体操作，请参见[添加网站](/intl.zh-CN/DDoS高防（新BGP&国际）用户指南/接入DDoS高防/网站配置/添加网站.md)。

        示例：源站IP是1.1.1.1，网站是a.test（也可以是b.test、c.test）。

        ![网站配置,CnameReuse](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/7641919951/p65277.png)

2.  选择是否结合流量调度器及更新域名CNAME解析。

    在启用CnameReuse时，您需要选择是否结合流量调度器。

    -   不使用流量调度器
        1.  在选择流量调度器对话框中，选择**不使用流量调度器**，并单击**确定**。

            ![不使用流量调度器](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/7641919951/p65278.png)

        2.  成功添加网站配置后，记录网站配置的CNAME地址。
        3.  前往域名服务商，更新源站（1.1.1.1）对应的所有网站（a.test、b.test、c.test）的域名解析，应用CNAME解析并将记录值更新为网站配置的CNAME地址。
    -   使用流量调度器
        1.  在选择流量调度器对话框中，选择**使用流量调度器**，并选择对应的流量调度规则，单击**确定**。

            ![使用流量调度器](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/7641919951/p65279.png)

            流量调度器规则应联动网站配置中用到的源站IP（1.1.1.1）和DDoS高防IP。若您还未创建对应规则，请单击**新建流量调度规则**添加对应规则（见下图示例），再选择应用规则。

            **说明：** 联动规则中的DDoS高防IP必须和网站配置中关联的DDoS高防实例一致。

            ![流量调度器规则](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/7641919951/p65248.png)

        2.  成功选择流量调度器规则后，记录调度规则的CNAME地址。

            ![防护规则cname](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/7641919951/p65286.png)

        3.  前往域名服务商，更新源站（1.1.1.1）对应的所有网站（a.test、b.test、c.test）的域名解析，应用CNAME解析并将记录值更新为调度规则的CNAME地址。
3.  如果还需要为不同源站（2.2.2.2）对应的域名接入DDoS防护，请重复步骤1~2进行配置。


## 关闭CNAME复用

如果您不再需要使用CNAME复用，您可以在网站配置中关闭Cname Reuse。

**说明：** 关闭Cname Reuse前，请确保所有复用高防CNAME的域名已不再解析到高防，否则关闭功能后会导致网站流量转发失败。

1.  登录[DDoS高防控制台](https://yundun.console.aliyun.com/?p=ddoscoo)。

2.  在顶部导航栏，选择**非中国内地**地域。

3.  在左侧导航栏，选择**接入管理** \> **域名接入**。

4.  编辑已有网站配置，并在网站配置中关闭**Cname Reuse**。

5.  根据需要选择是否保留网站配置和防护调度规则。

    -   保留网站配置，则网站配置中的转发逻辑继续生效。
    -   保留防护调度规则，则流量调度器继续生效。

