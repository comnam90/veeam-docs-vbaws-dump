---
title: "restore_item_before_you_begin"
product: "vbaws"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/restore_item_before_you_begin.html"
last_updated: "12/15/2025"
product_version: "10.0.0.232"
---


In this article

Before you start file-level recovery, consider the following limitations and prerequisites:

* Restore of files and folders is supported for FAT, FAT32, NTFS, ext2, ext3, ext4, XFS, Btrfs file systems only. For EC2 instances running Microsoft Windows OSes, Veeam Backup for AWS supports file-level recovery for basic volumes only.

* Veeam Backup for AWS does not support restore of files and folders stored on EBS volumes with Windows-native [Data Deduplication](https://learn.microsoft.com/en-us/windows-server/storage/data-deduplication/overview) enabled. To work around the issue, you can restore entire volumes, and then attach these volumes to an EC2 Windows instance with the deduplication feature enabled. To learn how to restore entire EBS volumes, see [Performing Volume Restore](restore_volume_perform.md).
* To recover files and folders of an EC2 instance from a backup that is stored in an archive backup repository, you must retrieve the archived data manually before you begin the file-level recovery operation. For more information on data retrieval, see [Retrieving EC2 Data From Archive](data_retrieval.md).

* The 443 port must be open on worker instances to allow inbound network access from the machine from which you plan to open the file-level recovery browser. To enable access for a worker instance, update the security group specified in [worker instance settings](worker_settings.md) to add an inbound rule. To learn how to add rules to security groups, see [AWS Documentation](https://docs.aws.amazon.com/vpc/latest/userguide/security-group-rules.html#adding-security-group-rules).

If you want worker instances to operate in a private network, enable the [private network deployment](enable_private_network_deployment.md) functionality and configure specific VPC endpoints for all subnets to which the worker instances will be connected. Alternatively, configure VPC endpoints for all subnets as described in section [Appendix C. Configuring Endpoints in AWS](configure_endpoints.md).

|  |
| --- |
| Tip |
| It is recommended that you run a file-level recovery test before you start a file-level recovery operation in a specific AWS Region. For more information, see [Testing Configurations for FLR](worker_settings_test.md). |

Restoring to Original Location

If you plan to perform file-level recovery to the original location, consider the following additional limitations and prerequisites:

* To perform restore to the original location, Veeam Backup for AWS deploys worker instances in the [backup account](worker_options.md#backup) and in the AWS Region where a backup repository with backed-up data resides. That is why you must specify network settings for worker instances beforehand as described in section [Adding Configurations for Backup Account](worker_add_config_backup.md).
* [For EC2 instances running Linux OS] Restore of files and folders is supported only for systemd-based distributions.
* [For EC2 instances running Windows OS] Restore of files and folders is supported only if Windows Management Framework (WMF) version 5.1 is installed on the processed instances.

* [For Linux-based EC2 instances] Python v2 or v3 with module 6 must be installed on the source instance.
* The source instance must be configured to communicate with AWS System Manager. To learn how to configure instance permissions for Systems Manager, see [AWS Documentation](https://docs.aws.amazon.com/systems-manager/latest/userguide/setup-instance-permissions.html).
* SSM Agent must be installed on the source instance. To learn how to install SSM Agent, see [AWS Documentation](https://docs.aws.amazon.com/systems-manager/latest/userguide/ssm-agent.html).

* The IAM role attached to the source EC2 instance must meet the following requirements:

1. The IAM role must be included in the instance profile. For more information on instance profiles, see [AWS Documentation](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_use_switch-role-ec2_instance-profiles.html).
2. The Amazon EC2 service must be granted permissions to assume the IAM role.

To allow the Amazon EC2 service to assume the IAM role, configure trust relationships for the role and add the following statement to the trust policy.

|  |
| --- |
| {   "Version": "2012-10-17",   "Statement": [     {       "Effect": "Allow",       "Action": "sts:AssumeRole",       "Principal": {         "Service": "ec2.amazonaws.com"       }     }   ]  } |

1. During the file-level recovery session, Veeam Backup for AWS will create a temporary IAM role in the backup account to perform data transmission using [Amazon Kinesis Data Streams](https://docs.aws.amazon.com/streams/latest/dev/introduction.html). That is why the IAM role attached to the source EC2 instance must have the permissions to assume the temporary role:

|  |
| --- |
| {     "Version": "2012-10-17",     "Statement": [         {             "Sid": "VisualEditor1",             "Effect": "Allow",             "Action": "sts:AssumeRole",             "Resource": "arn:aws:iam::<backup-account-id>:role/veeam\_rto\_<original-instance-id>"         }     ]  } |

Where the <service-account-id> is an AWS ID of the trusted [backup account](worker_options.md#backup), and <original-instance-id> is an AWS ID of the source EC2 instance.

* If the source EC2 instance operates in a private network, you must create the following VPC endpoints for the subnet to which the instance is connected:

* com.amazonaws.<region>.ec2messages
* com.amazonaws.<region>.ssm
* com.amazonaws.<region>.sqs
* com.amazonaws.<region>.kinesis-streams
* com.amazonaws.<region>.sts

To learn how to create interface VPC endpoints, see [AWS Documentation](https://docs.aws.amazon.com/vpc/latest/privatelink/create-interface-endpoint.html).

Page updated 12/15/2025

Page content applies to build 10.0.0.232
