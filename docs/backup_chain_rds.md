---
title: "backup_chain_rds"
product: "vbaws"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/backup_chain_rds.html"
last_updated: "10/8/2025"
product_version: "10.0.0.232"
---


In this article

The forever forward incremental backup method is not implemented for DB instances — during every backup session Veeam Backup for AWS creates a full backup in the regular backup chain.

Each RDS backup in the backup chain contains encrypted metadata that stores information about the protected DB instance, the backup policy that created the backup, as well as the date, time and configured retention settings. Veeam Backup for AWS uses metadata to identify outdated backups, to retrieve information on the source instance configuration during recovery operations, and so on.

RDS backups act as independent restore points for backed-up DB instances. If you remove any backup, it will not break the backup chain — you will still be able to roll back data to any existing restore point.

The period of time during which RDS backups are kept in the backup chain is defined by retention policy settings. For more information, see [RDS Backup Retention](retention_backup_rds.md).

Related Topics

* [Archive Backup Chain](archive_chain_rds.md)
* [RDS Backup Retention](retention_backup_rds.md)

Page updated 10/8/2025

Page content applies to build 10.0.0.232
