---
title: "license_scenarios"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/license_scenarios.html"
last_updated: "8/8/2025"
product_version: "10.0.0.232"
---


In this article

Backup appliances managed by a Veeam Backup & Replication server use the same license that is installed on the backup server. To learn what types of licenses and licensing models are incorporated in Veeam solutions, see:

* The Veeam Backup & Replication User Guide, section [Licensing](https://helpcenter.veeam.com/docs/vbr/userguide/licensing.html?ver=13)
* The Veeam Backup & Replication Veeam Cloud Connect Guide, section [Licensing for Service Providers](https://helpcenter.veeam.com/docs/backup/cloud/cloud_connect_hosting_licenses.html?ver=120)

Licensing of New Backup Appliances

When you [deploy a new backup appliance](deploying_appliances.md) from the Veeam Backup & Replication console, workloads start consuming license units from the license installed on the backup server after you create and run backup policies. After you remove the backup appliance from the backup infrastructure, Veeam Backup & Replication stops counting backed-up workloads and Veeam Backup for AWS switches to the Free edition that allows you to protect up to 10 workloads free of charge.

|  |
| --- |
| Note |
| When you [connect to an existing backup appliance](connect_appliance.md) to a Veeam Backup & Replication server, the license installed on the appliance is replaced with the license installed on the backup server. However, protected instances start consuming license units from the license installed on the backup server only after backup policy sessions run on the connected appliance. After you remove the backup appliance from the backup infrastructure, Veeam Backup & Replication stops counting backed-up workloads and Veeam Backup for AWS continues using the license that was used before you added the backup appliance to the backup infrastructure. |

Licensing When Connection to Veeam Backup & Replication is Lost

Veeam Backup for AWS stores information on protected workloads licensed by Veeam Backup & Replication. This information allows you to back up workloads even if the connection between the backup appliance and backup server is lost. However, the following conditions must be met:

* The workload must have already been licensed by the backup server.
* The workload must be listed as licensed on the backup appliance side. For more information, see [Revoking License Units](lic_revoke.md#web_ui).
* The connection must be lost not more than 31 days ago.

Note that the loss of connection with Veeam Backup & Replication does not affect restore processes and creating of snapshots manually.

Page updated 8/8/2025

Page content applies to build 10.0.0.232
