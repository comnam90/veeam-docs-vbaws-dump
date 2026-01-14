---
title: "config_backup_console"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/config_backup_console.html"
last_updated: "8/22/2025"
product_version: "10.0.0.232"
---


In this article

While performing configuration backup, Veeam Backup & Replication backs up the configuration of the backup server and also configurations of all backup appliances added to the backup infrastructure. The results of every configuration backup session are displayed in the History view under the System node.

You can perform configuration backup manually or instruct Veeam Backup & Replication to do it automatically on a regular basis:

* To perform configuration backup manually, follow the instructions provided in the Veeam Backup & Replication User Guide, section [Running Configuration Backups Manually](https://helpcenter.veeam.com/docs/vbr/userguide/vbr_config_manually.html?ver=13).
* To instruct Veeam Backup & Replication to perform configuration backup automatically, follow the instructions provided in the Veeam Backup & Replication User Guide, section [Scheduling Configuration Backups](https://helpcenter.veeam.com/docs/vbr/userguide/vbr_config_schedule.html?ver=13).

Before You Begin

If you plan to back up the configuration of a managed backup appliance, keep in mind the following limitations and considerations:

* You must enable backup file encryption in the configuration backup settings. Otherwise, Veeam Backup & Replication will not be able to back up the backup appliance configuration.

To learn how to create encrypted configuration backup, see the Veeam Backup & Replication User Guide, section [Creating Encrypted Configuration Backups](https://helpcenter.veeam.com/docs/vbr/userguide/config_backup_encrypted.html?ver=13).

* You must log in to the Host Management Console using the credentials of a user account with the Security Officer role and specify a passphrase for this account. Otherwise, Veeam Backup & Replication will not be able to back up the backup appliance configuration.

To learn how to specify passphrases for user accounts with the Security Officer role, see the Veeam Backup & Replication User Guide, section [Performing Initial Security Login](https://helpcenter.veeam.com/docs/vbr/userguide/hmc_users_security_officer.html?ver=13).

* You cannot store configuration backups in scale-out backup repositories and external repositories.
* For Veeam Backup & Replication to be able to back up the appliance configuration, the backup appliance must be available and must run a Veeam Backup for AWS version that is compatible with the Veeam Plug-In for AWS version.

For the list of compatible versions, see [System Requirements](system_requirements.md#versions).

* During configuration backup, Veeam Backup & Replication processes only 3 appliances at a time — the appliances exceeding this limit are queued.

* To enable data loss protection in case you lose or forget the password used for data encryption, you can use Veeam Backup Enterprise Manager to decrypt backup files.

To learn how to let Veeam Backup & Replication encrypt and decrypt data with Enterprise Manager, see the Veeam Backup Enterprise Manager Guide, section [Managing Encryption Keys](https://helpcenter.veeam.com/docs/backup/em/em_manage_keys.html?ver=120).

Configuration Backup Location

Veeam Backup & Replication stores configuration backups of backup appliances in a repository specified in configuration backup settings. Backups are saved in the \VeeamConfigBackup\AWS folder.

|  |
| --- |
| Notes |
| * It is not recommended to store configuration backups on the backup server. Otherwise, you will not be able to restore configuration of managed backup appliances in case the backup server goes down.  * If the name of an appliance contains unsupported characters, these characters are replaced with the '\_' underscore symbol in the name format for a subfolder and a backup files. |

Page updated 8/22/2025

Page content applies to build 10.0.0.232
