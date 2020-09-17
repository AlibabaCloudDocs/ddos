# How do I enable WebSocket?

This topic describes how to enable WebSocket when you add domain names to an Anti-DDoS Pro or Anti-DDoS Premium instance.

## Introduction to WebSocket and WebSocket Secure

WebSocket is a new HTML5 protocol for full-duplex communication between clients and servers. It supports real-time communication and reduces the consumption of server resources and bandwidth. Similar to HTTP, WebSocket uses an established TCP connection to transmit data. However, it is different from HTTP.

One major difference between WebSocket and HTTP is that WebSocket is a two-way communication protocol. After a connection is established, a WebSocket server and client can send or receive data between each other similar to a socket. The WebSocket server and client must complete a handshake to establish a WebSocket connection.

WebSocket Secure is the encrypted version of WebSocket.

## Background information about WebSocket and WebSocket Secure

New web applications emerge as the Internet develops. These applications, such as live video streaming and online chat rooms, require that servers must have real-time pushing capabilities. To implement pushing, a large number of websites used the polling technique. With the polling technique, the browser sends an HTTP request to the server at regular intervals, such as every second, and the server returns the latest data to the browser. One disadvantage of this technique is that bandwidth resources are wasted. The browser must constantly send requests to the server, and the HTTP request header is long and doesn't contain much valid data.

To solve this problem, HTML5 defines WebSocket, which helps save server and bandwidth resources and facilitates real-time communication. WebSocket supports full-duplex communication between clients and servers and allows a server to send requests to a client.

The following figure shows how a client interacts with a server by using WebSocket.

![WebSocket](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/4261610061/p34641.png)

## How to enable WebSocket and WebSocket Secure for an Anti-DDoS Pro or Anti-DDoS Premium instance

-   Enable Websocket: Select **Websocket** when you add a domain name.
-   Enable Websocket Secure: Select **Websockets** when you add a domain name. After the domain name is added, you must upload an HTTPS certificate for the domain name.

![Enable WebSocket ](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/5261610061/p34642.png)

For more information, see [Add a website](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Use domains/Add a website.md) and [Upload an SSL certificate](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Use domains/Upload an SSL certificate.md).

