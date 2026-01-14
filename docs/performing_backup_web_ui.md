---
title: "performing_backup_web_ui"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/performing_backup_web_ui.html"
last_updated: "11/24/2025"
product_version: "10.0.0.232"
---


In this article

Veeam Backup for AWS runs backup policies for every data protection operation. A backup policy is a collection of settings that define the way backup operations are performed: what data to back up, where to store backups, when to start the backup process, and so on.

One backup policy can be used to process multiple resources within different regions, but you can back up each resource with one backup policy at a time. For example, if an instance is added to more than one backup policy, it will be processed only by a backup policy that has the highest priority. Other backup policies will skip this instance from processing. For information on how to set a priority for a backup policy, see [Setting Policy Priority](policies_priority.md).

In This Section

* [Performing EC2 Backup](perform_ec2_backup.md)
* [Performing RDS Backup](perform_rds_backup.md)
* [Performing DynamoDB Backup](perform_dynamo_backup.md)
* [Performing Redshift Clusters Backup](perform_redshift_backup.md)
* [Performing Redshift Serverless Backup](perform_redshift_serverless_backup.md)
* [Performing EFS Backup](perform_efs_backup.md)
* [Performing FSx Backup](perform_fsx_backup.md)
* [Performing VPC Configuration Backup](perform_vpc_backup.md)
* [Managing Backup Policies](policies_ec2_manage.md)

Page updated 11/24/2025

Page content applies to build 10.0.0.232
