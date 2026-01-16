---
title: "restore_entire_vpc_mode"
product: "vbaws"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/restore_entire_vpc_mode.html"
last_updated: "10/1/2025"
product_version: "10.0.0.232"
---


In this article

At the Restore Mode step of the wizard, choose whether you want to restore the selected VPC configuration to the original or to a custom location. If you select the Restore to new location, or with different settings option, specify the target AWS Region where to restore the VPC configuration.

|  |
| --- |
| Important |
| If you select the Restore to a new location, or with different settings option, consider that AWS Regions have different lists of the supported AWS services. VPC endpoints created using an AWS service that is not available in the target AWS Region will not be restored. |

[![Restoring VPC Configuration](images/vpc_restore_entire_mode.webp)](images/vpc_restore_entire_mode.webp "Restoring VPC Configuration")

Page updated 10/1/2025

Page content applies to build 10.0.0.232
