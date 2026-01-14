---
title: "role_permissions_backup_efs"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/role_permissions_backup_efs.html"
last_updated: "4/28/2025"
product_version: "10.0.0.232"
---


In this article

Veeam Backup for AWS uses EFS Backup IAM roles to perform the following operations:

* To enumerate resources added to a backup policy.
* To create backups of EFS file systems.

* To create backup copies, and so on.

To perform these operations, IAM roles specified in the [organization settings](organization_add_settings.md) or in the [EFS backup policy settings](add_policy_scope_efs.md#account) must meet the following requirements:

1. The backup appliance must be granted permissions to assume the IAM roles. For more information on the requirements for adding IAM roles, see [Before You Begin](byb_roles.md).
2. The AWS Backup service must be granted permissions to assume the IAM roles.

To allow the AWS Backup service to assume an IAM role, configure trust relationships for the role and add the following statement to the trust policy.

|  |
| --- |
| {     "Version": "2012-10-17",     "Statement": [         {             "Effect": "Allow",             "Action": "sts:AssumeRole",             "Principal": {                 "Service": "backup.amazonaws.com"             }         }     ]  } |

To learn how to modify role trust policies, see [AWS Documentation](https://docs.aws.amazon.com/IAM/latest/UserGuide/roles-managingrole-editing-console.html#roles-managingrole_edit-trust-policy).

1. The IAM roles must be granted the following permissions:

* IAM roles specified in the [backup policy settings](add_policy_scope_efs.md#role):

|  |
| --- |
| {     "Version": "2012-10-17",     "Statement": [         {             "Effect": "Allow",             "Action": [                 "backup:CopyFromBackupVault",                 "backup:CopyIntoBackupVault",                 "backup:DeleteRecoveryPoint",                 "backup:DescribeBackupJob",                 "backup:DescribeCopyJob",                 "backup:DescribeRegionSettings",                 "backup:DescribeRecoveryPoint",                 "backup:ListBackupVaults",                 "backup:ListRecoveryPointsByBackupVault",                 "backup:ListTags",                 "backup:StartBackupJob",                 "backup:StartCopyJob",                 "backup:StopBackupJob",                 "backup:TagResource",                 "backup:UntagResource",                 "ec2:CreateKeyPair",                 "ec2:DeleteKeyPair",                 "ec2:DescribeAvailabilityZones",                 "ec2:DescribeImages",                 "ec2:DescribeInstances",                 "ec2:DescribeInternetGateways",                 "ec2:DescribeKeyPairs",                 "ec2:DescribeNetworkInterfaceAttribute",                 "ec2:DescribeRegions",                 "ec2:DescribeRouteTables",                 "ec2:DescribeSecurityGroups",                 "ec2:DescribeSubnets",                 "ec2:DescribeVpcEndpoints",                 "ec2:DescribeVpcs",                 "elasticfilesystem:Backup",                 "elasticfilesystem:DescribeAccessPoints",                 "elasticfilesystem:DescribeBackupPolicy",                 "elasticfilesystem:DescribeFileSystemPolicy",                 "elasticfilesystem:DescribeFileSystems",                 "elasticfilesystem:DescribeLifecycleConfiguration",                 "elasticfilesystem:DescribeMountTargetSecurityGroups",                 "elasticfilesystem:DescribeMountTargets",                 "elasticfilesystem:DescribeTags",                 "elasticfilesystem:ListTagsForResource",                 "events:DeleteRule",                 "events:DescribeRule",                 "events:ListTargetsByRule",                 "events:PutRule",                 "events:PutTargets",                 "events:RemoveTargets",                 "iam:GetContextKeysForPrincipalPolicy",                 "iam:GetInstanceProfile",                 "iam:GetRole",                 "iam:ListAccountAliases",                 "iam:ListInstanceProfilesForRole",                 "iam:PassRole",                 "iam:SimulatePrincipalPolicy",                 "sns:CreateTopic",                 "sns:DeleteTopic",                 "sns:ListSubscriptionsByTopic",                 "sns:ListTopics",                 "sns:SetTopicAttributes",                 "sns:Subscribe",                 "sns:Unsubscribe",                 "sqs:CreateQueue",                 "sqs:DeleteMessage",                 "sqs:DeleteQueue",                 "sqs:ListQueues",                 "sqs:ReceiveMessage",                 "sqs:SendMessage",                 "sqs:SetQueueAttributes",                 "ssm:GetCommandInvocation",                 "ssm:GetParameter",                 "ssm:SendCommand"             ],             "Resource": "\*"         }     ]  } |

* IAM roles used to perform backup operations manually as described in section [Creating EFS Backups Manually](backup_manual_efs.md):

|  |
| --- |
| {     "Version": "2012-10-17",     "Statement": [         {             "Effect": "Allow",             "Action": [                 "backup-storage:MountCapsule",                 "backup:CopyFromBackupVault",                 "backup:CopyIntoBackupVault",                 "backup:CreateBackupVault",                 "backup:DeleteBackupVault",                 "backup:DeleteRecoveryPoint",                 "backup:DescribeBackupJob",                 "backup:DescribeCopyJob",                 "backup:DescribeRegionSettings",                 "backup:DescribeRecoveryPoint",                 "backup:ListBackupVaults",                 "backup:ListTags",                 "backup:StartBackupJob",                 "backup:StartCopyJob",                 "backup:StopBackupJob",                 "backup:TagResource",                 "backup:UntagResource",                 "ec2:DescribeAvailabilityZones",                 "ec2:DescribeNetworkInterfaceAttribute",                 "ec2:DescribeRegions",                 "elasticfilesystem:Backup",                 "elasticfilesystem:DescribeAccessPoints",                 "elasticfilesystem:DescribeBackupPolicy",                 "elasticfilesystem:DescribeFileSystemPolicy",                 "elasticfilesystem:DescribeFileSystems",                 "elasticfilesystem:DescribeLifecycleConfiguration",                 "elasticfilesystem:DescribeMountTargetSecurityGroups",                 "elasticfilesystem:DescribeMountTargets",                 "elasticfilesystem:DescribeTags",                 "elasticfilesystem:ListTagsForResource",                 "iam:GetContextKeysForPrincipalPolicy",                 "iam:GetRole",                 "iam:PassRole",                 "iam:SimulatePrincipalPolicy",                 "kms:DescribeKey"             ],             "Resource": "\*"         }     ]  } |

To learn how to create IAM roles and assign them the required permissions, see [Appendix A. Creating IAM Roles in AWS](create_iam_policy_role.md).

Permissions Required to Create Indexes of EFS File Systems

[Applies only to IAM roles specified in the backup policy settings] If you plan to instruct Veeam Backup for AWS to perform [indexing of the processed file systems](add_policy_indexing_efs.md), [IAM roles specified in the backup policy settings](add_policy_scope_efs.md#role) must be granted the following additional permissions to deploy worker instances in [production accounts](worker_options.md#production):

|  |
| --- |
| {     "Version": "2012-10-17",     "Statement": [         {             "Effect": "Allow",             "Action": [                 "ec2:TerminateInstances",                 "ec2:StartInstances"             ],             "Resource": "\*",             "Condition": {                 "StringEquals": {                     "ec2:ResourceTag/EfsIndexWorker": "EfsIndexWorker"                 }             }         },         {             "Effect": "Allow",             "Action": "ec2:CreateTags",             "Resource": "\*",             "Condition": {                 "StringEquals": {                     "ec2:CreateAction": "RunInstances",                     "aws:RequestTag/EfsIndexWorker": "EfsIndexWorker"                 }             }         },         {             "Effect": "Allow",             "Action": [                 "ec2:RunInstances",                 "servicequotas:ListServiceQuotas"             ],             "Resource": "\*"         }     ]  } |

Page updated 4/28/2025

Page content applies to build 10.0.0.232
