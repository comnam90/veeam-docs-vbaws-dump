---
title: "perform_config_backup"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/perform_config_backup.html"
last_updated: "8/8/2024"
product_version: "10.0.0.232"
---


In this article

During configuration backup, data from configuration database of an appliance is exported and saved to a backup file in a repository. The configuration database contains the following information: existing backup policies, protected AWS resources, created worker instance configurations and profiles, added IAM roles and users, logged session records and so on.

|  |
| --- |
| Important |
| If your backup appliance is managed by a Veeam Backup & Replication server, you will neither be able to perform manual or scheduled configuration backup of Veeam Backup for AWS from the Web UI, nor to export the configuration data from the Web UI. In this case, you can perform configuration backup using the Veeam Backup & Replication console as described in section [Performing Configuration Backup Using Console](config_backup_console.md). |

In This Section

* [Performing Configuration Backup Using Console](config_backup_console.md)
* [Performing Configuration Backup Using Web UI](config_backup_ui.md)

Page updated 8/8/2024

Page content applies to build 10.0.0.232
