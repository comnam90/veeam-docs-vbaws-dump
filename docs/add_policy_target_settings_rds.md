---
title: "add_policy_target_settings_rds"
product: "vbaws"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/add_policy_target_settings_rds.html"
last_updated: "10/3/2025"
product_version: "10.0.0.232"
---


In this article

By default, backup policies create only cloud-native snapshots of processed instances. At the Targets step of the wizard, you can enable the following additional data protection scenarios:

* [Instruct Veeam Backup for AWS to replicate cloud-native snapshots to other AWS accounts or AWS Regions](add_policy_target_settings_rds_replica.md).
* [Instruct Veeam Backup for AWS to create image-level backups](add_policy_target_settings_backups_rds.md).

|  |
| --- |
| Important |
| Creating image-level backups is supported for Microsoft SQL Server and PostgreSQL DB instances only. For the list of supported PostgreSQL versions, see [Protecting RDS Resources](overview_rds.md#applications). |

Page updated 10/3/2025

Page content applies to build 10.0.0.232
