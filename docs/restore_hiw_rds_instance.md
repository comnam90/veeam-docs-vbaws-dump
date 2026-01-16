---
title: "restore_hiw_rds_instance"
product: "vbaws"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/restore_hiw_rds_instance.html"
last_updated: "7/10/2024"
product_version: "10.0.0.232"
---


In this article

To restore a DB instance from a snapshot, Veeam Backup for AWS performs the following steps using native [AWS capabilities](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/CHAP_Tutorials.RestoringFromSnapshot.html):

1. Creates a DB instance in the specified location.
2. Modifies the configuration setting values of the created DB instance.
3. Restores backed-up databases to the restored DB instance.

To restore an Aurora DB cluster from a snapshot, Veeam Backup for AWS performs the following steps using native [AWS capabilities](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/CHAP_Tutorials.RestoringFromSnapshot.html):

1. Creates an Aurora DB cluster in the specified location.
2. Restores backed-up databases to the created Aurora DB cluster.
3. Modifies the configuration setting values of the created Aurora DB cluster.
4. In the created Aurora DB cluster, creates all backed-up DB instances (when restoring to the original location) or creates the primary DB instance (when restoring to a new location).
5. Modifies the configuration setting values of each created DB instance.

To learn how to restore a DB instance or an Aurora DB cluster from a cloud-native snapshot or snapshot replica, see [RDS Restore](rds_restore.md).

Page updated 7/10/2024

Page content applies to build 10.0.0.232
