---
title: "redshift_restore_ui"
product: "vbaws"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/redshift_restore_ui.html"
last_updated: "12/12/2025"
product_version: "10.0.0.232"
---


In this article

In case of a disaster, you can restore a Redshift cluster from a Redshift backup. Veeam Backup for AWS allows you to restore one or more Redshift clusters at a time to the original location, with the source or different settings. To learn how Redshift restore works, see [Redshift Restore](restore_hiw_redshift.md).

|  |
| --- |
| Important |
| * Veeam Backup for AWS supports restoring Redshift clusters only to the same AWS accounts to which the source clusters belong and to the same AWS Region where the source cluster resides.  * Veeam Backup for AWS supports restoring only those Redshift cluster properties that are described in section [Protecting Redshift Clusters](overview_redshift.md#properties).  * Veeam Backup for AWS does not support restoring Amazon Redshift clusters with the Multi-AZ deployment. These clusters will be restored as clusters with the Single-AZ deployment. |

How to Perform Redshift Restore

To restore a protected Redshift cluster, do the following:

1. [Launch the Redshift Restore wizard](restore_launch_redshift.md).
2. [Select a restore point](restore_point_redshift.md).
3. [Specify account settings for restore](restore_account_redshift.md).
4. [Choose a restore mode](restore_mode_redshift.md).
5. [Enable encryption for the restored cluster](restore_encryption_redshift.md).
6. [Configure Redshift cluster settings](restore_redshift_settings.md).
7. [Configure network settings](restore_redshift_networks.md).
8. [Specify a restore reason](restore_reason_redshift.md).
9. [Finish working with the wizard](restore_finish_redshift.md).

Page updated 12/12/2025

Page content applies to build 10.0.0.232
