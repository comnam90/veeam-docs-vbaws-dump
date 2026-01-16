---
title: "restore_to_google"
product: "vbaws"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/restore_to_google.html"
last_updated: "8/8/2025"
product_version: "10.0.0.232"
---


In this article

Veeam Backup & Replication allows you to restore Amazon EC2 instances from image-level backups created with Veeam Backup for AWS to Google Cloud as VM instances. You can restore EC2 instances to any available restore point. For more information, see the Veeam Backup & Replication User Guide, section [Restore to Google Compute Engine](https://helpcenter.veeam.com/docs/vbr/userguide/restore_google.html?ver=13).

|  |
| --- |
| Important |
| * Restore to Google Cloud can be performed only using backup files stored in standard backup repositories for which you have specified access keys of an IAM user whose permissions are used to access the repositories. To learn how to specify credentials for the repositories, see sections [Creating New Repositories](add_s3_account.md) and [Connecting to Existing Appliances](connect_appliance_repo.md).  * Before you start the restore operation, check the limitations and prerequisites described in the Veeam Backup & Replication User Guide, section [Before You Begin](https://helpcenter.veeam.com/docs/vbr/userguide/restore_google_byb.html?ver=13). |

To restore an EC2 instance to Google Cloud, do the following:

1. In the Veeam Backup & Replication console, open the Home view.
2. Navigate to Backups > External Repository.
3. Expand the backup policy that protects an EC2 instance that you want to restore, select the necessary instance and click Google CE on the ribbon.
4. Complete the Restore to Google Compute Engine wizard as described in the Veeam Backup & Replication User Guide, section [Restoring to Google Compute Engine](https://helpcenter.veeam.com/docs/vbr/userguide/restore_google_virtual_machines.html?ver=13).

[![Restore to Google Cloud Platform](images/restore_to_google.webp)](images/restore_to_google.webp "Restore to Google Cloud Platform")

Page updated 8/8/2025

Page content applies to build 10.0.0.232
