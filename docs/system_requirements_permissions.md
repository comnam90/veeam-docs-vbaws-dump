---
title: "system_requirements_permissions"
product: "vbaws"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/system_requirements_permissions.html"
last_updated: "11/7/2025"
product_version: "10.0.0.232"
---


In this article

To perform data protection and disaster recovery operations, you must specify IAM roles whose permissions Veeam Backup for AWS will use to access AWS services and resources.

When you deploy Veeam Backup for AWS, the [Default Backup Restore IAM role](deploying_appliances.md) is automatically created and added to the backup appliance. This IAM role is assigned all permissions required to perform operations in the same AWS account where the backup appliance resides. However, you can manually create additional IAM roles with granular permissions to perform specific operations in this or in other AWS accounts [using the AWS Management Console](create_iam_policy_role.md), and then add them to Veeam Backup for AWS.

For more information on IAM roles in Veeam Backup for AWS, see [Managing IAM Roles](accounts_iam_roles.md).

In This Section

* [Organization Rescan IAM Permissions](organization_permissions.md)
* [Worker IAM Permissions](role_permissions_service.md)
* [Repository IAM Permissions](role_permissions_repo.md)
* [Backup IAM Permissions](role_permissions_backup.md)
* [Restore IAM Permissions](role_permissions_restore.md)
* [Full List of IAM Permissions](full_list_permissions.md)
* [IAM Permissions Changelog](permissions_changelog.md)

Page updated 11/7/2025

Page content applies to build 10.0.0.232
