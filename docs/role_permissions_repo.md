---
title: "role_permissions_repo"
product: "vbaws"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/role_permissions_repo.html"
last_updated: "11/12/2024"
product_version: "10.0.0.232"
---


In this article

To allow Veeam Backup for AWS to create backup repositories in Amazon S3 buckets and to access the repository when performing backup and restore operations, IAM roles specified in the [repository settings](repository_add_folder.md) must meet the following requirements:

1. The backup appliance must be granted permissions to assume the IAM roles. For more information on the requirements for adding IAM roles, see [Before You Begin](byb_roles.md).
2. The Amazon S3 Batch Operations service must be granted permissions to assume the IAM roles.

To allow the AWS service to assume an IAM role, configure trust relationships for the role and add the following statement to the trust policy:

|  |
| --- |
| {   "Version": "2012-10-17",   "Statement": [     {       "Effect": "Allow",       "Action": "sts:AssumeRole",       "Principal": {         "Service": "batchoperations.s3.amazonaws.com"       }     }   ]  } |

To learn how to modify role trust policies, see [AWS Documentation](https://docs.aws.amazon.com/IAM/latest/UserGuide/roles-managingrole-editing-console.html#roles-managingrole_edit-trust-policy).

1. The IAM roles must be granted the following permissions:

|  |
| --- |
| {     "Version": "2012-10-17",     "Statement": [         {             "Effect": "Allow",             "Action": [                 "ec2:DescribeRegions",                 "ec2:DescribeVpcEndpoints",                 "iam:GetContextKeysForPrincipalPolicy",                 "iam:SimulatePrincipalPolicy",                 "iam:GetRole",                 "iam:PassRole",                 "iam:ListAccountAliases",                 "kms:ListKeys",                 "kms:ListAliases",                 "kms:DescribeKey",                 "kms:Encrypt",                 "kms:Decrypt",                 "s3:ListAllMyBuckets",                 "s3:CreateJob",                 "s3:DescribeJob",                 "s3:PutObject",                 "s3:GetObject",                 "s3:DeleteObject",                 "s3:RestoreObject",                 "s3:GetObjectRetention",                 "s3:PutObjectRetention",                 "s3:GetObjectVersion",                 "s3:DeleteObjectVersion",                 "s3:ListBucket",                 "s3:ListBucketVersions",                 "s3:GetBucketLocation",                 "s3:GetBucketVersioning",                 "s3:GetBucketObjectLockConfiguration"             ],             "Resource": "\*"         }     ]  } |

|  |
| --- |
| Important |
| If you plan to use KMS key encryption for backup repositories, consider the following:   * The key policy of an AWS KMS key that will be used to encrypt a repository must allow the IAM role specified in the repository settings access to the key. * AWS managed keys cannot be used to encrypt repositories due to [AWS limitations](https://docs.aws.amazon.com/kms/latest/developerguide/concepts.html#aws-managed-cmk). |

To learn how to create IAM roles and assign them the required permissions, see [Appendix A. Creating IAM Roles in AWS](create_iam_policy_role.md).

Page updated 11/12/2024

Page content applies to build 10.0.0.232
