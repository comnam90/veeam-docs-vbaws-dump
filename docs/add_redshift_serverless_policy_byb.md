---
title: "Before You Begin"
product: "vbaws"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/add_redshift_serverless_policy_byb.html"
last_updated: "3/12/2026"
product_version: "10.0.0.232"
---

# Before You Begin


Before you protect Redshift Serverless namespaces, consider the following:

* Veeam Backup for AWS supports backup of only those Redshift Serverless properties that are described in section [Protecting Redshift Serverless](overview_redshift_serverless.md#properties).

* Veeam Backup for AWS supports creating cloud-native backups for Redshift Serverless namespaces only to the same AWS accounts to which the source namespaces belong and the same AWS Region where the source namespaces reside.

* Make sure that workgroups are associated with Redshift Serverless namespaces that you plan to protect. Otherwise, the backup operation may fail to complete successfully.
* Due to technical limitations, Veeam Backup for AWS does not estimate the cost of creating and maintaining cloud-native backups of Redshift Serverless namespaces.

* Veeam Backup for AWS runs retention sessions at 4:00 AM by default, according to the time zone set on the backup appliance. If you schedule backup policies to execute at 4:00 AM, the backup policies and retention tasks will be queued.


