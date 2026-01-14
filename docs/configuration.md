---
title: "configuration"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/configuration.html"
last_updated: "12/9/2025"
product_version: "10.0.0.232"
---


In this article

To start working with Veeam Backup for AWS, perform a number of steps for its configuration:

1. [Add backup appliances to the backup infrastructure](connect_appliance.md).
2. [Add repositories that will be used to store backed-up data](repositories.md).

This step applies if you plan to protect EC2 or DB instances with image-level backups, to perform EFS indexing operations, to back up Veeam Backup for AWS configuration and to keep additional copies of Amazon VPC configuration backups in Amazon S3.

1. Configure the added backup appliances:

1. [Add IAM roles to access AWS services and resources that belong to a standalone AWS account](accounts_iam_roles.md).
2. [[Optional] Add AWS Organizations to access resources that belong to AWS accounts across organizational units within the organizations](managing_organizations.md).
3. [[Optional] Add users to control access to Veeam Backup for AWS](accounts_vba_users.md).
4. [[Optional] Add database accounts to access databases of PostgreSQL DB instances](accounts_database.md).
5. [[Optional] Configure worker instance settings](workers.md).

If you do not configure settings for worker instances, Veeam Backup for AWS will use the default settings of AWS Regions where worker instances will be deployed.

1. [[Optional] Configure policy templates that will be used by SLA-based backup policies](sla_storage_manage.md).
2. [[Optional] Configure private network deployment, global retention, email notification and single-sign-on settings](general_settings.md).

|  |
| --- |
| Note |
| Even after you add IAM roles or AWS Organizations that manage your AWS resources and configure all the necessary settings, Veeam Backup for AWS will not populate [the list of resources on the Resources page](aws_resources.md) — unless you create backup policies and specify regions where the AWS resources belong, as described in section [Performing Backup](backup.md). |

Page updated 12/9/2025

Page content applies to build 10.0.0.232
