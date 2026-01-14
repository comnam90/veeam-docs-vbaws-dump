---
title: "restore_entire_before_you_begin"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/restore_entire_before_you_begin.html"
last_updated: "12/15/2025"
product_version: "10.0.0.232"
---


In this article

Before you restore EC2 instances, consider the following limitations:

* To restore an EC2 instance from a backup that is stored in an archive backup repository, you must retrieve the archived data first. You can either retrieve the archived data manually before you begin the restore operation, or launch the data retrieval process right from the Instance Restore wizard. To learn how to retrieve data manually, see [Retrieving EC2 Data From Archive](data_retrieval.md).

* If you restore multiple EC2 instances that have the same EBS volume attached, Veeam Backup for AWS creates a separate volume for each instance and enables the Multi-Attach option for all volumes. After the restore operation completes, you can manually delete extra EBS volumes in the AWS Management Console and attach the necessary volume to the instances.

For more information on Amazon EBS Multi-Attach, see [AWS Documentation](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-volumes-multi.html).

* [Applies only if you plan to restore EC2 instances to a new location or with different settings] Veeam Backup for AWS restores EC2 instances with a single network interface and assigns a new primary private IP address to each instance.
* [Applies only if you plan to restore EC2 instances to the original location] If [stop protection](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-stop-protection.html) or [termination protection](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/terminating-instances.html#Using_ChangingDisableAPITermination) is enabled on an EC2 instance, Veeam Backup for AWS will not be able to restore the instance and will raise an error notifying that you must disable stop protection or termination protection on the source instance.
* [Applies only if you plan to restore EC2 instances to the original location] Veeam Backup for AWS does not support restoring EC2 instances if the source instances with termination protection and stop protection enabled still exist in AWS.

* Veeam Backup for AWS does not support restore of IPv6 addresses, tags of Elastic IP addresses and prefixes assigned to Amazon EC2 network interfaces attached to EC2 instances.

* [Applies only if you plan to restore EC2 instances to the original location] Veeam Backup for AWS restores the instance and all network interfaces that were attached to the source EC2 instance. However, keep in mind the following:

* If the Elastic IP address that was assigned to the source EC2 instance is still assigned to this EC2 instance, the address will be reassigned to the restored instance.
* If the Elastic IP address is in use by any other EC2 instance, Veeam Backup for AWS will raise a warning. If you decide to proceed with the restore operation, the address will not be associated with the restored instance. Note that Veeam Backup for AWS will not allocate a new Elastic IP address to your AWS account.
* If the Elastic IP address that was assigned to the source EC2 instance has been removed from AWS, Veeam Backup for AWS will attempt to restore this address using the native [AWS capabilities](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/elastic-ip-addresses-eip.html#using-eip-recovering).
* If private IP addresses that were assigned to the source EC2 instance are in use by the source or any other EC2 instance, Veeam Backup for AWS will raise a warning. If you decide to proceed with the restore operation, the restored EC2 instance will be assigned new private IP addresses.
* If the source instance still exists in AWS, Veeam Backup for AWS will raise a warning. If you decide to proceed with the restore operation, the source EC2 instance, including all EBS volumes and all network interfaces attached to it, will be automatically deleted from AWS.

Note that EBS volumes excluded from the backup scope and volumes for which the DeleteOnTermination attribute is set to false will also be deleted from AWS.

Page updated 12/15/2025

Page content applies to build 10.0.0.232
