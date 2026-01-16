---
title: "immutability"
product: "vbaws"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/immutability.html"
last_updated: "12/15/2025"
product_version: "10.0.0.232"
---


In this article

Veeam Backup for AWS allows you to protect EC2, RDS and VPC configuration data stored in backup repositories from deletion by making the data temporarily immutable. To do that, Veeam Backup for AWS uses [Amazon S3 Object Lock](https://docs.aws.amazon.com/AmazonS3/latest/userguide/object-lock.html) — once imposed, S3 Object Lock prevents objects from being deleted or overwritten for a specific immutability period. The immutability period is set based on the retention policy configured in the backup policy settings.

|  |
| --- |
| Note |
| To reduce the number of requests sent to immutable repositories during EC2 and RDS backup operations, Veeam Backup for AWS leverages the [Block Generation mechanism](block_generation.md). |

Considerations and Limitations

Before you start creating immutable backups, keep in mind the following limitations:

* S3 Object Lock and S3 Versioning must be enabled for an Amazon S3 bucket in which the immutable backup repository will be located. The default retention period must not be configured in the Object Lock settings. For more information on the S3 Versioning and S3 Object Lock features, see [AWS Documentation](https://docs.aws.amazon.com/AmazonS3/latest/userguide/data-protection.html).

* Veeam Backup for AWS does not support changes made to immutability settings in the AWS Management Console for buckets that are already used as target locations for image-level backups.

* An IAM role that you plan to specify to create the immutable backup repository and further to access the repository when performing data protection and recovery tasks must be assigned permissions to collect immutability settings of Amazon S3 buckets and to create immutable backups. For more information on the required permissions, see [Repository IAM Role Permissions](role_permissions_repo.md).

* Veeam Backup for AWS does not support storing indexes of EFS file systems and backups of the appliance configuration database in immutable repositories.
* You cannot manually remove immutable data from immutable repositories using the Veeam Backup for AWS Web UI, as described in sections [Removing EC2 Backups and Snapshots](backups_remove.md), [Removing RDS Backups and Snapshots](snapshots_remove_rds.md) and [Removing VPC Configuration Backups](backups_remove_vpc.md).
* You can neither remove immutable data from AWS using any cloud service provider tools nor request the technical support department to do it for you. Since Veeam Backup for AWS uses S3 Object Lock in the compliance mode, none of the protected objects can be overwritten or deleted by any user, including the root user in your AWS account. For more information on S3 Object Lock retention modes, see [AWS Documentation](https://docs.aws.amazon.com/AmazonS3/latest/userguide/object-lock.html#object-lock-retention-modes).

How To Create Immutable Backups

To protect backups created with Veeam Backup for AWS from deletion by making them temporarily immutable, perform the following steps:

1. [Add a backup repository with immutability enabled](repositories_add_ui.md#enable_efs_indexing).
2. Create a backup policy and specify the backup repository with immutability enabled as the target location for image-level backups. For more information, see [Creating Scheduled-Based Backup Policies](policies_create.md), [Creating SLA-Based EC2 Backup Policies](ec2_sla_create.md), [Creating RDS Backup Policies](policies_create_rds.md), [Editing VPC Configuration Backup Policy](policies_edit_vpc.md).

Page updated 12/15/2025

Page content applies to build 10.0.0.232
