---
title: "vpc_restore_ui"
product: "vbaws"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/vpc_restore_ui.html"
last_updated: "11/7/2025"
product_version: "10.0.0.232"
---


In this article

Veeam Backup for AWS offers the following disaster recovery operations:

* [VPC configuration restore](vpc_entire_restore.md) — restore an entire VPC configuration.
* [Selected items restore](vpc_items_restore.md) — restore the selected VPC configuration items.

You can restore the VPC configuration data to the most recent state or to any available restore point.

|  |
| --- |
| Important |
| When restoring VPC route tables, consider that routes that had the blackhole state when a restore point was created will not be restored and a restore session will complete with warning. In this case, it is recommended to check the restored target route table configurations in the AWS Management Console to ensure that all traffic flows correctly. To learn how to configure routes in route tables, see [AWS Documentation](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_Route_Tables.html). |

Related Topics

[Exporting VPC Configuration](export_vpc.md)

Page updated 11/7/2025

Page content applies to build 10.0.0.232
