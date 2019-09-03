# 启用AI智能防护 {#task_183121 .task}

AI智能防护基于阿里云的大数据能力，通过智能分析引擎自学习业务流量基线，动态调整防护模型，及时帮助您发现并阻断恶意攻击，例如恶意Bot、HTTP flood攻击等。

**说明：** 开启AI智能防护时，自动下发的智能规则无法手动删除。若智能防护规则不适合您的业务场景，建议您关闭智能防护开关。关闭AI智能防护后，AI产生的防护规将即时清空。

1.  登录[云盾新BGP高防管理控制台](https://yundun.console.aliyun.com/?p=ddoscoo&__consolePageCode=ddoscoo)。
2.  定位到**防护** \> **防护设置** \> **CC防护策略**。
3.  选择需要设置AI智能防护的域名（以example.aliyundemo.com为例），开启AI智能防护开关。 

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/156918/156747980044284_zh-CN.png)


界面提示：“修改AI智能防护状态成功”，表示该功能已经开启。

开启AI智能防护后，当检测到恶意攻击行为时，高防实例自动下发防护规则，具体规则条目在精准防护控制模块中查看，规则名称以“smartcc\_” 开头。如下图所示：

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/156918/156747980044285_zh-CN.png)

**说明：** 智能防护下发的规则存在有效期，超过有效期，防护规则会自动失效并清除。

