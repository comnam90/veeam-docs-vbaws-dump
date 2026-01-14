---
title: "overview_ec2"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/overview_ec2.html"
last_updated: "12/12/2025"
product_version: "10.0.0.232"
---


In this article

With Veeam Backup for AWS, you can perform the following operations to protect EC2 instances:

* Create cloud-native snapshots of EC2 instances and replicate these snapshots to any AWS Region within any AWS account.

A cloud-native snapshot of an EC2 instance includes point-in-time snapshots of EBS volumes attached to the processed instance. Snapshots of EBS volumes (also referred to as EBS snapshots) are taken using native [AWS capabilities](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EBSSnapshots.html).

* Create transactionally consistent backups using application-aware processing for Windows EC2 instances running VSS-aware applications.
* Create transactionally consistent snapshots using custom scripts to quiesce running applications for all processed EC2 instances.
* Create image-level backups of EC2 instances and keep them in Amazon Simple Storage Service (Amazon S3) for high availability, cost-effective and long-term storage.

An image-level backup captures the whole image of the processed EC2 instance (including instance configuration, OS data, application data and so on) at a specific point in time.

Backup Policies

To produce cloud-native snapshots and image-level backups of EC2 instances, Veeam Backup for AWS runs backup policies of the following types:

* Schedule-based backup policies

These policies define the way backup operations are performed: what data to back up, where to store backups, when to start the backup process, and so on. When you configure a schedule-based backup policy, your data is protected according to a specific backup schedule (at an exact date and time).

One schedule-based backup policy allows you to use a single repository for all protected AWS Regions. After Veeam Backup for AWS finishes running a schedule-based backup policy, you can [track the status of data protection](reporting.md) for each EC2 instance included in the policy in terms of whether the backup operation completed successfully.

|  |
| --- |
| Note |
| The start time of each schedule-based backup policy is not region specific — these policies run according to the time zone of the backup appliance. |

* SLA-based backup policies

These policies automate the way backup operations are performed: what data to back up, how frequently to run the backup process, what region-specific repositories to use to store backups, how many restore points should be created in time to meet SLA requirements, and so on. When you configure an SLA-based backup policy, your data is protected according to a periodic backup schedule (regularly, within a specific time interval) to help balance the load on your production environment.

One SLA-based backup policy allows you to use a separate repository for each protected AWS Region. After Veeam Backup for AWS finishes running an SLA-based backup policy, you can [track the status of data protection](sla_monitoring.md) for each EC2 instance included in the policy in terms of whether the target SLA was met (in addition to monitoring the backup operation status).

|  |
| --- |
| Note |
| The start time of each SLA-based backup policy is adjusted to the time zone of the AWS Regions protected by this policy. |

Veeam Backup for AWS does not install agent software inside instances to back up EC2 instance data — it uses native AWS capabilities instead. During every backup session, Veeam Backup for AWS creates a cloud-native snapshot for each EC2 instance added to a backup policy. The cloud-native snapshot is further used to create a snapshot replica in another AWS Region or another AWS account and an image-level backup of the instance. For more information on how EC2 instance backup works, see [EC2 Backup](backup_hiw_ec2.md).

Worker Deployment Considerations

Before you start creating EC2 backup policies and performing EC2 image-level backup, consider the following:

* By default, Veeam Backup for AWS deploys worker instances in the same AWS account to which the backup appliance belongs (that is, the default backup account) and employs the worker deployment role (service IAM role). However, you can also instruct Veeam Backup for AWS to deploy worker instances in production accounts. For more information, see [Worker Deployment Options](worker_options.md#production).

* To minimize cross-region traffic charges, Veeam Backup for AWS deploys worker instances in specific locations that depend on the data protection or disaster recovery operation. For more information, see [Worker Instance Locations](workers_location.md).

* By default, Veeam Backup for AWS automatically chooses the default network settings of AWS Regions (if any) to deploy the worker instances. However, you can add worker configurations to define network settings for each region in which the worker instances will be deployed. For more information, see [Managing Worker Configurations](worker_settings.md).

How To Protect EC2 Instances

To create an EC2 backup policy, perform the following steps:

1. [Check limitations and prerequisites](limitations.md#backup_ec2).
2. [Specify IAM roles to access AWS services and resources](accounts_iam_roles.md).
3. [[Optional] Add backup repositories to store backed-up data](repositories.md).
4. [[Optional] Configure worker instance settings to deploy workers while processing EC2 instance data](workers.md).
5. [[Optional] Configure global retention settings for obsolete snapshots and session records](retention_settings.md).
6. [[Optional] Configure email notification settings for automated delivery of backup policy results and daily reports](email_settings.md).
7. Do either of the following:

* To create a schedule-based backup policy, [complete the Add EC2 Policy wizard](policies_create.md).
* To create an SLA-based backup policy:

1. [Complete the Add SLA Template wizard](sla_add.md).
2. [Complete the Add Storage Template wizard](storage_add.md).
3. [Complete the SLA-Based Policy wizard](ec2_sla_create.md).

Related Topics

[EC2 Restore](restore_hiw_ec2.md)

Page updated 12/12/2025

Page content applies to build 10.0.0.232
