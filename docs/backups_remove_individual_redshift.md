---
title: "backups_remove_individual_redshift"
product: "vbaws"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/backups_remove_individual_redshift.html"
last_updated: "9/26/2025"
product_version: "10.0.0.232"
---


In this article

To remove all backups created for a Redshift cluster manually, follow the instructions provided in the [Removing Redshift Backups](backups_remove_redshift.md) section. If you want to remove a specific Redshift backup created manually, do the following:

1. Navigate to Protected Data > Databases > Redshift.
2. Select the necessary cluster, and click the link in the Restore Points column.
3. In the Available Restore Points window, select a backup that you want to remove, and click Remove Manual Backup.

[![Removing Redshift Backups Created Manually](images/remove_manual_points_redshift.webp)](images/remove_manual_points_redshift.webp "Removing Redshift Backups Created Manually")

Related Topics

* [Creating Redshift Backups Manually](backup_manual_redshift.md)
* [Removing Redshift Backups](backups_remove_redshift.md)

Page updated 9/26/2025

Page content applies to build 10.0.0.232
