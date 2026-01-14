---
title: "role_permissions_backup_redshift_serverless"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/role_permissions_backup_redshift_serverless.html"
last_updated: "4/28/2025"
product_version: "10.0.0.232"
---


In this article

Veeam Backup for AWS uses Redshift Serverless Backup IAM roles to perform the following operations:

* To enumerate resources added to a backup policy.
* To create backups of Redshift Serverless namespaces.

To perform these operations, IAM roles specified in the [organization settings](organization_add_settings.md) or in the [Redshift Serverless backup policy settings](add_policy_scope_redshift_serverless.md#account) must meet the following requirements:

1. The backup appliance must be granted permissions to assume the IAM roles. For more information on the requirements for adding IAM roles, see [Before You Begin](byb_roles.md).

1. The IAM roles must be granted the following permissions:

* IAM roles specified in the [backup policy settings](add_policy_scope_redshift_serverless.md#role):

|  |
| --- |
| {     "Version": "2012-10-17",     "Statement": [         {             "Effect": "Allow",             "Action": [                 "ec2:DescribeAvailabilityZones",                 "ec2:DescribeRegions",                 "redshift-serverless:CreateSnapshot",                 "redshift-serverless:DeleteSnapshot",                 "redshift-serverless:GetSnapshot",                 "redshift-serverless:ListNamespaces",                 "redshift-serverless:ListWorkgroups",                 "redshift-serverless:ListTagsForResource",                 "redshift-serverless:ListSnapshots",                 "redshift-serverless:TagResource",                 "iam:GetContextKeysForPrincipalPolicy",                 "iam:SimulatePrincipalPolicy",                 "iam:ListAccountAliases",                 "kms:DescribeKey",                 "events:DeleteRule",                 "events:DescribeRule",                 "events:ListTargetsByRule",                 "events:PutRule",                 "events:PutTargets",                 "events:RemoveTargets",                 "sns:CreateTopic",                 "sns:DeleteTopic",                 "sns:ListSubscriptionsByTopic",                 "sns:ListTopics",                 "sns:SetTopicAttributes",                 "sns:Subscribe",                 "sns:Unsubscribe",                 "sqs:CreateQueue",                 "sqs:DeleteMessage",                 "sqs:DeleteQueue",                 "sqs:ListQueues",                 "sqs:ReceiveMessage",                 "sqs:SetQueueAttributes"             ],             "Resource": "\*"         }     ]  } |

* IAM roles used to perform backup operations manually as described in section [Creating Redshift Serverless Backups Manually](backup_manual_redshift_serverless.md):

|  |
| --- |
| {     "Version": "2012-10-17",     "Statement": [         {             "Effect": "Allow",             "Action": [                 "ec2:DescribeAvailabilityZones",                 "ec2:DescribeRegions",                 "iam:GetContextKeysForPrincipalPolicy",                 "iam:ListAccountAliases",                 "iam:SimulatePrincipalPolicy",                 "redshift-serverless:CreateSnapshot",                 "redshift-serverless:DeleteSnapshot",                 "redshift-serverless:GetSnapshot",                 "redshift-serverless:ListNamespaces",                 "redshift-serverless:ListWorkgroups",                 "redshift-serverless:ListTagsForResource",                 "redshift-serverless:ListSnapshots",                 "redshift-serverless:TagResource",                 "kms:DescribeKey"             ],             "Resource": "\*"         }     ]  } |

To learn how to create IAM roles and assign them the required permissions, see [Appendix A. Creating IAM Roles in AWS](create_iam_policy_role.md).

Page updated 4/28/2025

Page content applies to build 10.0.0.232
