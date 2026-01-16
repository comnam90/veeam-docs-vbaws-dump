---
title: "role_permissions_restore_redshift_serverless"
product: "vbaws"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/role_permissions_restore_redshift_serverless.html"
last_updated: "3/20/2025"
product_version: "10.0.0.232"
---


In this article

To perform Redshift Serverless restore operations, IAM roles and IAM users specified in the [restore settings](restore_account_redshift.md), or IAM roles specified in the [organization settings](organization_add_settings.md), must meet the following requirements:

1. The backup appliance must be granted permissions to assume the IAM roles. For more information on the requirements for adding IAM roles, see [Before You Begin](byb_roles.md).

1. The IAM roles must be granted the following permissions:

|  |
| --- |
| {     "Version": "2012-10-17",     "Statement": [         {             "Effect": "Allow",             "Action": [                 "iam:GetContextKeysForPrincipalPolicy",                 "iam:ListAccountAliases",                 "iam:SimulatePrincipalPolicy",                 "ec2:DescribeAccountAttributes",                 "ec2:DescribeAvailabilityZones",                 "ec2:DescribeRegions",                 "ec2:DescribeVpcs",                 "ec2:DescribeSubnets",                 "ec2:DescribeSecurityGroups",                 "kms:CreateGrant",                 "kms:Decrypt",                 "kms:DescribeKey",                 "kms:GenerateDataKey",                 "kms:ListKeys",                 "kms:ListAliases",                 "iam:ListRoles",                 "iam:PassRole",                 "redshift-serverless:CreateNamespace",                 "redshift-serverless:CreateWorkgroup",                 "redshift-serverless:DeleteNamespace",                 "redshift-serverless:DeleteWorkgroup",                 "redshift-serverless:GetNamespace",                 "redshift-serverless:GetWorkgroup",                 "redshift-serverless:GetSnapshot",                 "redshift-serverless:ListNamespaces",                 "redshift-serverless:ListWorkgroups",                 "redshift-serverless:ListTagsForResource",                 "redshift-serverless:RestoreFromSnapshot",                 "redshift-serverless:TagResource",                 "secretsmanager:DescribeSecret",                 "secretsmanager:CreateSecret",                 "secretsmanager:RotateSecret",                 "secretsmanager:TagResource"             ],             "Resource": "\*"         }     ]  } |

To learn how to create IAM roles and assign them the required permissions, see [Appendix A. Creating IAM Roles in AWS](create_iam_policy_role.md).

Page updated 3/20/2025

Page content applies to build 10.0.0.232
