---
title: "add_policy_target_settings_backups_dynamo"
product: "vbaws"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/add_policy_target_settings_backups_dynamo.html"
last_updated: "10/8/2025"
product_version: "10.0.0.232"
---


In this article

To specify backup vaults that will be used to store backups of the selected DynamoDB tables, do the following:

1. In the Backups section of the Targets step of the wizard, click Choose backup vaults.
2. In the Choose backup vaults window, for each AWS Region included in the policy, specify a backup vault to save and organize table backups. To do that:

1. Select an AWS Region and click Edit.
2. [Applies only if you have chosen the Account option at the Sources step of the wizard] In the Edit Backup Vault window, from the Backup vault drop-down list, select the necessary backup vault.

For a backup vault to be displayed in the list of available backup vaults, it must be created in the AWS Backup console as described in [AWS Documentation](https://docs.aws.amazon.com/aws-backup/latest/devguide/create-a-vault.html#creating-a-vault-console). If no custom backup vaults exist in the selected AWS Region, the list will contain the default backup vault only.

1. [Applies only if you have chosen the Organization option at the Sources step of the wizard] In the Edit Backup Vault window, in the Tag key and Tag value fields, specify a key and value of the AWS tag associated with the necessary backup vaults. The backup vault with the specified tag must be created in each AWS account within the AWS Organization or organizational units added to the backup policy. Note that the specified tag must not be associated with multiple backup vaults in the same AWS Region and account within the organization.

|  |
| --- |
| Important |
| * Veeam Backup for AWS does not support storing backups in [logically air-gapped vaults](https://docs.aws.amazon.com/aws-backup/latest/devguide/logicallyairgappedvault.html) and in backup vaults with the [AWS Backup Vault Lock](https://docs.aws.amazon.com/aws-backup/latest/devguide/vault-lock.html) feature enabled.  * Make sure policies assigned to the selected backup vault allow Veeam Backup for AWS to access vault resources and to perform backup, backup copy and restore operations, as well as to remove backups. For more information on vault access policies, see [AWS Documentation](https://docs.aws.amazon.com/aws-backup/latest/devguide/create-a-vault-access-policy.html). * For Veeam Backup for AWS to be able to back up DynamoDB tables, you must configure the AWS Backup settings to enable both the Opt-in service and the advanced features for Amazon DynamoDB backups. Otherwise, Veeam Backup for AWS will automatically enable these settings for each AWS Region specified in the Backups section in your AWS account while performing backup operations. For more information on advanced DynamoDB backup, see [AWS Documentation](https://docs.aws.amazon.com/aws-backup/latest/devguide/advanced-ddb-backup.html). |

1. Click Save.

1. To save changes made to the backup policy settings, click Apply.

[![Creating DynamoDB Backup Policy](images/backup_add_backup_settings_dynamodb.webp)](images/backup_add_backup_settings_dynamodb.webp "Creating DynamoDB Backup Policy")

Page updated 10/8/2025

Page content applies to build 10.0.0.232
