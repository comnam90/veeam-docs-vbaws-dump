---
title: "restore_hiw_ec2_entire"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/restore_hiw_ec2_entire.html"
last_updated: "9/12/2024"
product_version: "10.0.0.232"
---


In this article

To restore EC2 instances from cloud-native snapshots, manual cloud-native snapshots and snapshot replicas, Veeam Backup for AWS uses native [AWS capabilities](https://docs.aws.amazon.com/prescriptive-guidance/latest/backup-recovery/restore.html). To restore EC2 instances from image-level backups, Veeam Backup for AWS performs the following steps:

1. [Applies only if you perform restore from an archived backup] Retrieves data from the archived restore point.
2. Deploys a worker instance in the AWS Region where the restored EC2 instance will reside.
3. Creates empty EBS volumes and attaches them to the worker instance.

The number of empty EBS volumes equals the number of EBS volumes attached to the backed-up EC2 instance.

1. Restores backed-up data to the empty EBS volumes on the worker instance.
2. Detaches EBS volumes with restored data from the worker instance.

1. Removes the worker instance from Amazon EC2.
2. Creates an EC2 instance in the specified location.
3. Attaches EBS volumes with restored data to the target EC2 instance.
4. [Applies only if you perform restore to the original location] Powers off the source EC2 instance and removes it from Amazon EC2.

To learn how to restore an entire EC2 instance from a cloud-native snapshot, snapshot replica or an image-level backup, see [EC2 Restore](ec2_restore.md).

Page updated 9/12/2024

Page content applies to build 10.0.0.232
