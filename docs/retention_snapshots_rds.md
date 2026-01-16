---
title: "retention_snapshots_rds"
product: "vbaws"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/retention_snapshots_rds.html"
last_updated: "10/13/2025"
product_version: "10.0.0.232"
---


In this article

For cloud-native snapshots and snapshot replicas, Veeam Backup for AWS retains the number of latest restore points defined in backup scheduling settings.

During every successful backup session, Veeam Backup for AWS creates a new restore point. If Veeam Backup for AWS detects that the number of restore points in the snapshot chain exceeds the retention limit, the earliest restore point is removed from the chain. For more information on the snapshot deletion process, see [AWS Documentation](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_DeleteSnapshot.html).

[![EC2 Snapshot Retention](images/snapshot_retention.webp)](images/snapshot_retention.webp "EC2 Snapshot Retention")

|  |
| --- |
| Note |
| Veeam Backup for AWS does not apply retention policy to cloud-native snapshots created manually. To learn how to remove them, see [Managing Backed-Up Data](snapshots_remove_individual_rds.md). |

Page updated 10/13/2025

Page content applies to build 10.0.0.232
