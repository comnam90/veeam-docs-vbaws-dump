---
title: "restore_hiw_vpc_items"
product: "vbaws"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/restore_hiw_vpc_items.html"
last_updated: "9/12/2024"
product_version: "10.0.0.232"
---


In this article

To restore specific items of the VPC configuration from a backup, Veeam Backup for AWS performs the following steps:

1. Retrieves from the Veeam Backup for AWS database the backed-up VPC configuration data on items added to a [restore list](restore_items_vpc_point.md).
2. Validates the restore operation: sends API request to AWS to verify that AWS service quotas are not exceeded and there are no subnet CIDR block conflicts.
3. Retrieves information on existing items and their settings in the current Amazon VPC configuration.
4. Validates the restore list: sends API requests to AWS to check whether any of the selected VPC configuration items depend on other items that are missing from the current VPC configuration.

In case any VPC configuration items on which the selected items depend are missing, Veeam Backup for AWS allows the user to add the missing items to the restore list.

1. Restores the selected items of the backed-up VPC configuration:

* Creates the missing VPC configuration items.
* Modifies settings of the existing items that do not match the backed-up settings.

|  |
| --- |
| Important |
| * VPC peering connections will have the Pending Acceptance status after restoring. To accept the restored VPC peering connections, use the AWS Management Console. For more information, see [AWS Documentation](https://docs.aws.amazon.com/vpc/latest/peering/create-vpc-peering-connection.html).  * If restore of any selected item fails, Veeam Backup for AWS will stop the restore operation and initiate a rollback. During the rollback, Veeam Backup for AWS will delete all newly created items, but will retain all changes made to the existing VPC configuration items. |

To learn how to restore restores the selected VPC configuration items from a VPC configuration backup, see [Performing Selected Items Restore](vpc_items_restore.md).

Page updated 9/12/2024

Page content applies to build 10.0.0.232
