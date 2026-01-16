---
title: "performing_rds_database_restore"
product: "vbaws"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/performing_rds_database_restore.html"
last_updated: "12/12/2025"
product_version: "10.0.0.232"
---


In this article

In case of a disaster, you can restore corrupted databases of Microsoft SQL Server and PostgreSQL DB instances from an image-level backup. Veeam Backup for AWS allows you to restore one or more databases of only one DB instance at a time, to the original location or to a new location.

|  |
| --- |
| Important |
| Before you start the restore operation, check the limitations and prerequisites described in [Considerations and Limitations](limitations.md#rds_restore). |

How to Perform Database Restore

To restore databases of a protected DB instance, do the following:

1. [Launch the Database Restore wizard](restore_rds_database_launch.md).
2. [Select databases](restore_rds_database_point.md).
3. [Specify account settings for restore](restore_rds_database_workers.md).
4. [Specify data retrieval settings for archived backups](data_retrieval_database.md).
5. [Configure target instance settings](restore_rds_database_settings.md).
6. [Specify a restore reason](restore_rds_database_reason.md).
7. [Finish working with the wizard](restore_rds_database_finish.md).

Page updated 12/12/2025

Page content applies to build 10.0.0.232
