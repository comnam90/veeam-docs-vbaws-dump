---
title: "Performing Redshift Clusters Backup"
product: "vbaws"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/perform_redshift_backup.html"
last_updated: "3/18/2026"
product_version: "10.0.0.232"
---

# Performing Redshift Clusters Backup


One backup policy can be used to process one or more Redshift clusters either within one AWS account or within an entire AWS Organization. The scope of data that you can protect in an AWS account is limited by permissions of an IAM role that is specified in the backup policy settings, whereas the scope of data that you can protect in an AWS Organization is limited by permissions of an IAM role that is specified in the organization settings.

To schedule data protection tasks to run automatically, [create backup policies](policies_create_redshift.md). For each protected Redshift cluster, you can also [take a backup manually](backup_manual_redshift.md) when needed.

|  |
| --- |
| Important |
| Before you create a Redshift backup policy, check the limitations and prerequisites described in section [Before You Begin](add_redshift_cluster_policy_byb.md). |


