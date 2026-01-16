---
title: "add_policy"
product: "vbaws"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/add_policy.html"
last_updated: "11/4/2025"
product_version: "10.0.0.232"
---


In this article

You can create backup policies in the Veeam Backup for AWS Web UI only. However, you can launch the Add Policy wizard directly from the Veeam Backup & Replication console — to do that, use either of the following options:

* Switch to the Home tab, click Backup Job on the ribbon, navigate to AWS > EC2, RDS, EFS, DynamoDB, Redshift, Reshift Serverless or FSx and select the backup appliance on which you want to create the backup policy.
* Open the Home view, right-click Jobs, navigate to Backup > AWS > EC2, RDS, EFS, DynamoDB, Redshift, Reshift Serverless or FSx and select the backup appliance on which you want to create the backup policy.

Veeam Backup & Replication will open the Add EC2 Policy, Add RDS Policy, Add EFS Policy, Add DynamoDB Policy, Add Redshift Policy, Add Reshift Serverless Policy or Add FSx Policy wizard in a web browser. Complete the wizard as described in section [Creating EC2 Backup Policies](add_policy_name.md), [Creating RDS Backup Policies](add_policy_name_rds.md), [Creating EFS Backup Policies](add_policy_name_efs.md), [Creating DynamoDB Backup Policies](policies_create_dynamo.md), [Creating Redshift Cluster Backup Policies](policies_create_redshift.md), [Creating Redshift Serverless Backup Policies](policies_create_redshift_serverless.md) or [Creating FSx Backup Policies](policies_create_fsx.md).

|  |
| --- |
| Note |
| Backup appliance comes with a preconfigured VPC Configuration Backup policy that is disabled by default. To start protecting your Amazon VPC configuration, you must edit the VPC Configuration Backup policy settings and enable the policy. For more information, see [Editing VPC Configuration Backup Policy](policies_edit_vpc.md). |

[![Add backup policy](images/backup_policy_add.webp)](images/backup_policy_add.webp "Add backup policy")

Page updated 11/4/2025

Page content applies to build 10.0.0.232
