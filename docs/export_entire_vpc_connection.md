---
title: "export_entire_vpc_connection"
product: "vbaws"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/export_entire_vpc_connection.html"
last_updated: "9/29/2025"
product_version: "10.0.0.232"
---


In this article

[This step applies only if you have selected the Export to a new location option at the Export Mode step of the wizard]

At the Peering Connection step of the wizard, review VPC peering connection settings. You cannot modify the VPC peering connection settings for the exported VPC. By default, Veeam Backup for AWS will export VPC peering connections as follows:

* If you export both VPCs between which you have created a peering connection, Veeam Backup for AWS will create a peering connection between the exported VPCs in the target AWS Region.
* If you export a VPC that has a peering connection to a VPC in the same AWS Region, Veeam Backup for AWS will create an inter-region peering connection between the exported VPC in the target AWS Region and the VPC with which the source VPC is peered in the source AWS Region.
* If you export a VPC that has a peering connection to a VPC in another AWS Region, Veeam Backup for AWS will create an inter-region peering connection between the exported VPC in the target AWS Region and the VPC with which the source VPC is peered in the other AWS Region.

|  |
| --- |
| Note |
| VPC peering connections will have the Pending Acceptance status after restoring from the exported CloudFormation template. To accept the restored VPC peering connections, use the AWS Management Console. For more information, see [AWS Documentation](https://docs.aws.amazon.com/vpc/latest/peering/create-vpc-peering-connection.html). |

[![Exporting VPC Configuration](images/vpc_restore_entire_connection.webp)](images/vpc_restore_entire_connection.webp "Exporting VPC Configuration")

Page updated 9/29/2025

Page content applies to build 10.0.0.232
