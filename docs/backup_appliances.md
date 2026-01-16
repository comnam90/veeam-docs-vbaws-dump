---
title: "backup_appliances"
product: "vbaws"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/backup_appliances.html"
last_updated: "8/8/2025"
product_version: "10.0.0.232"
---


In this article

A backup appliance is a Linux-based EC2 instance where Veeam Backup for AWS is installed.

If you have multiple backup appliances in AWS, you can add the appliances to Veeam Backup & Replication, and then use the Veeam Backup & Replication console as the central management console for Veeam Backup for AWS operations. For more information on the Veeam Backup & Replication console, see the [Veeam Backup & Replication User Guide](https://helpcenter.veeam.com/docs/vbr/userguide/backup_console.html?ver=13).

Backup Appliance Software

The EC2 instance running Veeam Backup for AWS is deployed with the pre-installed set of software components:

* Ubuntu 22.04 LTS
* ASP.NET Core Runtime 8.0
* PostgreSQL 15
* nginx 1.18
* libpam-google-authenticator 20191231-2
* Veeam Backup for AWS installation packages

In case any software updates become available for the backup appliance, these updates can be installed using the Veeam Updater service as described in section [Updating Veeam Backup for AWS](update_vb.md).

Backup Appliance Functionality

The backup appliance performs the following administrative activities:

* Manages architecture components.
* Coordinates snapshot creation, backup and recovery tasks.
* Controls backup policy scheduling.
* Generates daily reports and email notifications.
* Manages backup and snapshot retention tasks.

Backup Appliance Components

The backup appliance uses the following components:

* Backup service — coordinates data protection and disaster recovery operations.

* Configuration database — stores data on the existing backup policies, worker instance configurations, added IAM roles, sessions and so on, as well as information on the available and protected resources collected from AWS.
* Configuration restore service — allows users to back up and restore the configuration of the backup appliance.
* Web UI — provides a web interface that allows user to access to the Veeam Backup for AWS functionality.
* Veeam Updater service — allows Veeam Backup for AWS to check, view and install product and software package updates.
* Veeam FLR service — allows users to restore individual files and folders of protected EC2 instances.
* Self Backup service — allows Veeam Backup for AWS to back up and restore the configuration database of the backup appliance.
* REST API service — allows users to perform operations with Veeam Backup for AWS entities using HTTP requests and standard HTTP methods. For more information, see the [Veeam Backup for AWS REST API Reference](https://helpcenter.veeam.com/references/vbaws/9/rest/1.7-rev0/tag/SectionOverview).

Page updated 8/8/2025

Page content applies to build 10.0.0.232
