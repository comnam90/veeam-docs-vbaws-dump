---
title: "Performing EFS Backup"
product: "vbaws"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/perform_efs_backup.html"
last_updated: "3/12/2026"
product_version: "10.0.0.232"
---

# Performing EFS Backup


One backup policy can be used to process one or more EFS file systems either within one AWS account or within an entire AWS Organization. The scope of data that you can protect in an AWS account is limited by permissions of an IAM role that is specified in the backup policy settings, whereas the scope of data that you can protect in an AWS Organization is limited by permissions of an IAM role that is specified in the organization settings.

|  |
| --- |
| Note |
| If you plan to receive email notifications on backup policy results, configure email notification settings first. For more information, see [Configuring Global Notification Settings](email_settings.md). |

To schedule data protection tasks to run automatically, [create backup policies](policies_create_efs.md). For each protected EFS systems, you can also [take a backup manually](backup_manual_efs.md) when needed.

|  |
| --- |
| Important |
| * Veeam Backup for AWS supports creating cloud-native backups for EFS file systems only to the same AWS accounts to which the source file systems belong.  * Veeam Backup for AWS does not support storing cloud-native backups in [logically air-gapped vaults](https://docs.aws.amazon.com/aws-backup/latest/devguide/logicallyairgappedvault.html) and in backup vaults with the [AWS Backup Vault Lock](https://docs.aws.amazon.com/aws-backup/latest/devguide/vault-lock.html) feature enabled.  * Indexing of the backed up EFS file systems is not supported in the Free edition of Veeam Backup for AWS. For more information on license editions, see [Licensing](licensing.md).  * Veeam Backup for AWS runs retention sessions at 4:00 AM by default, according to the time zone set on the backup appliance. If you schedule backup policies to execute at 4:00 AM, the backup policies and retention tasks will be queued. |


