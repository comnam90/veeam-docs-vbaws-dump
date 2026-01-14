---
title: "role_permissions_restore_redshift"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/role_permissions_restore_redshift.html"
last_updated: "3/20/2025"
product_version: "10.0.0.232"
---


In this article

To perform Redshift restore operations, IAM roles and IAM users specified in the [restore settings](restore_account_redshift.md), or IAM roles specified in the [organization settings](organization_add_settings.md), must meet the following requirements:

1. The backup appliance must be granted permissions to assume the IAM roles. For more information on the requirements for adding IAM roles, see [Before You Begin](byb_roles.md).
2. The AWS Backup service must be granted permissions to assume the IAM roles.

To allow the AWS Backup service to assume an IAM role, configure trust relationships for the role and add the following statement to the trust policy:

|  |
| --- |
| {   "Version": "2012-10-17",   "Statement": [     {       "Effect": "Allow",       "Action": "sts:AssumeRole",       "Principal": {         "Service": "backup.amazonaws.com"       }     }   ]  } |

To learn how to modify role trust policies, see [AWS Documentation](https://docs.aws.amazon.com/IAM/latest/UserGuide/roles-managingrole-editing-console.html#roles-managingrole_edit-trust-policy).

1. The IAM roles must be granted the following permissions:

|  |
| --- |
| {     "Version": "2012-10-17",     "Statement": [         {             "Effect": "Allow",             "Action": [                 "backup:DescribeRestoreJob",                 "backup:ListTags",                 "backup:StartRestoreJob",                 "ec2:DescribeInternetGateways",                 "ec2:DescribeRegions",                 "ec2:DescribeSecurityGroups",                 "ec2:DescribeSubnets",                 "ec2:DescribeVpcs",                 "iam:GetContextKeysForPrincipalPolicy",                 "iam:GetRole",                 "iam:ListAccountAliases",                 "iam:ListRoles",                 "iam:PassRole",                 "iam:SimulatePrincipalPolicy",                 "kms:CreateGrant",                 "kms:Decrypt",                 "kms:DescribeKey",                 "kms:GenerateDataKey",                 "kms:ListAliases",                 "kms:ListKeys",                 "redshift:CreateTags",                 "redshift:DeleteCluster",                 "redshift:DescribeClusterParameterGroups",                 "redshift:DescribeClusters",                 "redshift:DescribeClusterSnapshots",                 "redshift:DescribeClusterSubnetGroups",                 "redshift:DescribeNodeConfigurationOptions",                 "redshift:DescribeTags",                 "redshift:ModifyCluster",                 "redshift:RestoreFromClusterSnapshot",                 "secretsmanager:CreateSecret",                 "secretsmanager:DescribeSecret",                 "secretsmanager:TagResource"             ],             "Resource": "\*"         }     ]  } |

To learn how to create IAM roles and assign them the required permissions, see [Appendix A. Creating IAM Roles in AWS](create_iam_policy_role.md).

Page updated 3/20/2025

Page content applies to build 10.0.0.232
