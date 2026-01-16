---
title: "fsx_restore_ui"
product: "vbaws"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/fsx_restore_ui.html"
last_updated: "12/12/2025"
product_version: "10.0.0.232"
---


In this article

In case of a disaster, you can restore a FSx file system from a FSx backup or backup copy. Veeam Backup for AWS allows you to restore one or more file systems at a time, to the original location or to a new location. To learn how FSx restore works, see [FSx Restore](restore_hiw_fsx.md).

|  |
| --- |
| Important |
| * Veeam Backup for AWS supports restoring FSx file systems only to the same AWS accounts to which the source file systems belong.  * Veeam Backup for AWS supports restoring only those FSx file system properties that are described in section [Protecting FSx File Systems](overview_fsx.md#parameters).  * Veeam Backup for AWS supports restoring Amazon FSx for Windows File Server file systems. However, before you start a restore operation, it is recommended that you use the Amazon FSx Active Directory Validation tool to check the connection between the file systems that you plan to restore and the Microsoft Active Directories to which these file systems will be joined. To learn how to use the validation tool, see [AWS Documentation](https://docs.aws.amazon.com/fsx/latest/WindowsGuide/aws-ad-integration-fsxW.html). * Veeam Backup for AWS does not support restoring Amazon FSx for Windows File Server file systems that use AWS Secrets Manager to store service account credentials when joined to a self-managed Microsoft Active Directory (AD). |

How to Perform File System Restore

To restore a protected FSx file system, do the following:

1. [Launch the FSx Restore wizard](restore_launch_fsx.md).
2. [Select a restore point](restore_point_fsx.md).
3. [Specify account settings for restore](restore_account_fsx.md).
4. [Choose a restore mode](restore_mode_fsx.md).
5. [Enable encryption for the restored table](restore_encryption_fsx.md).
6. [Configure General Settings](restore_general_fsx.md).
7. [Configure network settings](restore_capacity_network_efs.md).
8. [Specify a restore reason](restore_reason_fsx.md).
9. [Finish working with the wizard](restore_finish_fsx.md).

Page updated 12/12/2025

Page content applies to build 10.0.0.232
