---
title: "Before You Begin"
product: "vbaws"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/add_redshift_cluster_policy_byb.html"
last_updated: "3/12/2026"
product_version: "10.0.0.232"
---

# Before You Begin


Before you protect Redshift clusters, consider the following:

* Veeam Backup for AWS supports backup of only those Redshift cluster properties that are described in section [Protecting Redshift Clusters](overview_redshift.md#parameters).
* Veeam Backup for AWS supports creating cloud-native backups for Redshift clusters only to the same AWS accounts to which the source clusters belong and the same AWS Region where the source clusters reside.
* For Veeam Backup for AWS to be able to create cloud-native backups of Redshift clusters, you must enable the Opt-in service for the Redshift resource type in the AWS Backup settings. Otherwise, Veeam Backup for AWS will automatically enable the service for each AWS Region specified in the backup policy settings in your AWS account while performing backup operations. For more information on considerations for using AWS Backup with Amazon Redshift, see [AWS Documentation](https://docs.aws.amazon.com/redshift/latest/mgmt/managing-aws-backup.html#managing-aws-backup-considerations).
* Veeam Backup for AWS does not support storing cloud-native backups in [logically air-gapped vaults](https://docs.aws.amazon.com/aws-backup/latest/devguide/logicallyairgappedvault.html) and in backup vaults with the [AWS Backup Vault Lock](https://docs.aws.amazon.com/aws-backup/latest/devguide/vault-lock.html) feature enabled.

* Veeam Backup for AWS runs retention sessions at 4:00 AM by default, according to the time zone set on the backup appliance. If you schedule backup policies to execute at 4:00 AM, the backup policies and retention tasks will be queued.


