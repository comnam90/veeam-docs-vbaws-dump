---
title: "license_limitations"
product: "vbaws"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/license_limitations.html"
last_updated: "11/4/2025"
product_version: "10.0.0.232"
---


In this article

Keep in mind the following limitations and considerations:

* If you use the Veeam Cloud Connect service provider license, the Veeam Plug-In for AWS functionality is available from Veeam Service Provider Console only. For more information, see the Veeam Service Provider Console [Guide for Service Providers](https://helpcenter.veeam.com/docs/vac/provider_admin/integration_clouds.html?ver=81).
* If you have a Perpetual per-socket license installed on the backup server, and you want to add a backup appliance to the backup infrastructure, you must install an additional Perpetual per-instance license or a subscription license. When you install an additional license, the new license is automatically merged with the existing Perpetual per-socket license. For more information on the merging process, see the Veeam Backup & Replication User Guide, section [Merging Licenses](https://helpcenter.veeam.com/docs/backup/vsphere/license_merge.html?ver=120).

If you do not install an additional Perpetual per-instance license or a subscription license, you will be able to use one free license instance per each socket (maximum 6 free instances per license). After you exceed the limit of free instances, Veeam Backup for AWS backup policies protecting resources that are not covered by the license will fail.

To obtain an additional license, contact a Veeam sales representative at [Sales Inquiry](https://www.veeam.com/salesinc.html).

* If an instance has not been backed up within the past 31 days, Veeam Backup for AWS automatically revokes the license unit from the instance. If you need to manually revoke a license unit, follow the instructions provided in section [Revoking License Units](lic_revoke.md#plugin).

Page updated 11/4/2025

Page content applies to build 10.0.0.232
