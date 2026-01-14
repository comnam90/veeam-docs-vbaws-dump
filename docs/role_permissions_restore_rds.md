---
title: "role_permissions_restore_rds"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/role_permissions_restore_rds.html"
last_updated: "11/14/2025"
product_version: "10.0.0.232"
---


In this article

To perform RDS instance restore operations, IAM roles and IAM users specified in the [restore settings](restore_rds_account.md), or IAM roles specified in the [organization settings](organization_add_settings.md), must meet the following requirements:

1. The backup appliance must be granted permissions to assume the IAM roles. For more information on the requirements for adding IAM roles, see [Before You Begin](byb_roles.md).

1. The IAM roles must be granted the following permissions:

|  |
| --- |
| {     "Version": "2012-10-17",     "Statement": [         {             "Effect": "Allow",             "Action": [                 "ec2:DescribeAvailabilityZones",                 "ec2:DescribeDhcpOptions",                 "ec2:DescribeInternetGateways",                 "ec2:DescribeRegions",                 "ec2:DescribeSecurityGroups",                 "ec2:DescribeSubnets",                 "ec2:DescribeVpcAttribute",                 "ec2:DescribeVpcs",                 "iam:CreateServiceLinkedRole",                 "iam:GetContextKeysForPrincipalPolicy",                 "iam:ListAccountAliases",                 "iam:PassRole",                 "iam:SimulatePrincipalPolicy",                 "kms:CreateGrant",                 "kms:DescribeKey",                 "kms:GetKeyPolicy",                 "kms:ListAliases",                 "kms:ListKeys",                 "rds:AddTagsToResource",                 "rds:CopyDBClusterSnapshot",                 "rds:CopyDBSnapshot",                 "rds:CreateDbInstance",                 "rds:CreateTenantDatabase",                 "rds:DeleteDBClusterSnapshot",                 "rds:DeleteDBInstance",                 "rds:DeleteDBSnapshot",                 "rds:DeleteDbCluster",                 "rds:DeleteTenantDatabase",                 "rds:DescribeAccountAttributes",                 "rds:DescribeDBClusterSnapshots",                 "rds:DescribeDBClusters",                 "rds:DescribeDBEngineVersions",                 "rds:DescribeDBInstances",                 "rds:DescribeDBParameterGroups",                 "rds:DescribeDBSnapshots",                 "rds:DescribeDBSubnetGroups",                 "rds:DescribeDbClusterParameterGroups",                 "rds:DescribeDbClusterParameters",                 "rds:DescribeOptionGroups",                 "rds:DescribeOrderableDbInstanceOptions",                 "rds:ListTagsForResource",                 "rds:ModifyDBClusterSnapshotAttribute",                 "rds:ModifyDBInstance",                 "rds:ModifyDbCluster",                 "rds:RemoveTagsFromResource",                 "rds:RestoreDBInstanceFromDBSnapshot",                 "rds:RestoreDbClusterFromSnapshot",                 "servicequotas:ListServiceQuotas"             ],             "Resource": "\*"         }     ]  } |

To learn how to create IAM roles and assign them the required permissions, see [Appendix A. Creating IAM Roles in AWS](create_iam_policy_role.md).

Page updated 11/14/2025

Page content applies to build 10.0.0.232
