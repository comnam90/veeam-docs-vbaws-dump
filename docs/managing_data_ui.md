---
title: "managing_data_ui"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/managing_data_ui.html"
last_updated: "9/29/2025"
product_version: "10.0.0.232"
---


In this article

Veeam Backup for AWS stores information on all protected AWS resources in the configuration database. Even if a resource is no longer protected by any configured backup policy and even if the resource no longer exists in AWS, information on the backed-up data will not be deleted from the database until Veeam Backup for AWS automatically removes all restore points associated with this resource according to the retention settings saved in the backup metadata. You can also remove the restore points manually on the Protected Data page.

|  |
| --- |
| Note |
| Veeam Backup for AWS does not include restore points created manually in backup and snapshot chains, and does not apply the configured retention policy settings to these restore points. This means that the restore points are kept in your AWS environment unless you remove them manually, as described in sections [Removing EC2 Snapshots Created Manually](backups_remove_manual_snapshots.md), [Removing RDS Snapshots Created Manually](snapshots_remove_individual_rds.md), [Removing DynamoDB Backups Created Manually](backups_remove_individual_dynamo.md), [Removing Redshift Backups Created Manually](backups_remove_individual_redshift.md), [Removing Redshift Serverless Backups Created Manually](backups_remove_individual_redshift_serverless.md), [Removing EFS Backups Created Manually](backups_remove_individual_efs.md) and [Removing FSx Backups Created Manually](backups_remove_individual_fsx.md). |

In This Section

* [EC2 Data](backups_view_ec2.md)
* [RDS Data](backups_view_rds.md)
* [DynamoDB Data](backups_view_dynamo.md)
* [Redshift Clusters Data](backups_view_redshift.md)
* [Redshift Serverless Data](backups_view_redshift_serverless.md)
* [EFS Data](backups_view_efs.md)
* [FSx Data](backups_view_fsx.md)
* [VPC Configuration Data](backups_view_vpc.md)

Page updated 9/29/2025

Page content applies to build 10.0.0.232
