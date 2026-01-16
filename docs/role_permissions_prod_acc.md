---
title: "role_permissions_prod_acc"
product: "vbaws"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/role_permissions_prod_acc.html"
last_updated: "10/23/2025"
product_version: "10.0.0.232"
---


In this article

|  |
| --- |
| Important |
| When you instruct Veeam Backup for AWS to deploy worker instances in [production accounts](worker_options.md#production) to perform RDS and EC2 backup and restore operations, as well as EFS indexing operations, Veeam Backup for AWS uses the permissions of IAM roles specified for backup and restore operations. That is why you must assign to these IAM roles additional permissions listed in sections [RDS Backup IAM Role Permissions](role_permissions_backup_rds.md#worker), [EC2 Backup IAM Role Permissions](role_permissions_backup_ec2.md#worker), [EC2 Restore IAM Permissions](role_permissions_restore_ec2.md#worker), [RDS Database Restore IAM Permissions](role_permissions_restore_db.md) and [EFS Backup IAM Role Permissions](role_permissions_backup_efs.md#worker). |

Veeam Backup for AWS uses IAM roles that are attached to worker instances deployed in production accounts, which are further used by Veeam Backup for AWS to communicate with these instances to perform the following operations:

* To create indexes of the backed up EFS file systems.
* To perform image-level backup and restore operations with Microsoft SQL Server and PostgreSQL DB instances.
* To perform image-level backup, entire instance and volume-level restore operations with EC2 instances.

To perform these operations, IAM roles specified in the [EFS backup policy settings](add_policy_indexing_efs.md#enable_efs_indexing), [RDS backup policy settings](add_policy_target_settings_backups_rds.md), [EC2 backup policy settings](add_policy_target_settings_backups.md), [EC2 entire instance restore](restore_entire_account.md#workers), [EC2 volume-level restore](restore_volume_account.md#workers) and [RDS database restore](restore_rds_database_workers.md#worker) settings must meet the following requirements:

* The IAM roles must be included at least in one instance profile. For more information on instance profiles, see [AWS Documentation](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_use_switch-role-ec2_instance-profiles.html).

* The backup appliance must be granted permissions to assume the IAM roles. For more information on the requirements for adding IAM roles, see [Before You Begin](byb_roles.md#reqs).

* The Amazon EC2 service must be granted permissions to assume the IAM roles.

To allow the Amazon EC2 service to assume an IAM role, configure trust relationships for the role and add the following statement to the trust policy:

|  |
| --- |
| {   "Version": "2012-10-17",   "Statement": [     {       "Effect": "Allow",       "Action": "sts:AssumeRole",       "Principal": {         "Service": "ec2.amazonaws.com"       }     }   ]  } |

To learn how to modify role trust policies, see [AWS Documentation](https://docs.aws.amazon.com/IAM/latest/UserGuide/roles-managingrole-editing-console.html#roles-managingrole_edit-trust-policy).

* The IAM roles must be granted the following permissions:

|  |
| --- |
| {     "Version": "2012-10-17",     "Statement": [         {             "Action": [                 "ec2messages:AcknowledgeMessage",                 "ec2messages:DeleteMessage",                 "ec2messages:FailMessage",                 "ec2messages:GetEndpoint",                 "ec2messages:GetMessages",                 "ec2messages:SendReply",                 "iam:GetContextKeysForPrincipalPolicy",                 "iam:GetRole",                 "iam:ListInstanceProfilesForRole",                 "iam:SimulatePrincipalPolicy",                 "sqs:DeleteMessage",                 "sqs:ListQueues",                 "sqs:ReceiveMessage",                 "sqs:SendMessage",                 "ssm:DescribeAssociation",                 "ssm:DescribeDocument",                 "ssm:GetDeployablePatchSnapshotForInstance",                 "ssm:GetDocument",                 "ssm:GetManifest",                 "ssm:GetParameter",                 "ssm:GetParameters",                 "ssm:ListAssociations",                 "ssm:ListInstanceAssociations",                 "ssm:PutComplianceItems",                 "ssm:PutConfigurePackageResult",                 "ssm:PutInventory",                 "ssm:UpdateAssociationStatus",                 "ssm:UpdateInstanceAssociationStatus",                 "ssm:UpdateInstanceInformation",                 "ssmmessages:CreateControlChannel",                 "ssmmessages:CreateDataChannel",                 "ssmmessages:OpenControlChannel",                 "ssmmessages:OpenDataChannel"             ],                       "Resource": "\*",                       "Effect": "Allow"           }     ]  } |

To learn how to create IAM roles and assign them the required permissions, see [Appendix A. Creating IAM Roles in AWS](create_iam_policy_role.md).

|  |
| --- |
| Note |
| Since you do not choose an IAM role for file-level recovery operations, the role that you specify [when enabling worker deployment in production accounts](restore_item_mode.md#workers) in the restore settings is also used by Veeam Backup for AWS to deploy worker instances. That is why this role must be assigned permissions listed in section [FLR Worker IAM Role Permissions](role_permissions_flr_prod.md). |

Related Topics

* [Worker Deployment Options](worker_options.md)
* [Worker Configuration IAM Role](role_permissions_service_prod_acc.md)

Page updated 10/23/2025

Page content applies to build 10.0.0.232
