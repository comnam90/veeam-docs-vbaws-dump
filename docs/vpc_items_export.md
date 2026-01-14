---
title: "vpc_items_export"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/vpc_items_export.html"
last_updated: "2/28/2025"
product_version: "10.0.0.232"
---


In this article

|  |
| --- |
| Note |
| If you export only specific VPC configuration items, you will not be able to choose a location. By default, Veeam Backup for AWS will create a CloudFormation template to restore to the original location.  When you restore the exported items from the CloudFormation template, all exported VPC configuration items will be newly created in the source AWS Region. If there are any already existing items with the same names in the current VPC configuration, the restored items will be created with new IDs, but with the same names. |

To export specific VPC configuration items to a CloudFormation template, do the following:

1. [Launch the VPC Export wizard](export_items_vpc_launch.md).
2. [Select a restore point and VPCs to export](export_items_vpc_point.md).
3. [Specify an IAM identity for export](export_items_vpc_account.md).
4. [Specify an Amazon S3 bucket where the Cloud Formation template must be placed](export_items_vpc_bucket.md).
5. [Specify a reason for the export](export_items_vpc_reason.md).
6. [Finish working with the wizard](export_items_vpc_finish.md).

Page updated 2/28/2025

Page content applies to build 10.0.0.232
