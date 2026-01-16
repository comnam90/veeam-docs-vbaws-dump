---
title: "restore_volume_mode"
product: "vbaws"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/restore_volume_mode.html"
last_updated: "9/29/2025"
product_version: "10.0.0.232"
---


In this article

At the Restore Mode step of the wizard, choose whether you want to restore the selected EBS volumes to the original or to a custom location. If you select the Restore to new location, or with different settings option, specify the AWS Region and Availability Zone to which Veeam Backup for AWS will place the restored EBS volumes.

|  |
| --- |
| Important |
| For Veeam Backup for AWS to be able to perform restore to the original location, the IAM role specified at the [Account](restore_volume_account.md) step of the wizard must belong to the AWS account to which the source EC2 instance belongs. |

[![Restoring EBS Volumes](images/restore_volume_mode.webp)](images/restore_volume_mode.webp "Restoring EBS Volumes")

Page updated 9/29/2025

Page content applies to build 10.0.0.232
