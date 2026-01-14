---
title: "restore_hiw_dynamodb"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/restore_hiw_dynamodb.html"
last_updated: "11/28/2025"
product_version: "10.0.0.232"
---


In this article

|  |
| --- |
| Important |
| You can restore a DynamoDB table only to the same AWS account to which the source table belongs. |

To restore a DynamoDB table from a backup, Veeam Backup for AWS performs the following steps using native [AWS capabilities](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Restore.TutorialAWS.html):

1. Creates a table in the specified location.
2. Restores backed-up data (items and attributes) to the restored table.
3. Modifies the configuration setting values of the created DynamoDB table.

To learn how to restore a DynamoDB table from a DynamoDB backup or a backup copy, see [DynamoDB Restore](dynamo_restore.md).

Page updated 11/28/2025

Page content applies to build 10.0.0.232
