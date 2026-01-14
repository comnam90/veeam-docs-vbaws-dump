---
title: "performing_backup_console"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/performing_backup_console.html"
last_updated: "11/11/2025"
product_version: "10.0.0.232"
---


In this article

Veeam Backup for AWS runs backup policies for every data protection operation. A backup policy is a collection of settings that define the way backup operations are performed: what data to back up, where backups must be stored, when the backup process must start, and so on.

You can create multiple backup policies for AWS resources. One backup policy can be used to process multiple resources within different regions, but you can back up each resource with one backup policy at a time. For example, if an instance is added to more than one backup policy, it will be processed only by a backup policy that has the highest priority. Other backup policies will skip this instance from processing. For information on how to set a priority for a backup policy, see [Settings Policy Priority](policies_priority.md).

After you install Veeam Plug-In for AWS and add backup appliances to the backup infrastructure, you can manage backup policies directly from the Veeam Backup & Replication console.

In This Section

* [Creating Backup Policies](add_policy.md)
* [Editing Backup Policy Settings](editing_policies_settings.md)
* [Enabling and Disabling Backup Policies](disabling_and_enabling_policies.md)
* [Starting and Stopping Backup Policies](starting_and_stopping_policies.md)
* [Deleting Backup Policies](deleting_policies.md)
* [Verifying Backups](verify_backups.md)
* [Creating Backup Copy Jobs](backup_copy.md)
* [Copying Backups to Tapes](copy_to_tape.md)

Page updated 11/11/2025

Page content applies to build 10.0.0.232
