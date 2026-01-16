---
title: "backups_compare_vpc"
product: "vbaws"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/backups_compare_vpc.html"
last_updated: "9/26/2025"
product_version: "10.0.0.232"
---


In this article

You can compare the attributes of the current Amazon VPC configuration to the attributes of a backed-up Amazon VPC configuration. To do that:

1. Navigate to Protected Data > VPC.
2. Select the necessary configuration record.
3. Click Compare.

By default, Veeam Backup for AWS uses the most recent valid restore point. However, you can compare the VPC configuration data to an earlier state. To do that, click the Restore point link in the Compare Attributes window.

|  |
| --- |
| Tip |
| You can use the selected restore point to restore or export the VPC configuration. To do that, click either Restore or Export, and follow the instructions provided in section [Performing Entire Configuration Restore](vpc_entire_restore.md) or [Performing Entire Configuration Export](vpc_entire_export.md). |

[![Comparing VPC Configuration Backups](images/vpc_backup_compare.webp)](images/vpc_backup_compare.webp "Comparing VPC Configuration Backups")

Page updated 9/26/2025

Page content applies to build 10.0.0.232
