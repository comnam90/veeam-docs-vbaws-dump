---
title: "backup_hiw_vpc"
product: "vbaws"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/backup_hiw_vpc.html"
last_updated: "4/25/2025"
product_version: "10.0.0.232"
---


In this article

Veeam Backup for AWS performs VPC configuration backup in the following way:

1. Sends API requests to AWS to retrieve the VPC configuration data, and saves this data in the configuration database.

To back up VPC configurations of AWS Regions added to backup policies, Veeam Backup for AWS uses permissions of IAM roles specified either in the [organization settings](organization_add_settings.md) or in the backup policy settings. The VPC configuration data is collected for the selected AWS Regions in the AWS accounts or AWS Organizations to which the specified IAM roles belong.

1. Veeam Backup for AWS creates a configuration record for each pair of the AWS account and an AWS Region whose VPC configuration data is being backed up. Every time the VPC Configuration Backup policy runs, Veeam Backup for AWS updates the record to create a new restore point for the VPC configurations. For more information, see [VPC Configuration Backup Chain](backup_chain_vpc.md).

1. If you [enable additional backup copy](vpc_policy_add_copy.md) for the VPC Configuration Backup policy, Veeam Backup for AWS launches the Veeam Data Mover service on the backup appliance to copy restore points to the target backup repository, creating an individual folder for each AWS account whose VPC configuration data is protected by the policy.

Related Topics

* [Backup Chain](backup_chain_vpc.md)
* [VPC Configuration Backup Retention](retention_backup_vpc.md)

Page updated 4/25/2025

Page content applies to build 10.0.0.232
