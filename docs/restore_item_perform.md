---
title: "restore_item_perform"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/restore_item_perform.html"
last_updated: "12/15/2025"
product_version: "10.0.0.232"
---


In this article

In case a disaster strikes, you can recover corrupted or missing files of an EC2 instance from a cloud-native snapshot or image-level backup.

You can use the following options:

* Download the necessary files and folders to a local machine.
* Restore the files and folders of the source EC2 instance to the original location.

By default, Veeam Backup for AWS restores files and folders to a local machine. If you want to perform restore to the original location, you must enable the [Additional restore mode](restore_item_mode.md) in the restore settings.

To learn how EC2 file-level recovery works, see [File-Level Recovery](restore_hiw_file_level.md). To learn how to configure network settings that will be used to deploy workers during the restore process, see [Managing Worker Configurations](worker_settings.md).

|  |
| --- |
| Important |
| Before you start the restore operation, consider the limitations and prerequisites described in section [Before You Begin](restore_item_before_you_begin.md). |

How to Perform EC2 File-Level Recovery

To recover files and folders of a protected EC2 instance, do the following:

1. [Launch the EC2 File-level Recovery wizard](restore_item_launch.md).
2. [Select a restore point](restore_item_settings.md).
3. [Specify restore settings](restore_item_mode.md).
4. [Specify a restore reason](restore_item_reason.md).
5. [Finish working with the wizard — start a recovery session](restore_item_finish.md).
6. [Choose files and folders to recover](restore_item_save.md).
7. [Stop the recovery session](restore_item_stop.md).

Page updated 12/15/2025

Page content applies to build 10.0.0.232
