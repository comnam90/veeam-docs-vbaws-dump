---
title: "snapshots_remove_individual_rds"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/snapshots_remove_individual_rds.html"
last_updated: "9/26/2025"
product_version: "10.0.0.232"
---


In this article

To remove all cloud-native snapshots created for a DB instance or an Aurora DB cluster manually, follow the instructions provided in the [Removing RDS Backups and Snapshots](snapshots_remove_rds.md) section. If you want to remove a specific snapshot created manually, do the following:

1. Navigate to Protected Data > Databases > RDS.
2. Select the necessary resource, and click the link in the Restore Points column.
3. In the Available Restore Points window, select a snapshot that you want to remove, and click Remove Manual Snapshot.

[![Removing RDS Snapshots Created Manually](images/remove_manual_points_rds.webp)](images/remove_manual_points_rds.webp "Removing RDS Snapshots Created Manually")

Related Topics

* [Creating Snapshots Manually](snapshot_manual_rds.md)
* [Removing RDS Backups and Snapshots](snapshots_remove_rds.md)

Page updated 9/26/2025

Page content applies to build 10.0.0.232
