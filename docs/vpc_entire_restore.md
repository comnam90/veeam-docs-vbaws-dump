---
title: "vpc_entire_restore"
product: "vbaws"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/vpc_entire_restore.html"
last_updated: "7/3/2025"
product_version: "10.0.0.232"
---


In this article

In case of unexpected configuration changes, you can restore entire Amazon VPC configuration from a VPC configuration backup. Veeam Backup for AWS allows you to restore the VPC configuration to the original location or to a new location.

|  |
| --- |
| Important |
| Restore to a new location is not supported for the following VPC configuration items:   * Client VPN endpoints. * Customer gateways and load balancer listeners that use authentication certificates. |

How to Perform Entire VPC Configuration Restore

To restore the entire VPC configuration, do the following:

1. [Launch the VPC Restore wizard](restore_entire_vpc_launch.md).
2. [Select a restore point and VPCs to restore](restore_entire_vpc_point.md).
3. [Specify account settings for restore](restore_entire_vpc_account.md).
4. [Choose a restore mode](restore_entire_vpc_mode.md).
5. [Configure mapping for Availability Zones](restore_entire_vpc_zone_mapping.md).
6. [Review settings of VPC peering connections](restore_entire_vpc_connection.md).
7. [Specify a restore reason](restore_entire_vpc_reason.md).
8. [Finish working with the wizard](restore_entire_vpc_finish.md).

Page updated 7/3/2025

Page content applies to build 10.0.0.232
