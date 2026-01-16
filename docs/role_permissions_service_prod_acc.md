---
title: "role_permissions_service_prod_acc"
product: "vbaws"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/role_permissions_service_prod_acc.html"
last_updated: "4/28/2025"
product_version: "10.0.0.232"
---


In this article

When creating a new [worker configuration](worker_add_config_prod.md), you specify an IAM role whose permissions will be used to list network settings available in AWS Regions of production AWS accounts. The specified IAM role must be granted the following permissions:

|  |
| --- |
| {     "Version": "2012-10-17",     "Statement": [         {             "Action": [                 "ec2:DescribeAvailabilityZones",                 "ec2:DescribeVpcs",                 "ec2:DescribeRegions",                 "ec2:DescribeAccountAttributes",                 "ec2:DescribeSubnets",                 "ec2:DescribeSecurityGroups"             ],                       "Resource": "\*",                       "Effect": "Allow"           }     ]  } |

Page updated 4/28/2025

Page content applies to build 10.0.0.232
