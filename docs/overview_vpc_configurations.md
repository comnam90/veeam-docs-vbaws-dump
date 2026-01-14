---
title: "overview_vpc_configurations"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/overview_vpc_configurations.html"
last_updated: "6/7/2024"
product_version: "10.0.0.232"
---


In this article

To protect Amazon VPC configurations, Veeam Backup for AWS retrieves configuration data through API and saves this data to the configuration database. You can also instruct Veeam Backup for AWS to store copies of VPC configuration backups in a backup repository. For more information on how VPC configuration backup works, see [VPC Configuration Backup](backup_hiw_vpc.md).

How To Protect VPC Configurations

To configure the VPC configuration backup policy settings, perform the following steps:

1. [Check limitations and prerequisites](limitations.md#backup).
2. [Specify IAM role or add custom IAM roles to access AWS services and resources](accounts_iam_roles.md).
3. [Add backup repositories to save additional VPC configuration backup copies](repositories.md).
4. [[Optional] Configure global retention settings for obsolete session records](retention_settings.md#sessions).
5. [[Optional] Configure email notification settings for automated delivery of backup policy results and daily reports](email_settings.md).
6. [Complete the VPC Configuration Backup wizard](policies_edit_vpc.md).

Related Topics

* [Exporting VPC Configuration](exporting_vpc_configuration.md)
* [VPC Configuration Restore](restore_hiw_vpc.md)

Page updated 6/7/2024

Page content applies to build 10.0.0.232
