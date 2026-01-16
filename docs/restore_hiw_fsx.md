---
title: "restore_hiw_fsx"
product: "vbaws"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/restore_hiw_fsx.html"
last_updated: "4/24/2024"
product_version: "10.0.0.232"
---


In this article

|  |
| --- |
| Important |
| You can restore an FSx file system only to the same AWS account to which the source file system belongs. |

To restore an FSx file system from a backup, Veeam Backup for AWS performs the following steps using native AWS capabilities:

1. Creates a file system in the specified location.
2. Modifies the configuration setting values of the created FSx file system.
3. Restores backed-up files and folders to the restored file system.

To learn how to restore an Amazon FSx file system from an FSx backup or a backup copy, see [FSx Restore](fsx_restore.md).

Page updated 4/24/2024

Page content applies to build 10.0.0.232
