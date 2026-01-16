---
title: "restore_hiw_redshift_serverless"
product: "vbaws"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/restore_hiw_redshift_serverless.html"
last_updated: "4/25/2025"
product_version: "10.0.0.232"
---


In this article

|  |
| --- |
| Important |
| You can restore a Redshift Serverless namespace only to the same AWS account to which the source namespace belongs and the same AWS Region where the source namespace resides. |

To restore a Redshift Serverless namespace from a cloud-native backup, Veeam Backup for AWS performs the following steps using native [AWS capabilities](https://docs.aws.amazon.com/redshift/latest/mgmt/serverless-snapshot-restore.html):

1. [Applies only if you perform restore to a new namespace] Creates a workgroup with the settings of a source workgoup or with custom settings in the region where the source namespace resides.
2. [Applies only if you perform restore to a new namespace] Creates a namespace with the settings of a source namespace or with custom settings in the region where the source namespace resides.
3. Restores backed-up database objects and users to the restored Redshift Serverless namespace.

To learn how to restore a Redshift Serverless namespace from a Redshift Serverless backup, see [Redshift Serverless Restore](redshift_serverless_restore.md).

Page updated 4/25/2025

Page content applies to build 10.0.0.232
