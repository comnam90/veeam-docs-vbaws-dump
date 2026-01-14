---
title: "perform_ec2_backup"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/perform_ec2_backup.html"
last_updated: "12/15/2025"
product_version: "10.0.0.232"
---


In this article

One backup policy can be used to process one or more instances either within one AWS account or within an entire AWS Organization. The scope of data that you can protect in an AWS account is limited by permissions of an IAM role that is specified in the backup policy settings, whereas the scope of data that you can protect in an AWS Organization is limited by permissions of an IAM role that is specified in the organization settings.

Before you create a backup policy, consider the following:

* Check the limitations and prerequisites described in [Considerations and Limitations](limitations.md#backup_ec2).
* If you plan to create image-level backups of EC2 instances, backup infrastructure components that will take part in the backup process must be added to the backup infrastructure and configured properly. These include [backup repositories](repositories_add_ui.md) and [worker instances](workers.md).
* If plan to create SLA-based backup policies, configure policy templates first. For more information, see [Managing SLA and Storage Templates](sla_storage_manage.md).
* If you plan to receive email notifications on backup policy results, configure email notification settings first. For more information, see [Configuring Global Notification Settings](email_settings.md).
* If you plan to create transactionally consistent backups of EC2 instances, check the requirements for application-aware processing and guest scripting. For more information, see sections [Creating Schedule-Based EC2 Backup Policies](add_policy_guest_processing.md) and [Creating SLA-Based EC2 Backup Policies](add_sla_policy_guest_processing.md).

To schedule data protection tasks to run automatically, create backup policies. For each protected EC2 instance, you can also [take cloud-native snapshots manually](snapshot_manual.md) when needed.

Related Topics

[SLA-Based Backup Policies](overview_ec2.md#policies)

Page updated 12/15/2025

Page content applies to build 10.0.0.232
