# Obtain the actual source IP addresses of requests to the origin server that is not deployed on Alibaba Cloud

If you use a server in your on-premises data center as the origin server and use Anti-DDoS Pro or Anti-DDoS Premium to protect your service, requests are first scrubbed by Anti-DDoS Pro or Anti-DDoS Premium and then forwarded to the origin server. The origin server cannot directly obtain the actual source IP addresses of the requests. This topic describes how to obtain the actual source IP addresses by configuring the TOA module on the origin server.

The method in this topic applies to the following operating systems:

-   Red Hat Enterprise Linux
-   CentOS 6.x
-   CentOS 7.x

**Note:**

-   You can use the method described in this topic in a test environment. If the service stably runs in the test environment, use the method in the production environment.
-   We recommend that you keep the original kernel of the operating system. If a restart fails, switch to the original kernel to restore your service.

## Procedure

1.  Download the required kernel installation file based on the operating system of your server.

    -   CentOS 7.x: [kernel-3.10.0-957.21.3.el7.toa.x86\_64.rpm](http://docs-aliyun.cn-hangzhou.oss.aliyun-inc.com/assets/attach/44520/intl_en/1565937758425/kernel-3.10.0-957.21.3.el7.toa.x86_64.rpm)
    -   CentOS 6.x or Red Hat Enterprise Linux:
        -   [kernel-firmware-2.6.32-696.13.2.el6.centos.plus.toa.x86\_64](http://docs-aliyun.cn-hangzhou.oss.aliyun-inc.com/assets/attach/170239/cn_zh/1597160651639/kernel-firmware-2.6.32-696.13.2.el6.centos.plus.toa.x86_64.rpm)
        -   [kernel-2.6.32-696.13.2.el6.centos.plus.toa.x86\_64](http://docs-aliyun.cn-hangzhou.oss.aliyun-inc.com/assets/attach/170239/cn_zh/1597054826193/kernel-2.6.32-696.13.2.el6.centos.plus.toa.x86_64.rpm)
2.  Install the kernel.

    -   CentOS 7.x

        Go to the directory of the installation file and run the following command:

        ```
        sudo yum localinstall kernel-3.10.0-957.21.3.el7.toa.x86_64.rpm
        ```

        **Note:** We recommend that you use the `yum localinstall` command to install the kernel to avoid dependency issues. You can also use the `sudo rpm -ivh kernel-3.10.0-957.21.3.el7.toa.x86_64.rpm` command.

    -   CentOS 6.x or Red Hat Enterprise Linux

        Go to the directory of the installation file and run the following commands:

        ```
        sudo rpm -ivh kernel-firmware-2.6.32-696.13.2.el6.centos.plus.toa.x86_64.rpm
        sudo rpm -ivh kernel-2.6.32-696.13.2.el6.centos.plus.toa.x86_64.rpm
        ```

        **Note:**

        -   If kernel-firmware runs 2.6.32-696.13.2.el6.centos.plus.toa or later, use only the preceding second command.
        -   If dependency issues occur during installation, add the `--nodeps` parameter to the `rpm` command.
        -   If the kernel version is later than the TOA version, add the `--force` parameter to the `rpm` command to forcibly install the kernel.
3.  Configure the TOA module to make sure that it is automatically loaded when the operating system is started.

    1.  Create the /etc/sysconfig/modules/toa.modules file and add the following content to the file:

        -   CentOS 7.x

            ```
            #! /bin/bash
            if [ -e /lib/modules/`uname -r`/kernel/net/toa/toa.ko.xz ] ;
            then 
            modprobe toa > /dev/null 2>&1
            fi                            
            ```

        -   CentOS 6.x or Red Hat Enterprise Linux:

            ```
            #! /bin/bash
            if [ -e /lib/modules/`uname -r`/kernel/net/toa/toa.ko ] ;
            then 
            modprobe toa > /dev/null 2>&1
            fi                            
            ```

    2.  Run the following command to grant execute permissions to the toa.modules file:

        ```
        sudo chmod +x /etc/sysconfig/modules/toa.modules
        ```

4.  Run the `reboot` command to restart the operating system.

    After the installation is complete, the origin server can obtain the actual source IP addresses of requests.

    If the actual source IP addresses are not obtained, run the `lsmod|grep toa` command to check the loading status of the TOA module. If the TOA module is not loaded, run the `modprobe toa` command to manually load it. After the TOA module is loaded, you can view server access logs and test whether the origin server can obtain the actual source IP addresses again.


## FAQ

-   Does network performance deteriorate if I use the TOA module?

    No, the network performance does not deteriorate. The TOA module is deployed in bypass mode and has little impact on network performance.

-   What do I do if the kernel is unstable after I load the TOA module?

    We recommend that you keep the original kernel of the operating system. If the restart fails, switch to the original kernel to restore your service.


