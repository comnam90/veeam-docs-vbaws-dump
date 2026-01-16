---
title: "appliance_aws"
product: "vbaws"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/appliance_aws.html"
last_updated: "6/25/2025"
product_version: "10.0.0.232"
---


In this article

You can choose the type of the EC2 instance running Veeam Backup for AWS during the deployment, or change it later as the environment grows.

General Recommendations

The following recommendations and examples apply to the latest Veeam Backup for AWS builds.

| Instance Type | Recommended Maximum Number of Protected EC2 Instances |
| --- | --- |
| T3.medium (default - 2 vCPU, 4 GB RAM) | 1,000 |
| T3.2xlarge (medium - 8 vCPU, 32 GB RAM) | 5,000 |
| C5.9xlarge (large - 36 vCPU, 72 GB RAM) | 10,000 |

When defining the instance type and amount of RAM required for proper functioning of the backup appliance, take into account the following:

* The average amount of RAM consumed in the idle state (approximately 1.5 GB).
* 5% of the total backup appliance RAM required for the Veeam Backup for AWS Web UI and REST API service.
* The maximum amount of RAM consumed by running backup policies. For more information, see [Backup Policies](policies_aws.md).

The RAM consumed by a backup policy depends on the data protection scenario.

| Backup Policy Configuration | RAM Utilization (Default) | Additional RAM (per Workload) |
| --- | --- | --- |
| EC2 Backup Policy | | |
| Snapshots only | 105 MB | 1 MB |
| Snapshots and snapshot replicas | 130 MB | 1 MB |
| Snapshots and backups | 170 MB | 3 MB |
| Snapshots, snapshot replicas and backups | 170 MB | 3 MB |
| RDS Backup Policy | | |
| Snapshots only | 105 MB | 1 MB |
| Snapshots and snapshot replicas | 110 MB | 1 MB |
| Snapshots and backups | 180 MB | 3 MB |
| Snapshots, snapshot replicas and backups | 185 MB | 3 MB |
| EFS Backup Policy | | |
| Snapshots only | 105 MB | 3 MB |
| Snapshots and backup copies | 120 MB | 3 MB |
| Snapshots and indexing | 165 MB | 3 MB |
| Snapshots, backup copies and indexing | 165 MB | 3 MB |
| FSx Backup Policy | | |
| Backups only | 110 MB | 3 MB |
| Backups and backup copies | 125 MB | 3 MB |
| DynamoDB Backup Policy | | |
| Snapshots only | 110 MB | 3 MB |
| Snapshots and backup copies | 125 MB | 3 MB |
| Redshift Backup Policy | | |
| Backups only | 110 MB | 3 MB |

Note that these values are provided for demonstration purposes only. For production environments, it is recommended that you allocate an additional margin of 20% RAM.

RAM Sizing Examples

Consider the following example. You configure a number of backup policies to protect your workloads by regularly creating snapshots, snapshot replicas and backups. In this case, we advise to allocate minimum 150 MB per 1 policy.

The amount of RAM utilized by policies running on a backup appliance (Utilized RAM) depends on the total amount of RAM allocated to the backup appliance, the number of configured backup policies and the number of workloads protected by one policy. However, consider that the actual amount of RAM available for policy execution (Free RAM) will also be affected by the OS and Veeam services operation.

| Total RAM | Number of Backup Policies | Workloads per Backup Policy | Utilized RAM1 | Free RAM2 |
| --- | --- | --- | --- | --- |
| 4 GB | 5 | 50 | (150 + (50 \* 3)) \* 5  = ~ 1.5 GB | 4 GB - 1.5 GB - 4 GB \* 0.05  = 2.3 GB |
| 8 GB | 20 | 50 | (150 + (50 \* 3)) \* 20  = ~ 6 GB | 8 GB - 1.5 GB - 8 GB \* 0.05  = 6.1 GB |
| 16 GB | 50 | 30 | (150 + (30 \* 3)) \* 50  = ~ 12 GB | 16 GB - 1.5 GB - 16 GB \* 0.05  = 13.7 GB |
| 32 GB | 75 | 75 | (150 + (75 \* 3)) \* 75  = ~ 28.2 GB | 32 GB - 1.5 GB - 32 GB \* 0.05  = 28.9 GB |
| 72 GB | 250 | 25 | (150 + (25 \* 3)) \* 250  = ~ 56.25 GB | 72 GB - 1.5 GB - 72 GB \* 0.05  = 66.9 GB |

