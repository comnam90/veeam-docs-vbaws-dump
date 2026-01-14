---
title: "perform_redshift_backup"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/perform_redshift_backup.html"
last_updated: "12/15/2025"
product_version: "10.0.0.232"
---


In this article

One backup policy can be used to process one or more Redshift clusters either within one AWS account or within an entire AWS Organization. The scope of data that you can protect in an AWS account is limited by permissions of an IAM role that is specified in the backup policy settings, whereas the scope of data that you can protect in an AWS Organization is limited by permissions of an IAM role that is specified in the organization settings.

Before you create a backup policy, consider the following:

* Check the limitations and prerequisites described in [Considerations and Limitations](limitations.md#backup_dynamo).
* If you plan to receive email notifications on backup policy results, configure email notification settings first. For more information, see [Configuring Global Notification Settings](email_settings.md).

To schedule data protection tasks to run automatically, [create backup policies](policies_create_redshift.md). For each protected Redshift cluster, you can also [take a backup manually](backup_manual_redshift.md) when needed.

Page updated 12/15/2025

Page content applies to build 10.0.0.232
