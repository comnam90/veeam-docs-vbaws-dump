---
title: "integration_vbr"
product: "vbaws"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/integration_vbr.html"
last_updated: "8/20/2025"
product_version: "10.0.0.232"
---


In this article

Starting from version 7.0, Veeam Backup for AWS is part of the Veeam Backup & Replication solution. Veeam Plug-In for AWS extends the Veeam Backup & Replication functionality and allows you to add backup appliances to Veeam Backup & Replication. With Veeam Plug-In for AWS, you can manage data protection and recovery operations for all these appliances from a single Veeam Backup & Replication console.

Versions 7.0, 8.0, 9.0 and 10 come with 6 major features — the ability to create image-level backups of Microsoft SQL Server and PostgreSQL DB instances, as well as the ability to back up DynamoDB tables, Redshift clusters, Redshift Serverless namespaces and FSx file systems. These features are available only for backup appliances managed by a Veeam Backup & Replication server. To unlock the full functionality, [install Veeam Plug-In for AWS on the server](deployment.md) and [add your appliances](connect_appliance.md) to the backup infrastructure.

|  |
| --- |
| Note |
| The current version of the Veeam Backup & Replication console comes with Veeam Plug-In for AWS pre-installed by default. For the list of compatible versions of Veeam Backup & Replication, see [System Requirements](system_requirements.md#versions). |

Considerations and Limitations

Before you add backup appliances to the backup infrastructure, consider the following:

* If you remove a backup appliance from the backup infrastructure, the following will happen:

* You will no longer be able to create image-level backups of Microsoft SQL Server and PostgreSQL DB instances, and the existing RDS backup policies configured to create these backups will start failing. To work around the issue, you can disable image-level backup when [editing backup policy settings](policies_edit.md).

* You will no longer be able neither to add and start DynamoDB, FSx, Redshift Clusters and Redshift Serverless backup policies, nor to manually back up DynamoDB tables, FSx file systems, Redshift clusters and Redshift Serverless namespaces.

* If the connection between a backup appliance and the backup server is lost for more than 31 days, the appliance will enter the standalone mode, and you will no longer be able to back up Microsoft SQL Server instances, PostgreSQL DB instances, DynamoDB tables, FSx file systems, Redshift clusters and Redshift Serverless namespaces.

Related Topics

* [Protecting RDS Resources](overview_rds.md)
* [Protecting DynamoDB Tables](overview_dynamo.md)
* [Protecting Redshift Clusters](overview_redshift.md)
* [Protecting Redshift Serverless](overview_redshift_serverless.md)
* [Protecting FSx File Systems](overview_fsx.md)

Page updated 8/20/2025

Page content applies to build 10.0.0.232
