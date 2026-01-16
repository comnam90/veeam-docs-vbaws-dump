---
title: "organization_permissions"
product: "vbaws"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/organization_permissions.html"
last_updated: "4/28/2025"
product_version: "10.0.0.232"
---


In this article

To allow Veeam Backup for AWS to collect information on AWS Organizations, the Organization rescan IAM role specified in the [organization settings](organization_add_settings.md) must meet the following requirements:

1. The backup appliance must be granted permissions to assume the IAM role. For more information on the requirements for adding IAM roles, see [Before You Begin](byb_roles.md).

1. The IAM role must be granted the following permissions:

|  |
| --- |
| {     "Version": "2012-10-17",     "Statement": [         {             "Effect": "Allow",             "Action": [                 "iam:GetContextKeysForPrincipalPolicy",                 "iam:ListAccountAliases",                 "iam:SimulatePrincipalPolicy",                 "organizations:DescribeAccount",                 "organizations:DescribeOrganizationalUnit",                 "organizations:DescribeOrganization",                 "organizations:ListChildren",                 "organizations:ListRoots"             ],             "Resource": "\*"         }     ]  } |

To learn how to create IAM roles and assign them the required permissions, see [Appendix A. Creating IAM Roles in AWS](create_iam_policy_role.md).

Page updated 4/28/2025

Page content applies to build 10.0.0.232
