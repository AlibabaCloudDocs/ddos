# Connect to an ECS instance for which blackhole filtering is triggered

This topic describes how to connect to an ECS instance for which blackhole filtering is triggered from another ECS instance that resides in the same region.

If your ECS instance encounters a volumetric attack that triggers blackhole filtering, all Internet traffic to the ECS instance is blocked. However, you can still access the ECS instance from Alibaba Cloud services that are in the same region as this ECS instance.

Therefore, after blackhole filtering is triggered for an ECS instance, you can connect to it from another ECS instance in the same region.

1.  Log on to a normal ECS instance that is in the same region as the ECS instance for which blackhole filtering is triggered.

    **Note:** These two ECS instances must be in the same VPC and be able to communicate with each other. Make sure that communication is not blocked by security group rules. For more information, see [Overview](/intl.en-US/Security/Security groups/Overview.md).

2.  Use a tool or the command line interface to connect to the ECS instance for which blackhole filtering is triggered.

    After the connection is successful, you can modify configuration files on this ECS instance or transfer files to the normal ECS instance to which you log on.


