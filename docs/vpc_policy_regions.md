---
title: "vpc_policy_regions"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/vpc_policy_regions.html"
last_updated: "9/29/2025"
product_version: "10.0.0.232"
---


In this article

At the Regions step of the wizard, select AWS Regions whose VPC configuration you want to back up.

Veeam Backup for AWS allows you to automatically collect and back up VPC configuration data for all AWS Regions selected for EC2, RDS, DynamoDB, Redshift Clusters, Redshift Serverless, EFS and FSx backup policies. To do that, [enable automatic protection](vpc_policy_regions_automatic.md) for AWS Regions. To retrieve VPC configurations of all automatically protected AWS Regions, Veeam Backup for AWS will use the permissions of IAM roles specified either in the [organization settings](organization_add_settings.md) (if you back up resources within an AWS Organization), or in the backup policy settings (if you back up resources belonging to an AWS account).

You can also configure the VPC Configuration Backup policy to protect configuration data for AWS Regions that are not specified in the settings of any backup policy, or choose another IAM role whose permissions Veeam Backup for AWS will use to collect the VPC configuration data of the automatically protected AWS Regions. To do that, [manually add AWS Regions](vpc_policy_regions_manual.md) to the VPC Backup policy and configure backup settings for them.

Page updated 9/29/2025

Page content applies to build 10.0.0.232
