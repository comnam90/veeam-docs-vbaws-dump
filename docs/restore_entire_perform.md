---
title: "restore_entire_perform"
product: "vbaws"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/restore_entire_perform.html"
last_updated: "12/15/2025"
product_version: "10.0.0.232"
---


In this article

In case of a disaster, you can restore an entire EC2 instance from a cloud-native snapshot, snapshot replica or image-level backup. Veeam Backup for AWS allows you to restore one or more EC2 instances at a time, to the original location or to a new location.

|  |
| --- |
| Important |
| Before you start the restore operation, check the limitations and prerequisites described in section [Before You Begin](restore_entire_before_you_begin.md). |

How to Perform Instance Restore

To restore a protected EC2 instance, do the following:

1. [Launch the Instance Restore wizard](restore_entire_launch.md).
2. [Select a restore point](restore_entire_settings.md).
3. [Specify data retrieval settings for archived backups](restore_entire_data_retrieval.md).
4. [Specify account settings for restore](restore_entire_account.md).
5. [Choose a restore mode](restore_entire_mode.md).
6. [Enable encryption for EBS volumes](restore_entire_encryption.md).
7. [Specify EC2 instance settings](restore_entire_type.md).
8. [Configure network settings](restore_entire_network.md).
9. [Specify a restore reason](restore_entire_reason.md).
10. [Finish working with the wizard](restore_entire_finish.md).

Page updated 12/15/2025

Page content applies to build 10.0.0.232
