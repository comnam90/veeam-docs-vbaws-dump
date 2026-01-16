---
title: "backup_manual_dynamo"
product: "vbaws"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/backup_manual_dynamo.html"
last_updated: "10/8/2025"
product_version: "10.0.0.232"
---


In this article

Veeam Backup for AWS allows you to manually create backups of DynamoDB tables. You can instruct Veeam Backup for AWS to store the created backups in the same AWS Regions where the processed DynamoDB tables reside, or in a different AWS Region.

|  |
| --- |
| Note |
| Veeam Backup for AWS does not include backups created manually in the backup chain and does not apply the configured retention policy settings to these backups. This means that the backups are kept in your AWS environment unless you remove them manually, as described in section [Managing Backed-Up DynamoDB Data](backups_view_dynamo.md). |

To manually create a backup of a DynamoDB table, do the following:

1. Navigate to Resources > Databases > DynamoDB.
2. Select the necessary table and click Take Backup Now.

For a DynamoDB table to be displayed in the list of available tables, an AWS Region where the table resides must be added to any of [configured DynamoDB backup policies](add_policy_source_settings_dynamo.md), and the IAM role specified in the backup policy settings or in the organization settings must have permissions to access the table. For more information on the required permissions, see [DynamoDB Backup IAM Role Permissions](role_permissions_backup_dynamo.md).

1. Complete the Take Manual Backup wizard:

1. At the Account step of the wizard, specify an IAM role whose permissions Veeam Backup for AWS will use to create the backup. The specified IAM role must belong to the same AWS account to which the processed DynamoDB tables reside.

For an IAM role to be displayed in the list of available roles, it must be added to Veeam Backup for AWS as described in section [Adding IAM Roles](iam_roles_add.md).

|  |
| --- |
| Important |
| Veeam Backup for AWS does not support taking manual snapshot using IAM roles specified in the [organization settings](organization_add_settings.md). |

1. In the Backup vault section of the Settings step of the wizard, click Edit Location Settings.

In the Choose region and backup vault window, specify the following settings:

1. From the Target region drop-down list, select an AWS Region where manual backups will be stored.
2. In the Backup vault section, select a backup vault that will be used to store table backups.

For a backup vault to be displayed in the list of available vaults, it must be created in the AWS Backup console as described in [AWS Documentation](https://docs.aws.amazon.com/aws-backup/latest/devguide/create-a-vault.html#creating-a-vault-console). If you have not created a backup vault for the selected AWS Region, Veeam Backup for AWS will display only the default backup vault created for the AWS Region automatically.

1. To save changes made to the location settings, click Apply.

|  |
| --- |
| Important |
| * Veeam Backup for AWS does not support storing backups in [logically air-gapped vaults](https://docs.aws.amazon.com/aws-backup/latest/devguide/logicallyairgappedvault.html) and in backup vaults with the [AWS Backup Vault Lock](https://docs.aws.amazon.com/aws-backup/latest/devguide/vault-lock.html) feature enabled.  * Make sure policies assigned to the selected backup vault allow Veeam Backup for AWS to access vault resources and to perform backup, backup copy and restore operations. For more information on vault access policies, see [AWS Documentation](https://docs.aws.amazon.com/aws-backup/latest/devguide/create-a-vault-access-policy.html).  * For Veeam Backup for AWS to be able to back up DynamoDB tables, you must configure the AWS Backup settings to enable both the Opt-in service and the advanced features for Amazon DynamoDB backups. Otherwise, Veeam Backup for AWS will automatically enable these settings for each AWS Region specified in the backup settings in your AWS account while performing backup operations. For more information on advanced DynamoDB backup, see [AWS Documentation](https://docs.aws.amazon.com/aws-backup/latest/devguide/advanced-ddb-backup.html). |

1. At the Tags section of the Settings step of the wizard, to assign tags to the created backup, click Edit Tag Settings.

In the Tag configuration window, specify tag settings:

1. To assign already existing AWS tags from the processed table, select the Copy tags from source table check box.

If you choose to copy tags from the source table, Veeam Backup for AWS will first create a backup of the DynamoDB table and assign to the created backup AWS tags with Veeam metadata, then Veeam Backup for AWS will copy tags from the processed table and, finally, assign the copied AWS tags to the backup.

1. To assign your own custom AWS tags, set the Add custom tags to created backup toggle to On and specify the tags explicitly. To do that, use the Key and Value fields to specify a key and a value for the new custom AWS tag, and then click Add. Note that you cannot add more than 5 custom AWS tags.

If you choose to add custom tags to the created backups, Veeam Backup for AWS will assign the specified tags right after it creates a backup.

1. To save changes made to the tag settings, click Apply.

1. At the Summary step of the wizard, review configuration information, choose whether you want to proceed to the [Session Log page](reporting.md#ui) to track the progress of snapshot creation, and click Finish.

[![Creating DynamoDB Backup Manually](images/backup_manual_dynamodb.webp)](images/backup_manual_dynamodb.webp "Creating DynamoDB Backup Manually")

Page updated 10/8/2025

Page content applies to build 10.0.0.232
