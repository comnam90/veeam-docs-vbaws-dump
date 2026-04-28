---
title: "Redshift Serverless Restore Using Web UI"
product: "vbaws"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/redshift_serverless_restore_ui.html"
last_updated: "4/27/2026"
product_version: "10.0.0.232"
---

# Redshift Serverless Restore Using Web UI


In case of a disaster, you can restore a Redshift Serverless namespace from a cloud-native backup. Veeam Backup for AWS allows you to restore only one Redshift Serverless namespace at a time to the original, any existing or a new namespace. To learn how Redshift Serverless restore works, see [Redshift Serverless Restore](restore_hiw_redshift_serverless.md).

|  |
| --- |
| Important |
| * Veeam Backup for AWS supports restoring Redshift Serverless namespaces only to the same AWS accounts to which the source namespaces belong and to the same AWS Region where the source namespaces reside.  * Veeam Backup for AWS supports restoring only those Redshift Serverless namespace properties listed in section [Protecting Redshift Serverless](overview_redshift_serverless.md#properties).  * Veeam Backup for AWS does not support restoring Amazon Redshift Serverless namespaces to provisioned clusters. * Veeam Backup for AWS does not support restoring tables of Amazon Redshift Serverless namespaces. |

To restore a protected Redshift Serverless namespace, do the following:

1. [Launch the Redshift Serverless Restore wizard](restore_launch_redshift_serverless.md).
2. [Select a restore point](restore_point_redshift_serverless.md).
3. [Specify account settings for restore](restore_account_redshift_serverless.md).
4. [Choose a restore mode](restore_mode_redshift_serverless.md).
5. [Configure workgroup settings](restore_redshift_serverless_workgroup.md).
6. [Configure namespace settings](restore_redshift_serverless_namespace.md).
7. [Specify a restore reason](restore_reason_redshift_serverless.md).
8. [Finish working with the wizard](restore_finish_redshift_serverless.md).


