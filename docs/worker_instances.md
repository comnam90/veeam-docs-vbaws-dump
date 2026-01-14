---
title: "worker_instances"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/worker_instances.html"
last_updated: "12/9/2025"
product_version: "10.0.0.232"
---


In this article

To perform most data protection and disaster recovery operations (such as creating EC2 and RDS image-level backups, restoring backed-up data, EFS indexing or retention tasks), Veeam Backup for AWS uses worker instances. Worker instances are temporary Linux-based EC2 instances that are responsible for the interaction between the backup appliance, AWS services and other Veeam Backup for AWS components. Worker instances process backup workload and distribute backup traffic when transferring data to backup repositories.

Veeam Backup for AWS automatically deploys a worker instance in Amazon EC2 for the duration of a backup, restore or retention operation and removes it immediately as soon as the operation completes. For example, Veeam Backup for AWS deploys one worker instance per each AWS resource specified in a EC2 backup policy.

|  |
| --- |
| Note |
| The location of each deployed worker instance depends on the operation being performed and on the resource being processed. For more information, see sections [Worker Deployment Options](worker_options.md) and [Worker Instance Locations](workers_location.md#regions). |

Worker Instance Components

Worker instances use the following components:

* Veeam Data Mover — a service that performs data processing tasks. During backup, Veeam Data Mover retrieves data of protected AWS resources and transfers it to backup repositories. During restore, Veeam Data Mover transfers backed-up data from backup repositories to the target location.

* File-level recovery browser — a web service that allows you to find and save files and folders of a backed-up EC2 instance to the local machine or to the original location. The file-level recovery browser is installed automatically on every worker instance that is deployed for file-level recovery.

For more information on recovering files of EC2 instances using the file-level recovery browser, see [Performing File-Level Recovery](restore_item_perform.md).

Security Certificates for Worker Instances

During the file-level recovery process, Veeam Backup for AWS uses self-signed TLS certificates to establish secure communication between the web browser on the local machine and the file-level recovery browser on the worker instance. A self-signed certificate is generated automatically on the worker instance when the restore session starts.

Worker Instance Network Settings

To deploy worker instances, Veeam Backup for AWS uses either the default or the [most appropriate network settings](workers_location.md) of AWS Regions. However, you can add specific worker configurations as described in section [Managing Worker Configurations](worker_settings.md).

Required Ports

The following network ports must be open to ensure proper operation of worker instances in Veeam Backup for AWS architecture:

| From | To | Protocol | Port | Notes |
| --- | --- | --- | --- | --- |
| Web browser (local machine) | Worker instances | TCP/HTTPS | 443 | Required to access the file-level recovery browser running on a worker instance during the file-level recovery process. |
| Worker instances | [AWS services](system_requirements_aws_services.md) | TCP/HTTPS | 443 | Required to perform data protection and disaster recovery operations. |
| TCP/NFS | 2049 | Required to perform EFS indexing. |

Required AWS Services

To perform backup and restore operations, worker instances must have outbound internet access to the following AWS services:

* [AWS Systems Manager (SSM)](https://docs.aws.amazon.com/general/latest/gr/ssm.html), including access to the ec2messages and ssmmessages endpoints
* [Amazon Simple Queue Service (SQS)](https://docs.aws.amazon.com/general/latest/gr/sqs-service.html)

* [Amazon Simple Storage Service (S3)](https://docs.aws.amazon.com/general/latest/gr/s3.html)

* [Amazon Elastic Block Store (EBS)](https://docs.aws.amazon.com/general/latest/gr/ebs-service.html)
* [Amazon Kinesis Data Streams](https://docs.aws.amazon.com/general/latest/gr/ak.html)

If you want worker instances to operate in a private environment, you must enable the private network deployment functionality and configure VPC endpoints for all subnets to which the worker instances will be connected. Otherwise, the instances will not be able to access all the listed services. For more information, see [Private Network Deployment](private_network_deployment.md#configure_private_deployment).

How To Configure Worker Instance Settings

You can configure the following worker instance settings:

1. [Choose whether you want to deploy worker instances in the backup or production accounts](worker_settings.md).
2. [Specify groups of network settings that Veeam Backup for AWS will use to deploy worker instances in specific AWS Regions](worker_settings.md).
3. [Specify instance types that Veeam Backup for AWS will use to deploy worker instances in specific AWS Regions](worker_profiles.md).
4. [Assign AWS tags to worker instances to help you differentiate the instances](worker_tags.md).

Page updated 12/9/2025

Page content applies to build 10.0.0.232
