---
title: "resource_share"
product: "vbaws"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/resource_share.html"
last_updated: "9/6/2024"
product_version: "10.0.0.232"
---


In this article

If you have multiple AWS accounts and want to deploy worker instances in [production accounts](worker_settings.md), you can create a single resource share in one AWS account for all subnets to which the worker instances will be connected. The resource share can be further used to share these subnets with other AWS accounts belonging to the same organization. For information, see [AWS Documentation](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-sharing.html).

To create a resource share, do the following:

1. Navigate to Services > Security, Identity & Compliance and click Resource Access Manager.
2. In the Resource Access Manager console, use the Region selector to choose an AWS Region in which the resource share will be created.
3. Navigate to Shared by me > Resource shares and click Create resource share.
4. Complete the Create resource share wizard:

1. At the Specify resource share details step, configure the following settings:

1. In the Resource share field, specify a name for the resource share.
2. In the Resources section, enter Subnets in the search field and choose subnets that you want to share.
3. In the Tags section, specify AWS tags that will be assigned to the resource share.

1. At the Associate managed permissions step, keep the default managed permissions associated with the specified subnets.
2. At the Grant access to principal step, use the Principals section to choose whether you want to share the subnets within your organization only. Then, select the AWS account option and specify the IDs of AWS accounts with which you want to share the subnets.

To obtain the IDs, you can either look them up in the AWS Management Console, or send a query to the AWS Command Line Interface (AWS CLI).

1. At the Review and create step, review the configured settings and click Create resource share.

Page updated 9/6/2024

Page content applies to build 10.0.0.232
