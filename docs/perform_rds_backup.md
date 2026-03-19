---
title: "Performing RDS Backup"
product: "vbaws"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/perform_rds_backup.html"
last_updated: "3/18/2026"
product_version: "10.0.0.232"
---

# Performing RDS Backup


One backup policy can be used to process one or more RDS resources either within one AWS account or within an entire AWS Organization. The scope of data that you can protect in an AWS account is limited by permissions of an IAM role that is specified in the backup policy settings, whereas the scope of data that you can protect in an AWS Organization is limited by permissions of an IAM role that is specified in the organization settings.

To schedule data protection tasks to run automatically, [create backup policies](policies_create_rds.md). For each protected DB instance and Aurora DB cluster, you can also [take a cloud-native snapshot manually](snapshot_manual_rds.md) when needed.

|  |
| --- |
| Important |
| Before you create an RDS backup policy, check the limitations and prerequisites described in section [Before You Begin](add_rds_policy_byb.md). |


