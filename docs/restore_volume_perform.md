---
title: "restore_volume_perform"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/restore_volume_perform.html"
last_updated: "12/12/2025"
product_version: "10.0.0.232"
---


In this article

In case a disaster strikes, you can restore corrupted EBS volumes of an EC2 instance from a cloud-native snapshot, snapshot replica or image-level backup. Veeam Backup for AWS allows you to restore EBS volumes to the original location or to a new location.

|  |
| --- |
| Notes |
| * Veeam Backup for AWS does not attach restored EBS volumes to any EC2 instances — the volumes are placed to the specified location as standalone EBS volumes. * To restore an EC2 instance from a backup that is stored in an archive backup repository, you must retrieve the archived data first. You can either retrieve the archived data manually before you begin the restore operation, or launch the data retrieval process right from the Volume Restore wizard. To learn how to retrieve data manually, see [Retrieving EC2 Data From Archive](data_retrieval.md). |

How to Perform Volume Restore

To restore EBS volumes of a protected EC2 instance, do the following:

1. [Launch the Volume Restore wizard](restore_entire_launch.md).
2. [Select a restore point](restore_volume_settings.md).
3. [Specify data retrieval settings for archived backups](restore_volume_data_retrieval.md).
4. [Specify account settings for restore](restore_volume_account.md).
5. [Choose a restore mode](restore_volume_mode.md).
6. [Enable encryption for EBS volumes](restore_volume_encryption.md).
7. [Specify the restored EBS volume name](restore_volume_name.md).
8. [Specify a restore reason](restore_volume_reason.md).
9. [Finish working with the wizard](restore_volume_finish.md).

Page updated 12/12/2025

Page content applies to build 10.0.0.232
