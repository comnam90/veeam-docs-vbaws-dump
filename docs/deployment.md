---
title: "deployment"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/deployment.html"
last_updated: "9/1/2025"
product_version: "10.0.0.232"
---


In this article

To deploy Veeam Backup for AWS, do the following:

1. Deploy the backup server as described in the Veeam Backup & Replication User Guide, sections [Installing Veeam Backup & Replication](https://helpcenter.veeam.com/docs/backup/vsphere/install_vbr.html?ver=120) and [Installation on Linux](https://helpcenter.veeam.com/docs/vbr/userguide/deployment_linux.html?ver=13).

Alternatively, you can use a backup server that already exists in your backup infrastructure if it meets the Veeam Plug-In for AWS [system requirements](system_requirements.md).

1. [Install Veeam Plug-In for AWS on the backup server](installing_plugin.md).

This step applies only to Veeam Backup & Replication versions prior to 12. Version 12 (and later) comes with Veeam Plug-In for AWS pre-installed by default.

1. [Deploy a backup appliance in AWS](deploying_appliances.md).

|  |
| --- |
| Important |
| If you install the backup server as described in section Installation on Linux, you will not be able to access the Veeam Backup for AWS functionality from the Veeam Backup & Replication Web UI. To work around the issue, [install a remote Veeam Backup & Replication console](https://helpcenter.veeam.com/docs/vbr/userguide/install_console.html?ver=13) — and then log in to the console using the name or IP address of the backup server. For more information, see the Veeam Backup & Replication User Guide, section [Logging in to Veeam Backup & Replication](https://helpcenter.veeam.com/docs/vbr/userguide/logon_to_console.html?ver=13). |

Related Topics

* [Failure and Recovery](failure_recovery.md)
* [Appendix E. Uninstalling Backup Appliances Deployed from AWS Marketplace](uninstall.md)

Page updated 9/1/2025

Page content applies to build 10.0.0.232
