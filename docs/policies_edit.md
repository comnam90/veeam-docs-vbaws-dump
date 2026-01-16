---
title: "policies_edit"
product: "vbaws"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/policies_edit.html"
last_updated: "8/6/2025"
product_version: "10.0.0.232"
---


In this article

For each backup policy, you can modify settings configured while creating the policy:

1. Navigate to Policies.
2. Switch to the necessary tab and select the backup policy whose settings you want to edit.

1. Click Edit. The Edit Policy wizard will open.

1. Edit backup policy settings as described in sections [Creating EC2 Backup Policies](policies_create.md), [Creating RDS Backup Policies](policies_create_rds.md), [Creating DynamoDB Backup Policies](policies_create_dynamo.md), [Creating Redshift Clusters Backup Policies](perform_redshift_backup.md), [Creating Redshift Serverless Backup Policies](perform_redshift_serverless_backup.md), [Creating EFS Backup Policies](policies_create_efs.md) or [Creating FSx Backup Policies](policies_create_fsx.md).

|  |
| --- |
| Tip |
| To protect additional resources by a configured backup policy, you can either edit the resource list in the backup policy settings, or add resources to the backup policy on the Resources tab. To learn how to add resources on the Resources tab, see [Adding Resources to Policy](add_to_policy.md). |

[![Editing Backup Policy Settings](images/policies_edit.webp)](images/policies_edit.webp "Editing Backup Policy Settings")

Page updated 8/6/2025

Page content applies to build 10.0.0.232
