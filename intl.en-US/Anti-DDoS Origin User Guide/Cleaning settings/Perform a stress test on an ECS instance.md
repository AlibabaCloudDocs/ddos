# Perform a stress test on an ECS instance

Anti-DDoS Origin Basic provides protection against DDoS attacks for Elastic Compute Service \(ECS\) instances free of charge. By default, if the network bandwidth of an ECS instance exceeds 180 Mbit/s, the number of packets exceeds 30,000 per second, or the number of HTTP requests exceeds 480 per second, Anti-DDoS Origin Basic automatically scrubs traffic. The preceding values may vary based on instance types.

Before you perform a stress test on an ECS instance, you must log on to the [Anti-DDoS console](https://yundun.console.aliyun.com/?p=ddosnext) to change the protection threshold for the ECS instance. For more information, see [Configure a cleaning threshold](/intl.en-US/Anti-DDoS Origin User Guide/Cleaning settings/Configure a cleaning threshold.md).

**Note:** We recommend that you do not increase the request volume more than 100 times per minute during the stress test.

