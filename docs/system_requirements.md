---
title: "system_requirements"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/system_requirements.html"
last_updated: "11/28/2025"
product_version: "10.0.0.232"
---


In this article

When you plan to install Veeam Plug-In for AWS, consider the following hardware and software requirements.

Backup Server

The machine where Veeam Plug-In for AWS will run must meet system requirements described in the Veeam Backup & Replication User Guide, section [System Requirements](https://helpcenter.veeam.com/docs/vbr/userguide/system_requirements.html?ver=13). Additionally, the following software must be installed:

* Microsoft .NET Core Runtime 8.0.21
* Microsoft ASP.NET Core Shared Framework 8.0.21

|  |
| --- |
| Important |
| If the version of Microsoft .NET Core Runtime differs from the version of Microsoft ASP.NET Core Shared Framework, Veeam Plug-In for AWS services will not be able to start. |

AWS Services

The [backup appliance](backup_appliances.md) and [worker instances](worker_instances.md) must have outbound internet access to a number of AWS services. For the list of services, see [AWS Services](system_requirements_aws_services.md).

Web Browsers

Internet Explorer is not supported. To access Veeam Backup for AWS, use Microsoft Edge (latest version), Mozilla Firefox (latest version) or Google Chrome (latest version).

Version Compatibility

The following table lists compatible versions of Veeam Backup & Replication, Veeam Plug-In for AWS and Veeam Backup for AWS.

| Veeam Backup & Replication Build | Veeam Plug-In for AWS Build | Veeam Backup for AWS Build |
| --- | --- | --- |
| 13.0.1.180 | 13.10.0.225 | 10.0.0.232 |
| 13.0.0.4967 | 13.9.1.467 | 9.1.0.45 |
| 12.3.2.3617 | 12.9.0.281 |
| 12.3.1.1139 | 9.0.0.304 |
| 12.1.2.172 | 12.8.1.8 | 8.1.0.7 |
| 12.8.0.3264 | 8.0.0.845 |
| 12.1.0.2131 | 12.7.0.1255 | 7.0.0, 7.0.1 |
| 12.0.0.1420 | 12.2.6.5 | 6.1.0, 6.1.1, 6.1.2 |
| 12.1.6.93 |
| 12.0.6.956 | 6.0.0, 6.0.1, 6.0.2 |

Page updated 11/28/2025

Page content applies to build 10.0.0.232
