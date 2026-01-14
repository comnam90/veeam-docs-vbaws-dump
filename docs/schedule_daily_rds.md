---
title: "schedule_daily_rds"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/schedule_daily_rds.html"
last_updated: "7/25/2025"
product_version: "10.0.0.232"
---


In this article

To create a daily schedule for the backup policy, at the Schedule step of the wizard, do the following:

1. Set the Daily schedule toggle to On and click Edit Daily Settings.
2. In the Create daily schedule section, select hours when the backup policy will create cloud-native snapshots, snapshot replicas or image-level backups.

If you want to protect RDS resources data more frequently, you can instruct the backup policy to create multiple cloud-native snapshots per hour. To do that, click the link to the right of the Snapshots hour selection area, and specify the number of cloud-native snapshots that the backup policy will create within an hour.

|  |
| --- |
| Note |
| Veeam Backup for AWS does not create snapshot replicas and image-level backups independently from cloud-native snapshots. That is why when you select hours to create snapshot replicas and image-level backups, the same hours are automatically selected for cloud-native snapshots. To learn how Veeam Backup for AWS performs backup, see [RDS Backup](backup_hiw_rds.md). |

1. Use the Run at drop-down list to choose whether you want the backup policy to run everyday, on work days (Monday through Friday) or on specific days.
2. In the Daily retention section, configure retention policy settings for the daily schedule:

* For cloud-native snapshots and snapshot replicas, specify the number of restore points that you want to keep in cloud-native snapshot and snapshot replica chains.

If the restore point limit is exceeded, Veeam Backup for AWS removes the earliest restore point from the chain. For more information, see [RDS Snapshot Retention](retention_snapshots_rds.md).

* For image-level backups, specify the number of days (or months) for which you want to keep restore points in a backup chain.

If a restore point is older than the specified time limit, Veeam Backup for AWS removes the restore point from the chain. For more information, see [RDS Backup Retention](retention_backup_rds.md).

1. To save changes made to the backup policy settings, click Apply.

|  |
| --- |
| Tip |
| Veeam Backup for AWS will start applying the configured retention settings as soon as the backup policy produces restore points. Even if you disable the daily schedule after the restore points are created, the retention policy will still be applied to these restore points. As a workaround, you can modify the configured retention settings. |

[![Creating RDS Backup Policy](images/rds_backup_daily_schedule.webp)](images/rds_backup_daily_schedule.webp "Creating RDS Backup Policy")

Page updated 7/25/2025

Page content applies to build 10.0.0.232
