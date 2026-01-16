---
title: "config_restore_limitations"
product: "vbaws"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/config_restore_limitations.html"
last_updated: "8/16/2024"
product_version: "10.0.0.232"
---


In this article

Before you restore the configuration database of a backup appliance, consider the following:

* Make sure there are no sessions currently running on the backup appliance. Also, make sure there are no backup policies scheduled to run during restore. Otherwise, backups created by these policies may be corrupted.

* If the backup appliance requires an upgrade, perform it before you start configuration restore. Otherwise, Veeam Backup & Replication will not be able to perform the restore operation. To learn how to upgrade appliances, see [Updating Appliances Using Console](upgrade_appliance_console.md).

* If you remove the backup appliance from the backup infrastructure, you will not be able to restore its configuration. However, you will be able to restore the configuration to another backup appliance currently added to the backup infrastructure.
* If you want to restore the configuration to another backup appliance, you must remove the initial appliance from the backup infrastructure beforehand.

* Make sure that repositories added to the restored backup appliance are not managed by any other backup appliances. Otherwise, retention sessions running on different appliances may corrupt backup files stored in the repositories, which may result in unpredictable data loss.

* The appliance to which you restore the configuration preserves its TLS certificate.
* [Applies only if you restore the configuration to another backup appliance] During restore, Veeam Backup & Replication removes the initial appliance and its repositories from the backup infrastructure. If the restore operation fails, re-add the appliance and its repositories to the backup infrastructure.

Page updated 8/16/2024

Page content applies to build 10.0.0.232
