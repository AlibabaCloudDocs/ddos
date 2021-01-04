# 云外主机获取真实请求来源IP

非阿里云ECS服务器（主要指线下IDC服务器）配置了DDoS高防后，由于业务请求流量先经过DDoS高防清洗过滤再转发到源站服务器，源站无法直接获取真实的请求来源IP。这种情况下建议您使用本文介绍的方法，在源站上配置toa模块来获取真实的请求来源IP。

本文介绍的方法适用于以下操作系统：

-   Redhat Linux
-   CentOS 6.x
-   CentOS 7.x

**说明：**

-   建议您先在测试环境中执行本文描述的操作，观察环境稳定后再在正式环境中进行配置。
-   建议您保留原有的内核，如果出现重启失败，可以切换到原有内核执行系统恢复。

## 操作步骤

1.  根据您的服务器系统类型，下载相应的内核安装文件。

    -   CentOS 7.x系统：[kernel-3.10.0-957.21.3.el7.toa.x86\_64.rpm](http://docs-aliyun.cn-hangzhou.oss.aliyun-inc.com/assets/attach/44520/intl_en/1565937758425/kernel-3.10.0-957.21.3.el7.toa.x86_64.rpm)
    -   CentOS 6.x或Redhat Linux系统：
        -   [kernel-firmware-2.6.32-696.13.2.el6.centos.plus.toa.x86\_64](http://docs-aliyun.cn-hangzhou.oss.aliyun-inc.com/assets/attach/170239/cn_zh/1597160651639/kernel-firmware-2.6.32-696.13.2.el6.centos.plus.toa.x86_64.rpm)
        -   [kernel-2.6.32-696.13.2.el6.centos.plus.toa.x86\_64](http://docs-aliyun.cn-hangzhou.oss.aliyun-inc.com/assets/attach/170239/cn_zh/1597054826193/kernel-2.6.32-696.13.2.el6.centos.plus.toa.x86_64.rpm)
2.  安装内核。

    -   CentOS 7.x系统

        定位到安装文件目录，执行以下命令：

        ```
        sudo yum localinstall kernel-3.10.0-957.21.3.el7.toa.x86_64.rpm
        ```

        **说明：** 建议您使用`yum localinstall`命令安装内核，避免出现依赖问题。您也可以执行`sudo rpm -ivh kernel-3.10.0-957.21.3.el7.toa.x86_64.rpm`命令进行安装。

    -   CentOS 6.x或Redhat Linux系统

        定位到安装文件目录，执行以下命令：

        ```
        sudo rpm -ivh kernel-firmware-2.6.32-696.13.2.el6.centos.plus.toa.x86_64.rpm
        sudo rpm -ivh kernel-2.6.32-696.13.2.el6.centos.plus.toa.x86_64.rpm
        ```

        **说明：**

        -   如果系统中的kernel-firmware版本大于或等于2.6.32-696.13.2.el6.centos.plus.toa，只需要执行上述第二行命令。
        -   如果安装过程中出现依赖错误，可以尝试在`rpm`命令中加上额外参数`--nodeps`。
        -   如果内核版本大于toa内核版本，可以尝试在`rpm`命令中加上额外参数`--force`，进行强制安装。
3.  设置toa模块，开启系统启动时自动加载功能。

    1.  创建文件/etc/sysconfig/modules/toa.modules，并在文件中添加以下内容：

        -   CentOS 7.x系统：

            ```
            #!/bin/bash
            if [ -e /lib/modules/`uname -r`/kernel/net/toa/toa.ko.xz ] ;
            then 
            modprobe toa > /dev/null 2>&1
            fi                            
            ```

        -   CentOS 6.x或Redhat Linux系统：

            ```
            #!/bin/bash
            if [ -e /lib/modules/`uname -r`/kernel/net/toa/toa.ko ] ;
            then 
            modprobe toa > /dev/null 2>&1
            fi                            
            ```

    2.  执行以下命令，授予toa.modules文件可执行权限：

        ```
        sudo chmod +x /etc/sysconfig/modules/toa.modules
        ```

4.  执行`reboot`命令，重启系统。

    安装完成后，主机能够正常获取真实访问源IP。

    如果仍无法获取真实访问源IP，建议您执行`lsmod|grep toa`命令检测toa模块的加载情况。如果toa模块未加载，您可以执行`modprobe toa`命令手动加载。加载成功后，您可以查看服务端访问日志，重新测试主机能否获取真实的访问源IP。


## 相关问题

-   网络连接通过toa模块转换，对性能有多大影响？

    toa模块是部署在旁路的，因此对网络性能几乎没有影响。

-   如果担心加载新的内核模块可能出现稳定性问题怎么办？

    建议您保留原有的内核，如果出现重启失败，可以切换到原有内核执行系统恢复。


