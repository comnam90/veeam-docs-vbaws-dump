---
title: "retention_backup"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/retention_backup.html"
last_updated: "12/10/2025"
product_version: "10.0.0.232"
---


In this article

For image-level backups, Veeam Backup for AWS retains restore points for the number of days defined in backup scheduling settings as described in sections [Creating EC2 Backup Policies](add_policy_schedule_retention.md) and [Adding SLA Templates](sla_add.md).

To track and remove outdated restore points from a backup chain, Veeam Backup for AWS performs the following actions once a day:

1. Veeam Backup for AWS checks the configuration database to detect backup repositories that contain outdated restore points.
2. If an outdated restore point exists in a backup repository, Veeam Backup for AWS performs the following operations:

1. Deploys a worker instance in the backup account in an AWS Region where the backup repository is located to process a retention task.

By default, Veeam Backup for AWS uses the default network settings of AWS Regions to deploy worker instances. However, you can add specific worker configurations. For more information on worker instances, see [Managing Worker Instances](workers.md).

1. Transforms the backup chain in the following way:

1. Veeam Backup for AWS rebuilds the full backup to include data of the incremental backup that follows the full backup. To do that, Veeam Backup for AWS injects into the full backup data blocks from the earliest incremental backup in the chain. This way, a full backup ‘moves’ forward in the backup chain.

[![EC2 Backup Retention](images/backup_retention_injecting_blocks.webp)](images/backup_retention_injecting_blocks.webp "EC2 Backup Retention")

1. Veeam Backup for AWS removes the earliest incremental backup from the chain as redundant — this data has already been injected into the full backup.

[![EC2 Backup Retention](images/backup_retention_removing_data.webp)](images/backup_retention_removing_data.webp "EC2 Backup Retention")

1. Veeam Backup for AWS repeats step 2 for all other outdated restore points found in the backup chain until all the restore points are removed. As data from multiple restore points is injected into the rebuilt full backup, Veeam Backup for AWS ensures that the backup chain is not broken and that you will be able to recover your data when needed.

[![EC2 Backup Retention](images/backup_retention_multiple_points.webp)](images/backup_retention_multiple_points.webp "EC2 Backup Retention")

1. Veeam Backup for AWS removes this worker instance from Amazon EC2 when the retention session completes.

|  |
| --- |
| NoteS |
| * Veeam Backup for AWS runs retention sessions for backup policies at 4:00 AM by default. * Each retention task can process only one backup chain.  * Each worker instance can process only one retention task at a time.  * The number of retention tasks that Veeam Backup for AWS can handle simultaneously depends on the amount of RAM available on the backup appliance:  * If the RAM is below 8 GB, Veeam Backup for AWS will be able to handle up to 32 retention tasks at a time. * If the RAM equals 9–32 GB, Veeam Backup for AWS will be able to handle up to 64 retention tasks at a time. * If the RAM exceeds 33 GB, Veeam Backup for AWS will be able to handle up to 128 retention tasks at a time.   If the number of retention tasks exceeds the specified limit, the remaining tasks will be queued. |

Related Topics

* [CBT Impact on Snapshot Retention](cbt_retention.md)
* [Retention Policy for Archived Backups](retention_archive.md)

Page updated 12/10/2025

Page content applies to build 10.0.0.232
