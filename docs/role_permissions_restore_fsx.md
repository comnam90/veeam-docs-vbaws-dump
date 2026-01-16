---
title: "role_permissions_restore_fsx"
product: "vbaws"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/role_permissions_restore_fsx.html"
last_updated: "2/10/2025"
product_version: "10.0.0.232"
---


In this article

To perform FSx restore operations, IAM roles and IAM users specified in the [restore settings](restore_account_fsx.md), or IAM roles specified in the [organization settings](organization_add_settings.md), must meet the following requirements:

1. The backup appliance must be granted permissions to assume the IAM roles. For more information on the requirements for adding IAM roles, see [Before You Begin](byb_roles.md).
2. The AWS Backup service must be granted permissions to assume the IAM roles.

To allow the AWS Backup service to assume an IAM role, configure trust relationships for the role and add the following statement to the trust policy.

|  |
| --- |
| {   "Version": "2012-10-17",   "Statement": [     {       "Effect": "Allow",       "Action": "sts:AssumeRole",       "Principal": {         "Service": "backup.amazonaws.com"       }     }   ]  } |

To learn how to modify role trust policies, see [AWS Documentation](https://docs.aws.amazon.com/IAM/latest/UserGuide/roles-managingrole-editing-console.html#roles-managingrole_edit-trust-policy).

1. The IAM roles must be granted the following permissions:

|  |
| --- |
| {     "Version": "2012-10-17",     "Statement": [         {             "Effect": "Allow",             "Action": [                 "ds:DescribeDirectories",                 "ec2:CreateTags",                 "ec2:DescribeRegions",                 "ec2:DescribeVpcs",                 "ec2:DescribeSecurityGroups",                 "ec2:DescribeSubnets",                 "ec2:DescribeRouteTables",                 "backup:CopyFromBackupVault",                 "backup:CopyIntoBackupVault",                 "backup:CreateBackupVault",                 "backup:DescribeCopyJob",                 "backup:DeleteRecoveryPoint",                 "backup:DeleteBackupVault",                 "backup:DescribeRestoreJob",                 "backup:DescribeRecoveryPoint",                 "backup:DescribeBackupVault",                 "backup:ListTags",                 "backup:StartCopyJob",                 "backup:StartRestoreJob",                 "backup:TagResource",                 "backup:ListBackupVaults",                 "backup-storage:MountCapsule",                 "fsx:CreateFileSystemFromBackup",                 "fsx:CopyBackup",                 "fsx:DescribeFileSystems",                 "fsx:DeleteFileSystem",                 "fsx:TagResource",                 "fsx:UntagResource",                 "fsx:DescribeBackups",                 "fsx:ListTagsForResource",                 "iam:GetRole",                 "iam:GetContextKeysForPrincipalPolicy",                 "iam:SimulatePrincipalPolicy",                 "iam:PassRole",                 "iam:ListAccountAliases",                 "kms:ListKeys",                 "kms:DescribeKey",                 "kms:CreateGrant",                 "kms:ListAliases",                 "servicequotas:ListServiceQuotas"             ],             "Resource": "\*"         }     ]  } |

To learn how to create IAM roles and assign them the required permissions, see [Appendix A. Creating IAM Roles in AWS](create_iam_policy_role.md).

Page updated 2/10/2025

Page content applies to build 10.0.0.232
