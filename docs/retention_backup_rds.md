---
title: "RDS Backup Retention"
product: "vbaws"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/retention_backup_rds.html"
last_updated: "11/23/2023"
product_version: "10.0.0.232"
---

# RDS Backup Retention


The forever forward incremental backup method is not implemented for DB instances — during every backup session Veeam Backup for AWS creates a full backup in the regular backup chain. If Veeam Backup for AWS detects an outdated restore point in a backup repository, it removes this restore point from the backup chain.


