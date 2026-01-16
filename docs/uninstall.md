---
title: "uninstall"
product: "vbaws"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/uninstall.html"
last_updated: "10/10/2025"
product_version: "10.0.0.232"
---


In this article

Starting from version 8.0, you can deploy Veeam Backup for AWS from the Veeam Backup & Replication console only. However, if an appliance was previously deployed from the AWS Marketplace or is running Veeam Backup for AWS version 3.x (or earlier), use one of the following options to uninstall the solution:

* If you deployed a backup appliance from AWS Marketplace, you must [delete the CloudFormation stack](uninstall_cloudformation.md) created while installing Veeam Backup for AWS. All resources included in the stack will be deleted automatically.
* If you deployed a backup appliance from the AMI, you must [manually delete AWS resources](uninstall_ami.md) created while installing Veeam Backup for AWS.

|  |
| --- |
| Important |
| When you deploy Veeam Backup for AWS from the Veeam Backup & Replication console, the CloudFormation stack is not created and AWS resources cannot be managed as a single unit. Keep in mind that these resources are not automatically deleted from AWS when you remove the backup appliance from Veeam Backup & Replication. To learn how to manually delete resources created during Veeam Backup for AWS installation, see [Removing Appliances](remove_appliance.md). |

Note that backed-up data will not be removed automatically after you uninstall the solution. You can keep this data in your AWS environment and import it to a new backup appliance:

* To import cloud-native snapshots, rescan AWS Regions where the snapshots are stored. The snapshots will be automatically imported to the configuration database.
* To import image-level backups, assign the Amazon S3 bucket where the backups are stored to a new backup repository as described in section [Adding Backup Repositories Using Console](repositories_add_console.md).

If you do not want to keep the backed-up data, remove it manually as described in section [Managing Backed-Up Data](backups_view.md). Alternatively, you can remove the data using the AWS Management Console:

1. Log in to the AWS Management Console using credentials of an AWS account where the data is stored.
2. Use the region selector in the upper-right corner of the page to select the AWS Region in which the backed-up data is stored.
3. Remove the backed-up data:

* To remove backups, navigate to Services > S3. Select an Amazon S3 bucket where the backups are stored. Navigate to Veeam > Backup, select the backup repository folder, and click Delete.

Note that you cannot remove immutable backups stored in the Amazon S3 bucket with 3 Object Lock enabled until the default retention period expires.

* To remove RDS cloud-native snapshots, navigate to Services > Aurora and RDS > Snapshots, select the necessary Veeam snapshots, and click Delete snapshot.
* To remove EC2 cloud-native snapshots, navigate to Services > EC2 > Snapshots, select the necessary Veeam snapshots, and click Actions > Delete snapshot.
* To remove EFS, FSx, DynamoDB or Redshift cloud-native backups, navigate to Services > AWS Backup > Vaults, select the necessary recovery points, and click Actions > Delete.

Page updated 10/10/2025

Page content applies to build 10.0.0.232
