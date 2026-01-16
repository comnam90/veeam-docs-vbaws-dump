---
title: "permissions_changelog"
product: "vbaws"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/permissions_changelog.html"
last_updated: "11/18/2025"
product_version: "10.0.0.232"
---


In this article

This section describes the latest changes in IAM permissions required for Veeam Backup for AWS to perform operations.

When you update Veeam Backup for AWS version 9.1 to version 10, consider that an additional permission must be granted to the existing IAM roles — for Veeam Backup for AWS to be able to restore Oracle DB instances with multi-tenant architecture, the IAM roles specified in the [organization settings](organization_add_settings.md) or in the [restore settings](restore_rds_account.md) must be granted the "rds:DeleteTenantDatabase" permission.

|  |
| --- |
| Important |
| Veeam Backup for AWS version 10 comes with the ability to create image-level backups of Microsoft SQL Server DB instances and keep them in Amazon Simple Storage Service (Amazon S3). For the list of permissions required to perform backup and restore operations with Microsoft SQL Server DB instances, see sections [RDS Backup IAM Role Permissions](role_permissions_backup_rds.md#worker) and [RDS Database Restore IAM Permissions](role_permissions_restore_db.md). |

Page updated 11/18/2025

Page content applies to build 10.0.0.232
