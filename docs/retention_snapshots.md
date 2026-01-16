---
title: "retention_snapshots"
product: "vbaws"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/retention_snapshots.html"
last_updated: "12/8/2025"
product_version: "10.0.0.232"
---


In this article

Depending on the data protection scenario, Veeam Backup for AWS retains cloud-native snapshots as follows:

* In days/months/years — for snapshots and snapshot replicas produced by SLA-based backup policies.

Restore points can be kept in a snapshot chain only for the period of time defined in snapshot scheduling settings as described in section [Adding SLA Templates](sla_add_snapshot_settings.md). If Veeam Backup for AWS detects that a restore point is older than the specified time limit, it removes this restore point from the snapshot chain.

* In restore points — for snapshots and snapshot replicas produced by schedule-based backup policies.

A snapshot chain can contain only the allowed number of restore points defined in backup scheduling settings as described in section [Creating Schedule-Based EC2 Backup Policies](add_policy_schedule_retention.md). If Veeam Backup for AWS detects that the number of restore points in the snapshot chain exceeds the retention limit, it removes the earliest restore point from the chain.

Regardless of the number of restore points that you specify in the retention policy settings, Veeam Backup for AWS permanently retains an additional cloud-native snapshot in the chain by design, which is required for proper CBT functioning. To learn how the CBT mechanism works, see [Changed Block Tracking](cbt.md). For more information on the snapshot deletion process, see [AWS Documentation](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-deleting-snapshot.html#ebs-deleting-snapshot-incremental).

[![EC2 Snapshot Retention](images/snapshot_retention.webp)](images/snapshot_retention.webp "EC2 Snapshot Retention")

|  |
| --- |
| Notes |
| * If you add an EC2 instance to an SLA-based policy after it was previously protected by a schedule-based policy, Veeam Backup for AWS will start applying the retention settings configured in the SLA template to the entire snapshot chain. * Retention policy settings configured when creating schedule-based backup policies and SLA templates do not apply to cloud-native snapshots taken manually. However, you can configure their own retention settings as described in section [Performing EC2 Backup](snapshot_manual.md), or remove these snapshots manually as described in section [Managing Backed-Up EC2 Instance Data](backups_view_ec2.md). |

Related Topics

* [CBT Impact on Snapshot Retention](cbt_retention.md)
* [Configuring Global Retention Settings](retention_settings.md#snapshots)

Page updated 12/8/2025

Page content applies to build 10.0.0.232