1The table shows the maximum amount of RAM utilization when all backup policies run at the same time.

2Additional RAM required for any other software must be calculated separately.

CPU Sizing Examples

| Amount of vCPUs | Number of Snapshots Taken Simultaneously |
| --- | --- |
| EC2 CPU | |
| 2 vCPU | < 300 |
| 4 vCPU | < 600 |
| 8 vCPU | < 1,600 |
| 16 vCPU | > 1,600 |
| RDS CPU | |
| 2 vCPU | < 300 |
| 4 vCPU | < 800 |
| 8 vCPU | < 1,600 |
| 16 vCPU | > 1,600 |
| EFS CPU | |
| > 4 vCPU | > 25 |
| DynamoDB CPU | |
| > 4 vCPU | > 100 |

\*The examples apply only to workloads protected by snapshots and snapshot replicas, as the backup process is performed by worker instances.

Configuration Restore Recommendations

The following is recommended for large-scale deployments.

* The root EBS volume attached to the backup appliance must have at least twice as much free space as the size of the configuration backup file. If the backup file grows too large, you can increase the volume size as described in [AWS Documentation](https://docs.aws.amazon.com/AWSEC2/latest/WindowsGuide/ebs-modify-volume.html). Alternatively, open a [support case](https://helpcenter.veeam.com/docs/vbaws/guide/logs.html) to remove the unnecessary data from the configuration database.
* The EBS volume where Veeam Backup for AWS stores its configuration database must have at least twice as much free space as the size of the database. During configuration restore, Veeam Backup for AWS first creates the restored database and then deletes the original one.

Logging Recommendations

You can modify the following logging options in the configuration file /etc/veeam/awsbackup/config.ini:

|  |
| --- |
| [LogOptions] |

If the log files grow too large, you can remove them from the /mnt/vcb-storage/logs or /var/log/veeam folder, or open a [support case](https://helpcenter.veeam.com/docs/vbaws/guide/logs.html) to remove the unnecessary data.

Veeam Backup & Replication Integration

When you connect a backup appliance to the backup infrastructure, its backup policies, cloud-native snapshots, image-level backups, backup repositories and sessions are imported into the Veeam Backup & Replication database.

Time Consumption

When you connect an existing backup appliance to the backup infrastructure, the integration process includes the following steps:

* Retrieving data from the backup appliance.
* Saving the retrieved data to the Veeam Backup & Replication database.

| Protected Workloads | Snapshots | Backups | Backup Policy Sessions | Workload Processing Sessions | Time Consumption |
| --- | --- | --- | --- | --- | --- |
| 1,000 | 100,000 | 100,000 | 8,000 | 400,000 | about 2 hours\* |
| 2,000 | 200,000 | 200,000 | 16,000 | 800,000 | about 3 hours\* |
| 4,000 | 400,000 | 400,000 | 32,000 | 1,600,000 | about 5 hours\* |

\*The results were obtained when testing the backup appliance (c5.4xlarge, 16-core CPU, 32 GB RAM), the Veeam Backup & Replication server (PGSQL, 16-core CPU, 16 GB RAM) and Veeam Backup & Replication server (MSSQL, 16-core CPU, 16 GB RAM) and are approximate.

|  |
| --- |
| Note |
| The process of synchronizing data between the backup appliance and Veeam Backup & Replication database runs every 2 minutes after you add the backup appliance to the backup infrastructure. Creating new backup policies, updating policy settings, running backup and restore sessions may also trigger the synchronization process. |

Page updated 6/25/2025

Page content applies to build 10.0.0.232
