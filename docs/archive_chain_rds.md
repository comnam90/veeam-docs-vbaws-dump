---
title: "archive_chain_rds"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/archive_chain_rds.html"
last_updated: "12/5/2025"
product_version: "10.0.0.232"
---


In this article

|  |
| --- |
| Important |
| Veeam Backup for AWS does not support creating archived backups for Microsoft SQL Server DB instances. |

If you enable backup archiving for a backup policy protecting PostgreSQL DB instances, Veeam Backup for AWS creates a new backup in an archive backup repository during every archive session according to the backup policy schedule. A sequence of backups created during a set of archive sessions makes up an archive backup chain.

The archive backup chain includes backup files of the following types:

* Full — a full archive backup stores a copy of the full DB instance image.
* Incremental — incremental archive backups store incremental changes of the DB instance image.

To create an archive backup chain for a DB instance protected by a backup policy, Veeam Backup for AWS implements the forever forward incremental backup method:

1. During the first archive session, Veeam Backup for AWS detects backed-up data that is stored in the full backup and all incremental backups existing in the [standard backup chain](backup_chain_rds.md), creates a full archive backup with all the data, and copies this backup to the archive backup repository. The full archive backup becomes a starting point in the archive chain.
2. During subsequent archive sessions, Veeam Backup for AWS checks the standard backup chain to detect data blocks that have changed since the previous archive session, creates incremental archive backups with only those changed blocks, and copies these backups to the archive backup repository. The content of each incremental archive backup depends on the content of the full archive backup and the preceding incremental archive backups in the archive backup chain.

[![Archive Chain](images/archive_chain.webp)](images/archive_chain.webp "Archive Chain")

Full and incremental archive backups act as restore points for backed-up DB instances that let you roll back instance data to the necessary state. To restore databases of an PostgreSQL DB instance to a specific point in time, the chain of backups created for the instance must contain a full archive backup and a set of incremental archive backups.

If some backup in the archive backup chain is missing, you will not be able to roll back to the necessary state. For this reason, you must not delete individual files from the archive backup repository manually. Instead, you must specify retention policy settings that will let you maintain the necessary number of backups in the archive backup repository. For more information, see [Retention Policy for Archived Backups](retention_archive_rds.md).

Related Topics

[Enabling Backup Archiving](backup_archiving_rds.md)

Page updated 12/5/2025

Page content applies to build 10.0.0.232
