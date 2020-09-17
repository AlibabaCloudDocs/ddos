# 502 error reported after configuring Anti-DDoS Pro

This topic describes common causes and solutions to the 502 error reported when you attempt to access a domain name that is under the protection of Anti-DDoS Pro.

## Anti-DDoS Pro IP blocked

-   **Symptoms**

    Anti-DDoS Pro acts as a reverse proxy between the client and origin site. This functionality makes the IP address of the origin site invisible to clients and all requests accessing the origin “looks like” coming from Anti-DDoS Pro IP addresses.

    In addition, request traffic from each Anti-DDoS IP address is considerably large in amount, which makes the Anti-DDoS IP addresses much more suspicious to the origin site. However, if the source station IP is exposed, the client can request direct access to the source station, this bypasses the protection provided by high-security IP services.

-   **Analysis**

    In such cases, unless otherwise configured, the firewall or other security strategies in the origin site may regard Anti-DDoS IP addresses as abnormal or malicious visitors and thus blocks or imposes traffic restrictions on them. When Anti-DDoS Pro IP addresses are blocked or are subject to traffic restrictions, access requests passing through Anti-DDoS Pro are returned 502 errors.

-   **Resolution**

    You can resolve this issue by allowing all Anti-DDoS Pro IP addresses to access the origin site. The following methods are available to allow Anti-DDoS Pro IP addresses on the origin site:

    -   See [How to view the Anti-DDoS Pro IP addresses](/intl.en-US/Anti-DDoS Pro Service (Old)/FAQ/How to view the Anti-DDoS Pro IP addresses?.md) to obtain all Anti-DDoS Pro IP addresses and add them to the whitelist of your origin site’s firewall and other host security protection software \(such as a dongle\).
    -   Disable the firewall and other host security protection software in the origin site.

## Origin site exception

Origin site exception may cause response timeout when proceeding with an Anti-DDoS Pro request. Common origin site exceptions include the following cases:

-   The origin site IP address is exposed and attacked, leading to an origin site crash.
-   Physical failure in the origin site’s server data center.
-   Apache, Nginx, and other Web programs running on the origin site encounter a problem.
-   High memory and CPU occupation on the server causes a sharp decrease in performance.
-   The uplinks of the origin site are congested.

**Analysis**

Modify your local hosts file to redirect the domain name to the origin site IP address. If the origin site IP address cannot be accessed, ping the origin site IP address to check if any packet loss exists. If a packet loss exits, check if the telnet times out when attempting to access the server. If yes, chances are that the 502 error is caused by an origin site exception.

**Resolution**

Follow these steps to resolve this issue:

1.  Check the origin site traffic and the request volume for a sharp increase, and compare the result with the Security Report data from the Anti-DDoS Pro console. If the origin site is under heavy traffic attack, but the Anti-DDoS Pro console shows no exceptions, it means that the attackers may have bypassed the Anti-DDoS Pro IP address, and attacked the origin site directly. In this case, we recommend that you [Change the origin site IP address](/intl.en-US/Anti-DDoS Pro Service (Old)/User Guide/Instance management/Change ECS IP.md).
2.  After excluding the possibility of attacks, check the origin site server’s process status, CPU/memory usage, bandwidth usage of the data center, and so on. In case of exceptions, we recommend that you contact server technicians or data center personnel to help you identify and fix the problem.
3.  If only a limited number of clients have reported the 502 error, we recommend that you submit a ticket along with the clients’ IP addresses and the time of error occurrence information. On the basis of information provided, the Alibaba Cloud technical professionals work on your ticket, take relevant steps, and assist to identify and resolve the issue.

## Network congestion or jitter

Apart from the preceding two factors, occasional local network jitter, operator line failure, and some other factors may also cause the 502 error. Open a ticket to report this issue. The Alibaba Cloud technical professionals can also help you with the link quality monitoring information.

