---
title: "restore_hiw_vpc_entire"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/restore_hiw_vpc_entire.html"
last_updated: "11/10/2023"
product_version: "10.0.0.232"
---


In this article

To restore the entire VPC configuration from a backup, Veeam Backup for AWS performs the following steps:

1. Retrieves the backed-up VPC configuration from the Veeam Backup for AWS database.
2. Validates the restore operation: sends API requests to AWS to verify that AWS service quotas are not exceeded and there are no subnet CIDR block conflicts.
3. Retrieves information on existing items and their settings in the current Amazon VPC configuration.
4. Restores the backed-up VPC configuration:

1. Creates the missing VPC configuration items.
2. Modifies settings of the existing items that do not match the backed-up settings.

To learn how to restore an entire VPC configuration from a VPC configuration backup, see [Performing Entire Configuration Restore](vpc_entire_restore.md).

Page updated 11/10/2023

Page content applies to build 10.0.0.232
