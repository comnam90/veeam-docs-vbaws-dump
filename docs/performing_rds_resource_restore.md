---
title: "performing_rds_resource_restore"
product: "vbaws"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/performing_rds_resource_restore.html"
last_updated: "12/12/2025"
product_version: "10.0.0.232"
---


In this article

In case of a disaster, you can restore a DB instance or an Aurora DB cluster from a cloud-native snapshot or snapshot replica. Veeam Backup for AWS allows you to restore one or more RDS resources at a time, to the original location or to a new location.

|  |
| --- |
| Important |
| Before you start the restore operation, check the limitations and prerequisites described in [Considerations and Limitations](limitations.md#rds_restore). |

How to Perform RDS Restore

To restore a protected RDS resource, do the following:

1. [Launch the RDS Restore wizard](restore_rds_launch.md).
2. [Select a restore point](restore_rds_point.md).
3. [Specify account settings for restore](restore_rds_account.md).
4. [Choose a restore mode](restore_rds_mode.md).
5. [Enable encryption](restore_rds_encryption.md).
6. [Configure RDS instance settings](restore_rds_settings.md).
7. [Configure network settings](restore_rds_network.md).
8. [Specify a restore reason](restore_rds_reason.md).
9. [Finish working with the wizard](restore_rds_finish.md).

Page updated 12/12/2025

Page content applies to build 10.0.0.232
