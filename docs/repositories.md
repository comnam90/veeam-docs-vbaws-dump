---
title: "repositories"
product: "vbaws"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/repositories.html"
last_updated: "7/31/2025"
product_version: "10.0.0.232"
---


In this article

Veeam Backup for AWS uses Amazon S3 buckets as target locations for EC2 and RDS image-level backups, additional copies of Amazon VPC backups, indexes of EFS file systems and Veeam Backup for AWS configuration backups. To store backups in Amazon S3 buckets, configure backup repositories. A repository is a specific folder created by Veeam Backup for AWS in an Amazon S3 bucket.

|  |
| --- |
| Important |
| A backup repository must not be managed by multiple backup appliances simultaneously. Retention sessions running on different backup appliances may corrupt backups stored in the repository, which may result in unpredictable data loss. |

In This Section

* [Adding Backup Repositories Using Console](repositories_add_console.md)
* [Adding Backup Repositories Using Web UI](repositories_add_ui.md)
* [Editing Backup Repository Settings](repositories_edit.md)
* [Rescanning Backup Repositories](rescan_repositories.md)
* [Removing Backup Repositories](repositories_remove.md)

Page updated 7/31/2025

Page content applies to build 10.0.0.232
