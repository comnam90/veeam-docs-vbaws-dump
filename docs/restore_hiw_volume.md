---
title: "restore_hiw_volume"
product: "vbaws"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/restore_hiw_volume.html"
last_updated: "9/12/2024"
product_version: "10.0.0.232"
---


In this article

To restore EBS volumes from cloud-native snapshots, manual cloud-native snapshots and snapshot replicas, Veeam Backup for AWS uses native [AWS capabilities](https://docs.aws.amazon.com/prescriptive-guidance/latest/backup-recovery/restore.html). To restore EBS volumes from image-level backups, Veeam Backup for AWS performs the following steps:

1. [Applies only if you perform restore from an archived backup] Retrieves data from the archived restore point.
2. Deploys a worker instance in the AWS Region where the restored EBS volumes will reside.
3. Creates empty EBS volumes and attaches them to the worker instance.

The number of empty EBS volumes equals the number of volumes you selected to restore.

1. Restores backed-up data to the empty EBS volumes on the worker instance.
2. Detaches EBS volumes with restored data from the worker instance.
3. Removes the worker instance from Amazon EC2.

|  |
| --- |
| Note |
| Veeam Backup for AWS does not attach restored EBS volumes to any EC2 instances — the volumes are placed to the specified location as standalone EBS volumes. |

To learn how to restore EBS volumes attached to an EC2 instance from a cloud-native snapshot, snapshot replica or an image-level backup, see [Performing Volume-Level Restore](restore_volume_perform.md).

Page updated 9/12/2024

Page content applies to build 10.0.0.232
