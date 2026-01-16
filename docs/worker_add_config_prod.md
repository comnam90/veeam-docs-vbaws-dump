---
title: "worker_add_config_prod"
product: "vbaws"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/worker_add_config_prod.html"
last_updated: "1/5/2026"
product_version: "10.0.0.232"
---


In this article

By design, Veeam Backup for AWS deploys worker instances in production accounts to perform EFS indexing, RDS backup and RDS restore operations. You can [specify network settings](worker_configurations_prod.md#region) that will be used to deploy these worker instances.

|  |
| --- |
| Note |
| If you want Veeam Backup for AWS to deploy worker instances in production accounts to perform EC2 backup and restore operations as well (for example, to restore instances from cloud-native snapshots encrypted using default AWS managed keys), you must configure additional backup policy and restore settings. For more information, [Worker Deployment Options](worker_options.md#production). |

To deploy worker instances in production accounts, Veeam Backup for AWS employs the following IAM roles:

* An IAM role that is used to retrieve network settings of AWS Regions in a production account when adding new or editing existing working configurations. The role must be assigned permissions listed in section [Worker Configuration IAM Role Permissions](role_permissions_service_prod_acc.md).

You must specify this IAM role either in the Add Organization wizard as described in [Adding AWS Organizations](organization_add_settings.md), or in the Add Worker Configuration wizard as described in [Adding Worker Configurations](worker_configuration_general_prod.md#IAMrole).

* An IAM role that is used to perform a backup or restore operation. Veeam Backup for AWS also uses this role to deploy worker instances in a production account. That is why the role must be assigned additional permissions listed in section [EFS Backup IAM Role Permissions](role_permissions_backup_efs.md#worker), [EC2 Backup IAM Role Permissions](role_permissions_backup_ec2.md#worker), [EC2 Restore IAM Permissions](role_permissions_restore_ec2.md#worker) or [RDS Backup IAM Role Permissions](role_permissions_backup_rds.md#worker).

You must specify this IAM role either in the [organization settings](organization_add_settings.md#backup_role) when adding an AWS Organization to Veeam Backup for AWS, or in the backup policy or restore settings as described in section [Creating EFS Backup Policies](add_policy_scope_efs.md#account), [Creating EC2 Backup Policies](add_policy_scope.md), [Performing RDS Backup](add_policy_scope_rds.md#account), [Performing Entire EC2 Instance Restore](restore_entire_account.md#roles), [Performing Volume-Level Restore](restore_volume_account.md#roles) or [Performing RDS Database Restore](restore_rds_database_workers.md).

* An IAM role that is attached to the deployed worker instances and further used by Veeam Backup for AWS to communicate with the instances. The role must be assigned permissions listed in section [Worker Deployment Role Permissions in Production Accounts](role_permissions_prod_acc.md) or [FLR Worker IAM Role Permissions](role_permissions_flr_prod.md).

You must specify this IAM role either in the [organization settings](organization_add_settings.md#backup_role) when adding an AWS Organization to Veeam Backup for AWS, or when enabling worker deployment in production accounts in the backup policy or restore settings, as described in section [Creating EFS Backup Policies](add_policy_indexing_efs.md#enable_efs_indexing), [Creating EC2 Backup Policies](add_policy_target_settings_backups.md#workers), [Creating RDS Backup Policies](add_policy_target_settings_backups_rds.md), [Performing Entire EC2 Instance Restore](restore_entire_account.md#workers), [Performing Volume-Level Restore](restore_volume_account.md#workers), [Performing File-Level Recovery](restore_item_mode.md#workers) or [Performing RDS Database Restore](restore_rds_database_workers.md).

|  |
| --- |
| Note |
| Since you do not specify an IAM role for file-level recovery operations, the role that you specify when enabling worker deployment in production accounts in the restore settings is also used by Veeam Backup for AWS to deploy worker instances. |

Related Topics

* [Editing Configurations](worker_settings_edit.md)
* [Removing Configurations](worker_remove_config.md)

Page updated 1/5/2026

Page content applies to build 10.0.0.232
