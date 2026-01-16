---
title: "add_policy_target_settings_backups_rds"
product: "vbaws"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/add_policy_target_settings_backups_rds.html"
last_updated: "12/11/2025"
product_version: "10.0.0.232"
---


In this article

In the Backups section of the Targets step of the wizard, you can instruct Veeam Backup for AWS to create image-level backups of the processed DB instances and to copy backups to a long-term archive storage.

|  |
| --- |
| Note |
| To create RDS image-level backups, Veeam Backup for AWS deploys worker instances in a production account — that is, the same AWS account to which the processed resources belong. For more information, see [Worker Deployment Options](worker_options.md#production). |

Configuring Backup Settings

To instruct Veeam Backup for AWS to create image-level backups of the selected RDS resources, do the following:

1. Set the Enable backups toggle to On.
2. In the Repositories window, select a backup repository where the created image-level backups will be stored, and click Apply.

For a backup repository to be displayed in the list of available repositories, it must be added to Veeam Backup for AWS as described in section [Adding Backup Repositories](repositories_add_ui.md). The list shows only backup repositories of the S3 Standard storage class.

Note that if you have added Microsoft SQL Server DB instances to the backup scope at [step 4](add_policy_source_settings_rds.md) of the wizard, Veeam Backup for AWS will create a number of temporary Amazon S3 buckets in the same AWS Region in which the processed instances reside and then remove these buckets automatically — but only in case they are not used by any data protection or disaster recovery operations. To learn how Veeam Backup for AWS creates image-level backups, see [RDS Backup](backup_hiw_rds.md).

Keep in mind that if you have instructed Veeam Backup for AWS to deploy worker instances without public IPv4 addresses, it must be able to connect to the public s3.<region>.amazonaws.com endpoint to access temporary Amazon S3 buckets. Otherwise, Veeam Backup for AWS will not be able to create image-level backups of Microsoft SLQ Server DB instances. For more information on the private network deployment functionality, see [Configuring General Settings](enable_private_network_deployment.md).

|  |
| --- |
| Important |
| If you plan to back up Microsoft SQL Server DB instances, consider the following:   * The SQLSERVER\_BACKUP\_RESTORE option must be added to the option group that is applied to each processed DB instance. * The IAM role that is associated with the SQLSERVER\_BACKUP\_RESTORE option must have the permissions required to access temporary Amazon S3 buckets. The IAM role must also have a trust relationship and a permissions policy attached to allow the Amazon RDS service to assume the role.   For more information on the backup and restore option, see [AWS Documentation](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Appendix.SQLServer.Options.BackupRestore.html#Appendix.SQLServer.Options.BackupRestore.Add). |

Configuring Archive Settings

To instruct Veeam Backup for AWS to store backed-up data in a low-cost, long-term archive storage, do the following:

1. Select the Archives will be stored in check box.
2. In the Repositories window, select a backup repository where the archived data will be stored, and click Apply.

For an archive backup repository to be displayed in the list of available repositories, it must be added to Veeam Backup for AWS as described in section [Adding Backup Repositories](repositories_add_ui.md). The list shows only backup repositories of the S3 Glacier Flexible Retrieval or S3 Glacier Deep Archive storage classes.

For more information on backup archiving, see [Enabling Backup Archiving](backup_archiving_rds.md).

|  |
| --- |
| Important |
| * For Microsoft SQL Server DB instances, Veeam Backup for AWS does not support storing backed-up data in long-term archive storage. * If you enable backup archiving, consider that data encryption must be either enabled or disabled for both backup and archive backup repositories. This means that, for example, you cannot select an encrypted standard backup repository and an unencrypted archive backup repository in one backup policy. However, the selected repositories can have different encryption schemes (password and KMS encryption). |

Configuring Worker Settings

Depending on the option selected at [step 3](add_policy_scope_rds.md) of the wizard, the following will happen:

* If you have selected the Account option, you will be able to choose an IAM role that will be attached to the worker instances and used by Veeam Backup for AWS to communicate with these instances. The role you choose must belong to the same account to which the IAM role specified for the backup operation belongs, and must be assigned the permissions listed in section [Worker Deployment Role Permissions in Production Accounts](role_permissions_prod_acc.md#worker_reqs).

For an IAM role to be displayed in the list of available roles, it must be added to Veeam Backup for AWS with the Production worker role selected as described in section [Adding IAM Roles](https://helpcenter.veeam.com/docs/vbaws/guide/iam_roles_add.html). If you have not added the necessary IAM role to Veeam Backup for AWS beforehand, you can do it without closing the Add Policy wizard. To do that, click Add and complete the Add IAM Role wizard.

* If you have selected the Organization option, Veeam Backup for AWS will automatically choose an IAM role that will be attached to the worker instances and used by Veeam Backup for AWS to communicate with these instances. It will be one of the roles specified in the settings of the selected organization identity — either the IAM role whose permissions will be used to perform the backup operation (that is, the Backup and restore IAM role), or the IAM role that will be attached to the worker instances and used by Veeam Backup for AWS to communicate with these instances (that is, the Production worker IAM role).

For Veeam Backup for AWS to be able to choose an IAM role automatically, it must be created in all AWS accounts belonging to the selected organization identity, and specified in the organization settings as described in section [Adding AWS Organizations](organization_add_settings.md#backup_role) (step 3).

In both cases, you will have to assign additional permissions to the IAM role that will be used to perform the backup operation. For more information on the required permissions, see section [RDS Backup IAM Role Permissions](role_permissions_backup_rds.md).

|  |
| --- |
| Important |
| If you select the Account option, it is recommended that you check whether both the IAM role specified at [step 3](add_policy_scope_rds.md#account) of the wizard and the IAM role specified in the Backups section have the required permissions. If some permissions of the IAM role are missing, the backup policy may fail to complete successfully. To run the IAM role permission check, click Check Permissions and follow the instructions provided in section [Checking IAM Role Permissions](iam_roles_check.md#wizard). |

Worker Instance Requirements

To perform RDS image-level backups, Veeam Backup for AWS deploys worker instances in production accounts in the same AWS Regions and VPCs in which processed PostgreSQL DB instances reside. By default, Veeam Backup for AWS uses the most appropriate network settings of AWS Regions in production accounts to deploy worker instances. However, you can add [specific worker configurations](worker_add_config_prod.md) to specify network settings for each region in which worker instances will be deployed.

If no [specific worker configurations](worker_add_config_prod.md) are added to Veeam Backup for AWS, the most appropriate network settings of AWS Regions are used to deploy worker instances for the RDS backup operation. For Veeam Backup for AWS to be able to deploy a worker instance used to create an image-level backup:

* The DNS resolution option must be enabled for the VPC network. For more information, see [AWS Documentation](https://docs.aws.amazon.com/vpc/latest/userguide/working-with-vpcs.html#Create-VPC).
* As Veeam Backup for AWS uses public access to communicate with worker instances, the [public IPv4 addressing](https://docs.aws.amazon.com/vpc/latest/userguide/subnet-public-ip.html) attribute must be enabled at least for one subnet in the Availability Zone where the DB instance resides and the VPC network to which the subnet belongs must have an [internet gateway attached](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_Internet_Gateway.html). VPC network and subnet route tables must have routes that direct internet-bound traffic to this internet gateway.

If you want worker instances to operate in a private network, enable the [private network deployment](enable_private_network_deployment.md) functionality and configure [specific VPC endpoints](configuring_private_networks.md) for the subnet to let Veeam Backup for AWS use private IPv4 addresses. Alternatively, configure VPC interface endpoints as described in section [Appendix C. Configuring Endpoints in AWS](configure_endpoints.md).

|  |
| --- |
| Note |
| During RDS image-level backup operations, Veeam Backup for AWS creates 2 additional security groups that are further associated with the source DB instances and worker instances to allow direct network traffic between them. To learn how RDS resource backup works, see [RDS Backup](backup_hiw_rds.md). |

[![Creating RDS Backup Policy](images/rds_backup_target_backup.webp)](images/rds_backup_target_backup.webp "Creating RDS Backup Policy")

Page updated 12/11/2025

Page content applies to build 10.0.0.232
