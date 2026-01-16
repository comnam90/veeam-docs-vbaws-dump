---
title: "perform_config_restore"
product: "vbaws"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/perform_config_restore.html"
last_updated: "9/15/2025"
product_version: "10.0.0.232"
---


In this article

Veeam Backup for AWS offers restore of the configuration database that can be helpful in the following situations:

* The configuration database got corrupted, and you want to recover data from a configuration backup.
* You want to roll back the configuration database to a specific point in time.
* A backup appliance got corrupted, and you want to recover its configuration from a configuration backup.
* A backup appliance went down, and you want to apply its configuration to a new backup appliance.

|  |
| --- |
| Important |
| If your backup appliance is managed by a Veeam Backup & Replication server, you will not be able to restore the configuration of Veeam Backup for AWS from the Web UI. In this case, you can perform configuration restore using the Veeam Backup & Replication console as described in section [Restoring Configuration Data Using Console](config_restore_console.md). |

In This Section

* [Restoring Configuration Data Using Console](config_restore_console.md)
* [Restoring Configuration Data Using Web UI](config_restore_web_ui.md)

Page updated 9/15/2025

Page content applies to build 10.0.0.232
