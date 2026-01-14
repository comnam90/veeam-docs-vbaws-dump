---
title: "role_permissions_backup_fsx"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/role_permissions_backup_fsx.html"
last_updated: "4/28/2025"
product_version: "10.0.0.232"
---


In this article

Veeam Backup for AWS uses FSx Backup IAM roles to perform the following operations:

* To enumerate resources added to a backup policy.
* To create backups of FSx file systems.

* To create backup copies, and so on.

To perform these operations, IAM roles specified in the [organization settings](organization_add_settings.md) or in the [FSx backup policy settings](add_policy_scope_fsx.md#account) must meet the following requirements:

1. The backup appliance must be granted permissions to assume the IAM roles. For more information on the requirements for adding IAM roles, see [Before You Begin](byb_roles.md).
2. The AWS Backup service must be granted permissions to assume the IAM roles.

To allow the AWS Backup service to assume an IAM role, configure trust relationships for the role and add the following statement to the trust policy.

|  |
| --- |
| {     "Version": "2012-10-17",     "Statement": [         {             "Effect": "Allow",             "Action": "sts:AssumeRole",             "Principal": {                 "Service": "backup.amazonaws.com"             }         }     ]  } |

To learn how to modify role trust policies, see [AWS Documentation](https://docs.aws.amazon.com/IAM/latest/UserGuide/roles-managingrole-editing-console.html#roles-managingrole_edit-trust-policy).

1. The IAM roles must be granted the following permissions:

* IAM roles specified in the [backup policy settings](add_policy_scope_fsx.md#role):

|  |
| --- |
| {     "Version": "2012-10-17",     "Statement": [         {             "Effect": "Allow",             "Action": [                 "backup:CopyFromBackupVault",                 "backup:CopyIntoBackupVault",                 "backup:DescribeCopyJob",                 "backup:DescribeRegionSettings",                 "backup:DeleteRecoveryPoint",                 "backup:DescribeBackupJob",                 "backup:DescribeRecoveryPoint",                 "backup:ListTags",                 "backup:ListBackupVaults",                 "backup:ListRecoveryPointsByBackupVault",                 "backup:StartBackupJob",                 "backup:StartCopyJob",                 "backup:UpdateRegionSettings",                 "events:DeleteRule",                 "events:DescribeRule",                 "events:ListTargetsByRule",                 "events:PutTargets",                 "events:PutRule",                 "events:RemoveTargets",                 "ec2:DescribeRegions",                 "ec2:DescribeNetworkInterfaces",                 "ec2:DescribeAvailabilityZones",                 "fsx:CopyBackup",                 "fsx:DescribeDataRepositoryAssociations",                 "fsx:DescribeFileSystems",                 "fsx:DescribeBackups",                 "fsx:ListTagsForResource",                 "fsx:CreateBackup",                 "fsx:TagResource",                 "fsx:UntagResource",                 "iam:GetContextKeysForPrincipalPolicy",                 "iam:GetRole",                 "iam:ListAccountAliases",                 "iam:PassRole",                 "iam:SimulatePrincipalPolicy",                 "kms:DescribeKey",                 "kms:CreateGrant",                 "sns:CreateTopic",                 "sns:DeleteTopic",                 "sns:ListSubscriptionsByTopic",                 "sns:Subscribe",                 "sns:Unsubscribe",                 "sqs:CreateQueue",                 "sqs:DeleteQueue",                 "sqs:DeleteMessage",                 "sqs:ListQueues",                 "sns:ListTopics",                 "sns:SetTopicAttributes",                 "sqs:SetQueueAttributes",                 "sqs:ReceiveMessage"             ],             "Resource": "\*"         }     ]  } |

* IAM roles used to perform backup operations manually as described in section [Creating FSx Backups Manually](backup_manual_fsx.md):

|  |
| --- |
| {     "Version": "2012-10-17",     "Statement": [         {             "Effect": "Allow",             "Action": [                 "backup:CreateBackupVault",                 "backup:CopyIntoBackupVault",                 "backup:CopyFromBackupVault",                 "backup:DescribeBackupJob",                 "backup:DescribeCopyJob",                 "backup:DescribeRecoveryPoint",                 "backup:DescribeRegionSettings",                 "backup:ListBackupVaults",                 "backup:ListTags",                 "backup:TagResource",                 "backup:DeleteRecoveryPoint",                 "backup:DeleteBackupVault",                 "backup:StartCopyJob",                 "backup:StartBackupJob",                 "backup:UpdateRegionSettings",                 "backup-storage:MountCapsule",                 "ec2:DescribeRegions",                 "ec2:DescribeNetworkInterfaces",                 "iam:GetRole",                 "iam:GetContextKeysForPrincipalPolicy",                 "iam:PassRole",                 "iam:SimulatePrincipalPolicy",                 "fsx:DescribeBackups",                 "fsx:DescribeDataRepositoryAssociations",                 "fsx:DescribeFileSystems",                 "fsx:CopyBackup",                 "fsx:CreateBackup",                 "fsx:ListTagsForResource",                 "fsx:TagResource",                 "fsx:UntagResource",                 "kms:CreateGrant",                 "kms:DescribeKey"             ],             "Resource": "\*"         }     ]  } |

To learn how to create IAM roles and assign them the required permissions, see [Appendix A. Creating IAM Roles in AWS](create_iam_policy_role.md).

Page updated 4/28/2025

Page content applies to build 10.0.0.232
