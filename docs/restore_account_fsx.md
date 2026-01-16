---
title: "restore_account_fsx"
product: "vbaws"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/restore_account_fsx.html"
last_updated: "10/1/2025"
product_version: "10.0.0.232"
---


In this article

At the Account step of the wizard, choose whether you want to use an IAM role of a standalone AWS account, an AWS account of an AWS Organization, or one-time access keys of an IAM user to allow Veeam Backup & Replication to perform the restore operation. For information on the permissions that the IAM role or IAM user must have to perform the restore operation, see [FSx Restore IAM Permissions](role_permissions_restore_fsx.md).

|  |
| --- |
| Note |
| Depending on whether the AWS account to which the source FSx file systems belong is a part of an AWS Organization, Veeam Backup for AWS automatically does either of the following:   * If the AWS account is a part of an AWS Organization, Veeam Backup for AWS chooses the AWS account itself and the organization identity that contains the account — in this case, the Organization account option is selected by default. * If the AWS account is not a part of an AWS Organization, Veeam Backup for AWS chooses an IAM role from the AWS account — in this case, the IAM Role option is selected by default. |

Specifying IAM Role of Standalone AWS Account

To specify an IAM role to be used for the restore operation, select the IAM role option and choose the necessary IAM role from the list. Keep in mind that the selected role must belong to an AWS account to which you plan to restore FSx file systems.

For an IAM role to be displayed in the list of available roles, it must be added to Veeam Backup for AWS with the Amazon FSx Restore operation selected as described in section [Adding IAM Roles](iam_roles_add.md). If you have not added the necessary IAM role to Veeam Backup for AWS beforehand, you can do it without closing the FSx Restore wizard. To do that, click Add and complete the Add IAM Role wizard.

|  |
| --- |
| Important |
| It is recommended that you check whether the selected IAM role has all the permissions required to perform the operation. If some permissions of the IAM role are missing, the restore operation may fail to complete successfully. To run the IAM role permission check, click Check Permissions and follow the instructions provided in section [Checking IAM Role Permissions](iam_roles_check.md#wizard). |

Specifying AWS Account of AWS Organization

To specify an AWS account to be used for the restore operation, select the Organization account option. Since Veeam Backup for AWS does not support cross-account recovery of FSx file systems, Veeam Backup for AWS automatically chooses the AWS account to which the source FSx file systems belong and the organization identity (either an entire AWS Organization or a limited scope of organizational units) that contains the account.

For an organization identity to be displayed in the list of available identities, it must be added to Veeam Backup for AWS as described in section [Adding AWS Organizations](organizations_add.md). For an AWS account to be displayed in the list of available accounts, it must be included in the the selected organization identity.

Specifying One-Time Access Keys of IAM User

To specify one-time access keys to be used for the restore operation, select the Temporary access keys option and use the Access key and Secret key fields to provide the [access keys of an IAM user](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_access-keys.html). Note that the IAM user must belong to an AWS account where the source file systems reside.

|  |
| --- |
| Note |
| Veeam Backup for AWS does not store one-time access keys in the configuration database. |

[![Restoring FSx File Systems](images/restore_account_fsx.webp)](images/restore_account_fsx.webp "Restoring FSx File Systems")

Page updated 10/1/2025

Page content applies to build 10.0.0.232
