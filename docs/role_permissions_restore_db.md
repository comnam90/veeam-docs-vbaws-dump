---
title: "role_permissions_restore_db"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/role_permissions_restore_db.html"
last_updated: "10/1/2025"
product_version: "10.0.0.232"
---


In this article

To perform RDS database restore operations, IAM roles and IAM users specified in the [restore settings](restore_rds_database_workers.md), or IAM roles specified in the [organization settings](organization_add_settings.md), must meet the following requirements:

1. The backup appliance must be granted permissions to assume the IAM roles. For more information on the requirements for adding IAM roles, see [Before You Begin](byb_roles.md).
2. The RDS service must be granted permissions to assume the IAM roles.

To allow the RDS service to assume an IAM role, configure trust relationships for the role and add the following statement to the trust policy:

|  |
| --- |
| {   "Version": "2012-10-17",   "Statement": [     {       "Effect": "Allow",       "Action": "sts:AssumeRole",       "Principal": {         "Service": "rds.amazonaws.com"       }     }   ]  } |

To learn how to modify role trust policies, see [AWS Documentation](https://docs.aws.amazon.com/IAM/latest/UserGuide/roles-managingrole-editing-console.html#roles-managingrole_edit-trust-policy).

1. The IAM roles must be granted the following permissions:

|  |
| --- |
| {     "Version": "2012-10-17",     "Statement": [         {             "Effect": "Allow",             "Action": [                 "ec2:AuthorizeSecurityGroupEgress",                 "ec2:AuthorizeSecurityGroupIngress",                 "ec2:CreateKeyPair",                 "ec2:CreateSecurityGroup",                 "ec2:CreateTags",                 "ec2:DeleteKeyPair",                 "ec2:DeleteSecurityGroup",                 "ec2:DescribeAccountAttributes",                 "ec2:DescribeAvailabilityZones",                 "ec2:DescribeImages",                 "ec2:DescribeInstanceAttribute",                 "ec2:DescribeInstances",                 "ec2:DescribeInternetGateways",                 "ec2:DescribeKeyPairs",                 "ec2:DescribeRegions",                 "ec2:DescribeRouteTables",                 "ec2:DescribeSecurityGroups",                 "ec2:DescribeSubnets",                 "ec2:DescribeVpcs",                 "ec2:DescribeVpcEndpoints",                 "ec2:ModifyInstanceAttribute",                 "ec2:RevokeSecurityGroupEgress",                 "ec2:RevokeSecurityGroupIngress",                 "ec2:RunInstances",                 "ec2:StartInstances",                 "ec2:TerminateInstances",                 "iam:GetContextKeysForPrincipalPolicy",                 "iam:GetInstanceProfile",                 "iam:GetRole",                 "iam:ListInstanceProfilesForRole",                 "iam:PassRole",                 "iam:SimulatePrincipalPolicy",                 "rds:DescribeDBInstances",                 "rds:DescribeDBSubnetGroups",                 "rds:ModifyDBInstance",                 "s3:CreateBucket",                 "s3:DeleteBucket",                 "s3:DeleteObject",                 "s3:ListAllMyBuckets",                 "s3:ListBucket",                 "s3:PutBucketPolicy",                 "s3:PutObject",                 "servicequotas:listServiceQuotas",                 "sqs:CreateQueue",                 "sqs:DeleteMessage",                 "sqs:DeleteQueue",                 "sqs:ListQueues",                 "sqs:ReceiveMessage",                 "sqs:SendMessage",                 "sqs:SetQueueAttributes",                 "ssm:GetCommandInvocation",                 "ssm:GetParameter",                 "ssm:SendCommand"             ],             "Resource": "\*"         }     ]  } |

To learn how to create IAM roles and assign them the required permissions, see [Appendix A. Creating IAM Roles in AWS](create_iam_policy_role.md).

Page updated 10/1/2025

Page content applies to build 10.0.0.232
