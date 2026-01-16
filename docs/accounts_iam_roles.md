---
title: "accounts_iam_roles"
product: "vbaws"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/accounts_iam_roles.html"
last_updated: "8/12/2025"
product_version: "10.0.0.232"
---


In this article

|  |
| --- |
| Note |
| This section assumes that you have a good understanding of [IAM Roles](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles.html), [IAM Policies](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_create.html) and [IAM Identity Permissions](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_manage-attach-detach.html). |

Veeam Backup for AWS uses permissions of IAM roles to access AWS services and resources, and to perform the backup and restore operations. For example, Veeam Backup for AWS may require access to the following AWS resources:

* EC2 resources — to display the list of EC2 instances in backup policy settings, to create cloud-native snapshots, snapshot replicas, to deploy worker instances and to restore backed-up data.
* S3 resources — to store backed-up data in backup repositories, to perform transform operations with backup chains, and to copy backed-up data from backup repositories to worker instances during restore.

For each data protection and disaster recovery operation performed by Veeam Backup for AWS, you must specify an IAM role. By design, Veeam Backup for AWS comes with the Default Backup Restore IAM role. This role is added to the configuration database upon product installation and is automatically assigned all the permissions required to perform data protection tasks within the initial AWS account in which the backup appliance resides.

If you want to back up and restore resources in other AWS accounts, or if you want to specify custom IAM roles with granular permissions to perform specific operations, [add IAM roles to Veeam Backup for AWS](iam_roles_add.md). You can add IAM roles that already exist in your AWS accounts, or instruct Veeam Backup for AWS to automatically create IAM roles with predefined permission sets in AWS — and then add these roles to the backup appliance.

To help you configure the necessary IAM roles in AWS and grant all the required permissions, Veeam Backup for AWS allows you to [create IAM role templates](iam_template_add.md). Alternatively, you can create IAM roles in the AWS Management Console as described in [Appendix A. Creating IAM Roles in AWS](create_iam_policy_role.md).

In This Section

* [Adding IAM Roles](iam_roles_add.md)
* [Editing IAM Role Settings](iam_roles_edit.md)
* [Checking IAM Role Permissions](iam_roles_check.md)
* [Removing IAM Roles](iam_roles_remove.md)

Page updated 8/12/2025

Page content applies to build 10.0.0.232
