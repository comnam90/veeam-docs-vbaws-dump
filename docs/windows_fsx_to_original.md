---
title: "windows_fsx_to_original"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/windows_fsx_to_original.html"
last_updated: "11/19/2025"
product_version: "10.0.0.232"
---


In this article

[This step applies only if you have selected the Restore to original location option at the Restore Mode step of the wizard, and if the selected file system is an Amazon FSx for Windows File Server file system joined to a self-managed Microsoft Active Directory (AD)]

At the Settings step of the wizard, check Active Directory settings that will be used to authenticate against the Microsoft AD to which the restored file system will be connected, and provide the password of the service account.To do that, select the file system and click Edit.

|  |
| --- |
| Note |
| Veeam Backup for AWS does not store client secrets in the configuration database. |

For more information on Microsoft Active Directory in FSx for Windows File Server, see [AWS Documentation](https://docs.aws.amazon.com/fsx/latest/WindowsGuide/aws-ad-integration-fsxW.html).

[![Restoring FSx File Systems](images/restore_general_settings_ad_fsx.webp)](images/restore_general_settings_ad_fsx.webp "Restoring FSx File Systems")

Page updated 11/19/2025

Page content applies to build 10.0.0.232
