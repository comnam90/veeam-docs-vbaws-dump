---
title: "uninstall_ami"
product: "vbaws"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/uninstall_ami.html"
last_updated: "10/10/2025"
product_version: "10.0.0.232"
---


In this article

When you deploy a backup appliance from the Amazon Machine Image (AMI), Veeam Backup for AWS creates a number of resources while operating in AWS, and these resources are not removed from infrastructure automatically when you delete the backup appliance. To uninstall Veeam Backup for AWS, you must locate and delete the following resources from your infrastructure:

* AWS::IAM::InstanceProfile
* AWS::DLM::LifecyclePolicy
* AWS::CloudWatch::Alarm
* AWS::EC2::SecurityGroup
* AWS::IAM::Role
* AWS::EC2::Instance

To delete a resource, do the following:

1. Log in to the AWS Management Console using credentials of an AWS account where Veeam Backup for AWS is installed.
2. Use the region selector in the upper-right corner of the page to select the AWS Region in which the backup appliance resides.
3. Navigate to AWS service to which the AWS resource belong.
4. Select the AWS resource that you want to remove, and click Delete.

Page updated 10/10/2025

Page content applies to build 10.0.0.232
