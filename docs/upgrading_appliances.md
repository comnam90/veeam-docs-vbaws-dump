---
title: "upgrading_appliances"
product: "vbaws"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/upgrading_appliances.html"
last_updated: "11/6/2025"
product_version: "10.0.0.232"
---


In this article

Upgrade to Veeam Backup for AWS version 10 is supported from Veeam Backup for AWS version 4.0 or later. To upgrade from an earlier version, you must first perform upgrade to version 4 as described in section [Installing Updates](updates_install.md).

|  |
| --- |
| Important |
| Before you upgrade a backup appliance, make sure that all backup policies are both disabled and stopped, and no restore tasks are currently executing. Otherwise, the upgrade process will interrupt the running activities, which may result in data loss. |

To upgrade a backup appliance, do the following:

1. Install Veeam Plug-In for AWS as described in section [Deployment](deployment.md).

If you do not have a valid Veeam Backup & Replication license, you can download a [30-day trial version](https://www.veeam.com/backup-replication-vcp-download.html) of the product.

1. Add the backup appliance to the Veeam Backup & Replication infrastructure as described in section [Connecting to Existing Appliances](connect_appliance.md).

When connecting to the backup appliance, Veeam Backup & Replication will display a warning notifying you that the appliance must be upgraded. Acknowledge the warning to allow Veeam Backup & Replication to automatically upgrade the appliance to the necessary version.

|  |
| --- |
| Note |
| When you add a backup appliance to the Veeam Backup & Replication infrastructure, the license installed on the appliance is replaced with the license installed on the backup server. Protected instances start consuming license units from the license installed on the Veeam Backup & Replication server. However, as soon as you remove the backup appliance from the Veeam Backup & Replication infrastructure, Veeam Backup for AWS will continue using the license that had been used before you added the Veeam Backup for AWS appliance to the Veeam Backup & Replication infrastructure.  For more information on licensing scenarios, see [Licensing](license_scenarios.md). |

1. [Applies only if the backup appliance has not been upgraded at step 2] Upgrade the backup appliance as described in the section [Updating Appliances Using Web UI](upgrade_appliance_ui.md).
2. After the upgrade process completes, you can remove the backup appliance from the Veeam Backup & Replication infrastructure, as described in section [Removing Appliances](remove_appliance.md), if you do not plan to further manage this appliance from the Veeam Backup & Replication console.

If you remove the backup appliance from the backup infrastructure, you will no longer be able to create image-level backups of Microsoft SQL Server and PostgreSQL DB instances, as well as protect Redshift clusters, Redshift Serverless namespaces, DynamoDB tables and FSx file systems. For more information, see [Integration with Veeam Backup & Replication](integration_vbr.md).

|  |
| --- |
| Note |
| When you upgrade to Veeam Backup for AWS version 10 from Veeam Backup for AWS version 6 or earlier, the backup appliance operating system is upgraded to Ubuntu 22.04 LTS and the configuration database is upgraded to PostgreSQL 15. For more information on the upgrade process, see [Upgrading to Version 10 from Version 6.0 or Earlier](upgrade_vb_console.md). |

Page updated 11/6/2025

Page content applies to build 10.0.0.232
