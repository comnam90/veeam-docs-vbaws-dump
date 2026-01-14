---
title: "update_role"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/update_role.html"
last_updated: "4/15/2025"
product_version: "10.0.0.232"
---


In this article

When you update the backup appliance to a newer version, the improvements and new features instantly become available in Veeam Backup for AWS. However, to meet new requirements, IAM roles must be assigned missing permissions manually either using the Veeam Backup for AWS Web UI or the AWS Management Console.

To update the IAM role, run a permission check for this role at the IAM Roles tab as described in section [Checking IAM Role Permissions](iam_roles_check.md#check_permissions_iam_role_tab). The permission check verifies whether the IAM role has all the permissions required to perform operations with the workloads selected at the Permissions step of the Add IAM Role wizard. You can track the progress and view the results of the permission check in the AWS Permission Check window. If some of the IAM role permissions are missing, the check will complete with errors, and the Missing Permissions column will display the list of permissions that must be granted to the IAM role. You can grant the missing permissions to the IAM role using the AWS Management Console or [instruct Veeam Backup for AWS to do it](iam_roles_check.md). To learn how to grant permissions to IAM roles using the AWS Management Console, see [Appendix B. Creating IAM Policies in AWS](create_iam_policy.md).

|  |
| --- |
| Note |
| The [Default Backup Restore IAM role](deploying_appliances.md) is updated automatically during the upgrade of backup appliances from the Veeam Backup & Replication console. For more information, see [Updating Appliances Using Console](upgrade_appliance_console.md#default_role). |

Page updated 4/15/2025

Page content applies to build 10.0.0.232
