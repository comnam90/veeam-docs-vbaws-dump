---
title: "restore_hiw_redshift"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/restore_hiw_redshift.html"
last_updated: "11/26/2025"
product_version: "10.0.0.232"
---


In this article

|  |
| --- |
| Important |
| You can restore a Redshift cluster only to the same AWS account to which the source cluster belongs and the same AWS Region where the source cluster resides. |

To restore a Redshift cluster from a backup, Veeam Backup for AWS performs the following steps using native [AWS capabilities](https://docs.aws.amazon.com/aws-backup/latest/devguide/redshift-restores.html):

1. Creates a cluster in the specified location.
2. Modifies the configuration setting values of the created Redshift cluster.
3. Restores backed-up databases to the restored Redshift clusters.

To learn how to restore a Redshift cluster from a Redshift backup, see [Redshift Clusters Restore](redshift_restore.md).

Page updated 11/26/2025

Page content applies to build 10.0.0.232
