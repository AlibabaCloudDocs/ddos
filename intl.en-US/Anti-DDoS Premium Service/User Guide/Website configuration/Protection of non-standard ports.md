# Protection of non-standard ports {#concept_ild_n1l_l2b .concept}

Anti-DDoS Premium instances with the Standard Function plan support HTTP \(80, 8080\) and HTTPS \(443, 8443\) standard ports to help websites defend against DDoS attacks. The Enhanced Function plan supports non-standard HTTP and HTTPS ports. However, the number of ports used by each protected domain is limited.

**Note:** To add non-standard HTTP or HTTPS ports, make sure that your domain is associated with an Anti-DDoS Premium instance with the Enhanced Function plan.

## Limit on the total number of ports {#section_x4f_41l_l2b .section}

The domains of an Anti-DDoS Premium instance with the Enhanced Function plan can use a maximum of 10 ports.

## Supported ports {#section_z4f_41l_l2b .section}

**Note:** Anti-DDoS Pro Premium instances can only protect supported HTTP and HTTPS ports. The service does not protect or forward traffic from unsupported ports. For example, if an Anti-DDoS Premium instance receives a packet on port 4444, the packet will be discarded.

-   For the **HTTP** and **WebSocket** protocols, instances with the Enhanced Function plan support the following ports:

    80, 83, 84, 88, 89, 800, 808, 1000, 1090, 3333, 3501, 3601, 5000, 5111, 5222, 6001, 6666, 7000, 7001, 7002, 7003, 7004, 7005, 7006, 7009, 7010, 7011, 7012, 7013, 7014, 7015, 7016, 7018, 7019, 7020, 7021, 7022, 7023, 7024, 7025, 7026, 7060, 7070, 7081, 7082, 7083, 7088, 7097, 7777, 7800, 8000, 8001, 8002, 8003, 8008, 8009, 8020, 8021, 8022, 8025, 8026, 8077, 8078, 8080, 8081, 8082, 8083, 8084, 8085, 8086, 8087, 8088, 8089, 8090, 8091, 8106, 8181, 8334, 8336, 8800, 8686, 8787, 8888, 8889, 8999, 9000, 9001, 9002, 9003, 9080, 9200, 9999, 10000, 10001, 10080, 12601, 86, 9021, 9023, 9027, 9037, 9081, 9082, 9201, 9205, 9207, 9208, 9209, 9210, 9211, 9212, 9213, 48800, 87, 97, 7510, 9180, 9898, 9908, 9916, 9918, 9919, 9928, 9929, 9939, 28080, 33702

-   For the **HTTPS** and **WebSockets** protocols, instances with the Enhanced Function plan support the following ports:

    443, 4443, 5443, 6443, 7443, 7988, 8443, 9443, 8553, 8663, 9553, 9663, 10050, 10443, 18980, 30050


