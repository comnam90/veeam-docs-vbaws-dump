---
title: "overview_efs"
product: "vbaws"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/overview_efs.html"
last_updated: "9/6/2024"
product_version: "10.0.0.232"
---


In this article

With Veeam Backup for AWS, you can perform the following operations to protect EFS file systems:

* Create cloud-native backups of EFS file systems and store them in any backup vault in the source AWS Region.

An Amazon EFS file system backup captures the whole image of the EFS file system (including file system configuration, files, directories and so on) at a specific point of time. EFS backups are taken using native [AWS capabilities](https://docs.aws.amazon.com/efs/latest/ug/awsbackup.html).

* Create backup copies of EFS file systems and store them in any AWS Region within the same AWS account.

By default, EFS backups are stored only in the AWS Region where the processed resources reside. For enhanced data safety, you can instruct Veeam Backup for AWS to create copies of these backups and store them in any other AWS Region within the same AWS account. You can also combine the backup copy functionality with various [data recovery options](efs_restore_ui.md) to migrate file system data between AWS Regions.

To protect EFS file systems, Veeam Backup for AWS runs backup policies. A backup policy is a collection of settings that define the way backup operations are performed: what data to back up, where to store backups, when to start the backup process, how to retain restore points, and so on.

Veeam Backup for AWS does not install agent software inside instances to back up EFS file systems — it uses native AWS capabilities instead. During every backup session, Veeam Backup for AWS creates a cloud-native backup for each file system added to a backup policy. The cloud-native backup is further used to create a backup copy in another AWS Region.

EFS Indexing

Veeam Backup for AWS allows you to perform indexing of the processed EFS file systems — that is, to perform EFS file-level recovery operations without specifying the exact paths to the necessary files and to restore files using different restore points during one restore session. While performing EFS indexing of a file system, Veeam Backup for AWS creates a catalog of all files and directories (an index) and saves the index to a backup repository. This index is further used to reproduce the file system structure and to enable browsing and searching for specific files within an EFS backup. For more information on how EFS file systems backup works, see [EFS Backup](backup_hiw_efs.md).

To allow Veeam Backup for AWS to perform indexing of the processed EFS file systems, this functionality must be enabled in the [backup policy settings](add_policy_indexing_efs.md).

Worker Deployment Considerations

Before you start creating EFS backup policies, consider the following:

* To create indexes of the backed up EFS file systems, Veeam Backup for AWS deploys worker instances in production accounts and employs several IAM roles to deploy them. For more information, see [Worker Deployment Methods](worker_options.md#production).
* To create indexes of the backed up EFS file systems, Veeam Backup for AWS deploys the worker instances in the AWS Region, Availability Zone, and VPC in which a mount target has been created for the file system. For more information, see [Worker Instance Locations](workers_location.md).

* By default, Veeam Backup for AWS automatically chooses the most appropriate network settings of AWS Regions in production accounts to deploy the worker instances. However, you can [add specific worker configurations](worker_add_config_prod.md) to specify network settings for each region in which worker instances will be deployed.

If no specific worker configurations are added to Veeam Backup for AWS, the most appropriate network settings of AWS Regions are used to launch worker instances for EFS indexing operations. For Veeam Backup for AWS to be able to launch a worker instance used to create an index of a file system:

* A VPC in which the file system has the mount target must have at least one security group that allows outbound access on ports 2049 and 443. These ports are used by worker instances to mount the file system and to communicate with [AWS services](system_requirements_aws_services.md).
* The DNS resolution option must be enabled for the VPC. For more information, see [AWS Documentation](https://docs.aws.amazon.com/vpc/latest/userguide/working-with-vpcs.html#Create-VPC).
* As Veeam Backup for AWS uses public access to communicate with worker instances, the [public IPv4 addressing](https://docs.aws.amazon.com/vpc/latest/userguide/working-with-subnets.html#subnet-public-ip) attribute must be enabled at least for one subnet in the Availability Zone in which the file system has a mount target and the VPC to which the subnet belongs must have an [internet gateway attached](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_Internet_Gateway.html). VPC and subnet route tables must have routes that direct internet-bound traffic to this internet gateway.

If you want worker instances to operate in a private network, enable the [private network deployment](enable_private_network_deployment.md) functionality and configure [specific VPC endpoints](configuring_private_networks.md) for the subnet to let Veeam Backup for AWS use private IPv4 addresses. Alternatively, configure VPC interface endpoints as described in section [Appendix C. Configuring Endpoints in AWS](configure_endpoints.md).

How To Protect EFS File Systems

To create an EFS backup policy, perform the following steps:

1. [Check limitations and prerequisites](limitations.md#backup_efs).
2. [Specify IAM roles to access AWS services and resources](accounts_iam_roles.md).
3. [[Optional] Add backup repositories to store backed-up data](repositories.md).
4. [[Optional] Configure worker instance settings to deploy workers while performing indexing of the processed EFS file systems](workers.md).
5. [[Optional] Configure email notification settings for automated delivery of backup policy results and daily reports](email_settings.md).
6. [Complete the Add EFS Policy wizard](policies_create_efs.md).

Related Topics

[EFS Restore](restore_hiw_efs.md)

Page updated 9/6/2024

Page content applies to build 10.0.0.232
