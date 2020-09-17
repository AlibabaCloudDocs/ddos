# \[System upgrade\] Anti-DDoS Pro is upgraded on December 15, 2019

**Applicable services**: Anti-DDoS Pro

**Time**: \(UTC+8\) 06:00:00 to 09:00:00 on December 15, 2019

**Description**: The software of data centers where Anti-DDoS Pro is deployed is upgraded.

**Impact**: After the upgrade, the following back-to-origin CIDR blocks are added to Anti-DDoS Pro:

```
47.113.25.0/24
```

If you use Anti-DDoS Pro and have configured access control policies on your origin server, update the whitelist of your origin server to allow the preceding back-to-origin CIDR blocks. This prevents the back-to-origin IP addresses of Anti-DDoS Pro from being blocked during geo-disaster recovery.

During the upgrade, your services are not affected. In some cases, the origin server is configured with strong security verification policies and the IP addresses need to be authenticated again. This breaks the TCP-based connections two to four times. Transient disconnection errors have little impact on services that use short-lived connections and persistent connections that can be automatically reestablished. Make sure that your services support automatic reconnection to ensure fault tolerance.

**Customer service**: We apologize for any inconvenience caused. If you require any further assistance, we recommend that you contact [customer service](https://www.aliyun.com/contact?from=announcement).

