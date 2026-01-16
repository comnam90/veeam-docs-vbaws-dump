---
title: "retention_archive_rds"
product: "vbaws"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/retention_archive_rds.html"
last_updated: "12/10/2025"
product_version: "10.0.0.232"
---


In this article

For archived backups of PostgreSQL DB instances, Veeam Backup for AWS retains restore points for the number of days defined in [backup scheduling settings](backup_archiving_rds.md).

To track and remove outdated restore points from an archive backup chain, Veeam Backup for AWS performs the following actions once a day:

1. Veeam Backup for AWS checks the configuration database to detect archive backup repositories that contain outdated restore points.
2. If an outdated restore point exists in a archive backup repository, Veeam Backup for AWS performs the following operations:

1. Deploys a worker instance in an AWS Region where the backup repository is located to process a retention task.

By default, Veeam Backup for AWS uses the default network settings of AWS Regions to deploy worker instances. However, you can add specific worker configurations. For more information on worker instances, see [Managing Worker Instances](workers.md).

1. Transforms the archive backup chain in the following way:

1. Veeam Backup for AWS rebuilds the full archive backup to include data of the incremental archive backup that follows the full archive backup. To do that, Veeam Backup for AWS injects into the full archive backup data blocks from the earliest incremental archive backup in the chain. This way, the full archive backup ‘moves’ forward in the archive backup chain.

[![Retention Policy for Archived Backups](images/backup_retention_injecting_blocks_archive.webp)](images/backup_retention_injecting_blocks_archive.webp "Retention Policy for Archived Backups")

1. Veeam Backup for AWS removes the earliest incremental archive backup from the chain as redundant — this data has already been injected into the full archive backup.

[![Retention Policy for Archived Backups](images/backup_retention_removing_data_archive.webp)](images/backup_retention_removing_data_archive.webp "Retention Policy for Archived Backups")

1. Veeam Backup for AWS repeats step 2 for all other outdated restore points found in the archive backup chain until all the restore points are removed. As data from multiple restore points is injected into the rebuilt full archive backup, Veeam Backup for AWS ensures that the archive backup chain is not broken and that you will be able to recover your data when needed.

[![Retention Policy for Archived Backups](images/backup_retention_multiple_points_archive.webp)](images/backup_retention_multiple_points_archive.webp "Retention Policy for Archived Backups")

1. If the worker instance was deployed, Veeam Backup for AWS removes this worker instance from Amazon EC2 when the retention session completes.

|  |
| --- |
| Note |
| * The retention task processes only one backup chain.  * Each worker instance can process only one retention task at a time.  * The number of retention tasks that Veeam Backup for AWS can handle simultaneously depends on the amount of RAM available on the backup appliance:  * If the RAM is below 8 GB, Veeam Backup for AWS will be able to handle up to 32 retention tasks at a time. * If the RAM equals 9–32 GB, Veeam Backup for AWS will be able to handle up to 64 retention tasks at a time. * If the RAM exceeds 33 GB, Veeam Backup for AWS will be able to handle up to 128 retention tasks at a time.   If the number of retention tasks exceeds the specified limit, the remaining tasks will be queued. |

Page updated 12/10/2025

Page content applies to build 10.0.0.232
