---
title: "upgrade_vb_console"
product: "vbaws"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/upgrade_vb_console.html"
last_updated: "11/3/2025"
product_version: "10.0.0.232"
---


In this article

To upgrade Veeam Backup for AWS to version 10, a backup appliance must be running version 4.0 or later. To upgrade the appliance, check the [prerequisites](#Prerequisites) and follow the instructions provided in section [Updating Appliances Using Console](upgrade_appliance_console.md).

When you perform upgrade to version 10 from Veeam Backup for AWS version 6.0 or earlier, the backup appliance operating system is upgraded from Ubuntu 18.04 LTS to Ubuntu 22.04 LTS, and the configuration database is upgraded to PostgreSQL 15. Consider that during upgrade the original root volume of the backup appliance will be replaced with a new one.

How Upgrade to Version 10 Works

When upgrading backup appliances to version 10 from Veeam Backup for AWS version 6.0 or earlier, Veeam Backup & Replication performs the following steps:

1. Instructs Veeam Backup for AWS to create a cloud-native snapshot of the original appliance. If the upgrade process fails, the appliance will be reverted to the created snapshot.

Consider that this snapshot will be automatically removed by Veeam Backup & Replication from AWS after the upgrade operation completes successfully.

1. Upgrades the appliance configuration database to PostgreSQL 15: creates a new PostgreSQL database on the data volume, copies all configuration data to this database and removes the old database.
2. Saves the following configuration files and settings to the data volume: the appliance configuration file (/etc/awsbackup/config.ini), nginx configuration files (/etc/nginx/nginx.conf, /etc/nginx/proxy\_params), users, MFA and time zone settings, and Linux environment (/etc/ssh/, /root/, /home/).
3. Deploys a temporary EC2 instance from the Ubuntu 22.04 LTS image.
4. Detaches the root volume from the newly created EC2 instance and removes the EC2 instance.
5. Detaches the outdated root volume and attaches the new root volume to the original appliance.
6. Removes the outdated root volume from AWS.
7. Restores the configuration files and settings saved at step 3 to the new root volume.

Limitations and Prerequisites

Before you start the upgrade process, consider the following requirements and limitations:

* The IAM user whose access keys were specified when [deploying a backup appliance](deploy_appliance_account.md) or [connecting to the appliance](connect_appliance_account.md) must be assigned permissions required to perform upgrade. For the list of required permissions, see [Plug-in Permissions](req_permissions.md#permissions_to_upgrade).
* Outbound internet access must be allowed from the backup appliance to the PostgreSQL Apt Repository (apt.postgresql.org, apt-archive.postgresql.org) through port 443 over the HTTPS protocol.
* Outbound internet access must be allowed from the backup appliance to the PostgreSQL website (postgresql.org) through port 443 over the HTTPS protocol to download the repository key <https://www.postgresql.org/media/keys/ACCC4CF8.asc>.
* Outbound internet access must be allowed from the backup appliance to the [Veeam Update Repository](https://repository.veeam.com/) through port 443 over the HTTPS protocol.
* Outbound internet access must be allowed from the backup appliance to the Ubuntu Security Repository (security.ubuntu.com) through port 80 over the HTTP protocol.
* During upgrade, the data volume of the backup appliance will temporarily contain files of 2 databases. That is why the size of the data volume must be twice the total amount of storage space used by the configuration database.
* During upgrade, Veeam Backup & Replication will create a new root volume with default settings. That is why if you have modified the root disk settings, for example, have increased the volume size or enabled volume encryption, these settings will not be transferred, and custom 3rd-party software installed on the backup appliance will not be migrated.
* During upgrade, Veeam Backup & Replication will overwrite custom settings of the /etc/fstab configuration file on the backup appliance with the default settings. That is why if you have previously attached an additional EBS volume to the backup appliance, you must re-mount the volume by adding its label or UUID to the /etc/fstab file.
* After the upgrade process completes, the original root volume will be automatically deleted from AWS.

Eliminating Warnings Received During Upgrade

During upgrade to version 10 from Veeam Backup for AWS version 6.0 or earlier, Veeam Backup & Replication will verify whether the IAM user whose access keys are used to connect to the appliance has sufficient permissions to upgrade the appliance. If some permissions are missing, you will receive a warning.

You can manually grant missing permissions to the IAM user in AWS or instruct Veeam Backup & Replication to do it:

* If you want to grant the missing permissions manually, do the following:

1. Click Copy permissions to Clipboard.

Note that the list of copied permissions will contain all the permissions required to perform the upgrade operation, not the list of missing permissions.

1. In AWS, create an IAM policy with the missing permissions and attach the policy to the IAM user whose access key are used to connect to the appliance.

To learn how to create IAM policies, see [Appendix B. Creating IAM Policies in AWS](create_iam_policy.md).

1. Back to the Veeam Backup & Replication console, click Proceed.

* If you want to instruct Veeam Backup & Replication to grant the missing permissions automatically, click Grant and provide one-time access keys of an IAM user that is [authorized to grant IAM permissions](req_permissions.md#iam_user_grant_permissions) in the opened window. Note that the specified user must belong to the same AWS account in which the backup appliance is deployed.

Veeam Backup & Replication will create an IAM policy with missing permissions and attach the policy to the IAM user whose permissions are used to connect to the appliance.

If you remove the upgraded backup appliance that previously used a marketplace license, then you will no longer be able to switch to the Paid marketplace license, and the appliance will operate using the Free marketplace license. For more information on license editions, see [Licensing](licensing.md).

|  |
| --- |
| Note |
| Veeam Backup & Replication does not store the provided one-time access keys in the configuration database. |

Page updated 11/3/2025

Page content applies to build 10.0.0.232
