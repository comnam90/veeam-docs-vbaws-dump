---
title: "vpc_entire_export"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/vpc_entire_export.html"
last_updated: "7/3/2025"
product_version: "10.0.0.232"
---


In this article

You can export the entire VPC configuration and restore it from the CloudFormation template to the original location or to a new location.

|  |
| --- |
| Important |
| If you plan to restore the exported VPC configuration, consider that restore to a new location is not supported for the following VPC configuration items:   * Client VPN endpoints. * Customer gateways and load balancer listeners that use authentication certificates. |

To export the entire VPC configuration to a CloudFormation template, do the following:

1. [Launch the VPC Export wizard](export_entire_vpc_launch.md).
2. [Select a restore point and VPCs to export](export_entire_vpc_point.md).
3. [Specify an IAM identity for export](export_entire_vpc_account.md).
4. [Choose an export mode](export_entire_vpc_mode.md).
5. [Configure mapping for Availability Zones](export_entire_vpc_zone_mapping.md).
6. [Review settings for VPC peering connections](export_entire_vpc_connection.md).
7. [Specify an Amazon S3 bucket where the Cloud Formation template must be placed](export_entire_vpc_bucket.md).
8. [Specify a reason for export](export_entire_vpc_reason.md).
9. [Review export settings](export_entire_vpc_finish.md).

Page updated 7/3/2025

Page content applies to build 10.0.0.232
