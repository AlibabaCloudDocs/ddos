# Connect to a server whose IP address is thrown into the black hole

If your server suffers from a heavy traffic attack and its IP address is thrown into the black hole, then all external traffic to the server is discarded. However, you can still access this server from Alibaba Cloud services within the same region as that of this server.

**Note:** During the black hole period, external access requests sent to this server are blocked.

You can use an Alibaba Cloud ECS instance to connect to your server, even when its IP address is thrown into the black hole.

1.  Connect to an Alibaba Cloud ECS instance that can be normally accessed and is within the same region as this server.

    **Note:** This ECS instance must be connectable to the server under black hole status. They must belong to the same VPC environment, and the connection is not blocked by any security group access control rules.

2.  Use a tool or command line to connect from the ECS instance to the server under black hole status.

After successfully connecting to the server from the ECS instance, you can transfer files from the server to the ECS instance and modify the configuration files on this server.

