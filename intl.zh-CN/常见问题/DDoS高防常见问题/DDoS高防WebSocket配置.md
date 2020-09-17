# DDoS高防WebSocket配置

DDoS高防域名接入协议支持WebSocket，本文介绍了在高防中配置WebSocket的相关内容。

## 什么是WS、WSS？

WS是Web Socket的缩写，WebSocket是HTML5一种新的协议，它实现了浏览器与服务器全双工通信，能更好地节省服务器资源和带宽并达到实时通讯。WebSocket建立在TCP之上，同HTTP一样通过TCP来传输数据，但是它和HTTP不同。

WebSocket是一种双向通信协议，在建立连接后，WebSocket服务器和Browser、Client Agent都能主动地向对方发送或接收数据，就像Socket一样。WebSocket需要类似TCP的客户端和服务器端通过握手连接，连接成功后才能相互通信。

WSS是Web Socket Secure的缩写，即WebSocket加密版本。

## 为什么使用WS、WSS？

随着互联网的蓬勃发展，各种类型的Web应用层出不穷，很多应用要求服务端有能力进行实时推送能力（例如直播间聊天室），以往很多网站为了实现推送技术，所用的技术都是轮询。轮询是在特定的时间间隔（例如每1秒），由浏览器对服务器发出HTTP请求，然后由服务器返回最新的数据给客户端的浏览器。这种传统的模式存在很明显的缺点，即浏览器需要不断地向服务器发出请求，然而HTTP请求可能包含较长的头部，其中真正有效的数据可能只是很小的一部分，显然这样会浪费很多的带宽资源。

在这种情况下，HTML5定义了WebSocket协议，能更好地节省服务器资源和带宽，并且能够更实时地进行通讯。WebSocket实现了浏览器与服务器全双工（full-duplex）通信，允许服务器主动发送信息给客户端。

WebSocket协议的交互过程如下图所示。

![WebSocket协议](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/1938925951/p34641.png)

## 如何在DDoS高防上启用WS、WSS支持？

-   启用WS支持：在域名接入时，选择**Websockt**协议类型。
-   启用WSS支持：在域名接入时，选择**Websockets**协议类型，并在完成域名接入后上传域名的HTTPS证书。

![启用WS ](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/1938925951/p34642.png)

更多信息，请参见[添加网站](/intl.zh-CN/DDoS高防（新BGP&国际）用户指南/接入DDoS高防/网站配置/添加网站.md)、[上传HTTPS证书](/intl.zh-CN/DDoS高防（新BGP&国际）用户指南/接入DDoS高防/网站配置/上传HTTPS证书.md)。

