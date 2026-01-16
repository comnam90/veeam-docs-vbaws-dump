---
title: "restore_hiw_vpc"
product: "vbaws"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/restore_hiw_vpc.html"
last_updated: "12/4/2025"
product_version: "10.0.0.232"
---


In this article

Veeam Backup for AWS offers the following disaster recovery operations:

* [VPC configuration restore](restore_hiw_vpc_entire.md) — restores an entire VPC configuration from a VPC configuration backup. You can restore the VPC configuration to the original location or to a new location.
* [Selected items restore](restore_hiw_vpc_items.md) — restores the selected VPC configuration items from a VPC configuration backup. You can restore specific VPC configuration items only to the original location.

You can restore the VPC configuration data to the most recent state or to any available restore point.

|  |
| --- |
| Important |
| When restoring VPC route tables, consider that routes that had the blackhole state when a restore point was created will not be restored and a restore session will complete with warning. In this case, it is recommended that you check the restored target route table configurations in the AWS Management Console to ensure that all traffic flows correctly. To learn how to configure routes in route tables, see [AWS Documentation](https://docs.aws.amazon.com/vpc/latest/tgw/tgw-route-tables.html). |

Page updated 12/4/2025

Page content applies to build 10.0.0.232
