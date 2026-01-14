---
title: "overview_rds"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/overview_rds.html"
last_updated: "11/28/2025"
product_version: "10.0.0.232"
---


In this article

With Veeam Backup for AWS, you can perform the following operations to protect RDS resources:

* Create cloud-native snapshots of RDS resources (DB instances and Amazon Aurora DB clusters) and replicate these snapshots to any AWS Region within any AWS account.

A cloud-native snapshot of a DB instance includes a storage volume snapshot of the instance. Snapshots of DB instances (also referred to as DB snapshots) are taken using native [AWS capabilities](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_CreateSnapshot.html).

* Create image-level backups of Microsoft SQL Server and PostgreSQL DB instances and keep them in Amazon Simple Storage Service (Amazon S3) for high availability, cost-effective and long-term storage.

An image-level backup captures Microsoft SQL Server and PostgreSQL databases of the processed DB instances.

To protect RDS resources, Veeam Backup for AWS runs backup policies. A backup policy is a collection of settings that define the way backup operations are performed: what data to back up, where to store backups, when to start the backup process, how to retain restore points, and so on.

Veeam Backup for AWS does not install agent software inside instances to back up RDS resource data — it uses native AWS capabilities instead. During every backup session, Veeam Backup for AWS creates a cloud-native snapshot for each RDS resource added to a backup policy. For more information on how RDS resources backup works, see [RDS Backup](backup_hiw_rds.md).

Supported Applications

Veeam Backup for AWS supports image-level backup of the following PostgreSQL versions:

* PostgreSQL 17
* PostgreSQL 16
* PostgreSQL 15
* PostgreSQL 14
* PostgreSQL 13
* PostgreSQL 12

Worker Deployment Considerations

Before you start creating RDS backup policies, consider the following:

* By default, Veeam Backup for AWS deploys worker instances in production accounts and employs several IAM roles to deploy them. For more information, see [Worker Deployment Options](worker_options.md#production).
* To perform RDS image-level backups, Veeam Backup for AWS deploys the worker instances in the same AWS Regions and VPCs in which processed Microsoft SQL Server or PostgreSQL DB instances reside. For more information, see [Worker Instance Locations](workers_location.md).
* By default, Veeam Backup for AWS uses the most appropriate network settings of AWS Regions in production accounts to deploy the worker instances. However, you can add [specific worker configurations](worker_add_config_prod.md) to specify network settings for each region in which worker instances will be deployed.

If no specific worker configurations are added to Veeam Backup for AWS, the most appropriate network settings of AWS Regions are used to deploy worker instances for the RDS backup operation. For Veeam Backup for AWS to be able to launch a worker instance used to create an image-level backup:

* The DNS resolution option must be enabled for the VPC. For more information, see [AWS Documentation](https://docs.aws.amazon.com/vpc/latest/userguide/working-with-vpcs.html#Create-VPC).
* As Veeam Backup for AWS uses public access to communicate with worker instances, the [public IPv4 addressing](https://docs.aws.amazon.com/vpc/latest/userguide/subnet-public-ip.html) attribute must be enabled at least for one subnet in the Availability Zone where the DB instance resides and the VPC to which the subnet belongs must have an [internet gateway attached](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_Internet_Gateway.html). VPC and subnet route tables must have routes that direct internet-bound traffic to this internet gateway.

If you want worker instances to operate in a private network, enable the [private network deployment](enable_private_network_deployment.md) functionality and configure [specific VPC endpoints](configuring_private_networks.md) for the subnet to let Veeam Backup for AWS use private IPv4 addresses. Alternatively, configure VPC interface endpoints as described in section [Appendix C. Configuring Endpoints in AWS](configure_endpoints.md).

How To Protect RDS Resources

To create an RDS backup policy, perform the following steps:

1. [Check limitations and prerequisites](limitations.md#backup_rds).
2. [Specify IAM roles to access AWS services and resources](accounts_iam_roles.md).
3. [[Optional] Add backup repositories to store backed-up data](repositories.md).
4. [[Optional] Configure worker instance settings to deploy workers while processing DB instance data](workers.md).
5. [[Optional] Configure global retention settings for obsolete snapshots and session records](retention_settings.md).
6. [[Optional] Configure email notification settings for automated delivery of backup policy results and daily reports](email_settings.md).
7. [Complete the Add RDS Policy wizard](policies_create_rds.md).

Related Topics

[RDS Restore](restore_hiw_rds.md)

Page updated 11/28/2025

Page content applies to build 10.0.0.232
