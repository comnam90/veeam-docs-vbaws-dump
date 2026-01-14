---
title: "dynamo_restore_ui"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/dynamo_restore_ui.html"
last_updated: "12/12/2025"
product_version: "10.0.0.232"
---


In this article

In case of a disaster, you can restore a DynamoDB table from a DynamoDB backup or backup copy. Veeam Backup for AWS allows you to restore one or more DynamoDB tables at a time, to the original location or to a new location. To learn how DynamoDB restore works, see [DynamoDB Restore](restore_hiw_dynamodb.md).

|  |
| --- |
| Important |
| * Veeam Backup for AWS supports restoring DynamoDB tables only to the same AWS account where the source tables reside.  * Veeam Backup for AWS supports restoring only those DynamoDB table properties that are described in section [Protecting DynamoDB Tables](overview_dynamo.md#table_parameters). |

How to Perform DynamoDB Restore

To restore a protected DynamoDB table, do the following:

1. [Launch the DynamoDB Restore wizard](restore_launch_dynamo.md).
2. [Select a restore point](restore_point_dynamo.md).
3. [Specify account settings for restore](restore_account_dynamo.md).
4. [Choose a restore mode](restore_mode_dynamo.md).
5. [Enable encryption for the restored table](restore_encryption_dynamo.md).
6. [Specify configuration settings](restore_type_dynamo.md).
7. [Choose capacity mode for the restored table](restore_capacity_mode_dynamo.md).
8. [Specify a restore reason](restore_reason_dynamo.md).
9. [Finish working with the wizard](restore_finish_dynamo.md).

Page updated 12/12/2025

Page content applies to build 10.0.0.232
