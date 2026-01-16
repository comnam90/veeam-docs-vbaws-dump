---
title: "workers"
product: "vbaws"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/workers.html"
last_updated: "1/5/2026"
product_version: "10.0.0.232"
---


In this article

To perform most data protection and disaster recovery operations (such as creating and removing EC2 and RDS image-level backups, restoring backed-up data, EFS indexing), Veeam Backup for AWS uses worker instances. Worker instances are temporary Linux-based EC2 instances that are responsible for the interaction between the backup appliance and other Veeam Backup for AWS components. Worker instances process backup workload and distribute backup traffic when transferring data to backup repositories.

Each worker instance is deployed in a specific AWS Region for the duration of the backup, restore and retention process. AWS Regions in which Veeam Backup for AWS deploys worker instances to perform operations are predefined and described in section [Worker Instance Locations](workers_location.md). However you can choose whether you want Veeam Backup for AWS to deploy worker instances in the backup account or in production AWS accounts, specify network settings and instance types that will be used to deploy worker instances. For more information on AWS accounts in which Veeam Backup for AWS deploys worker instances, see [Worker Deployment Options](worker_options.md).

|  |
| --- |
| Note |
| You can tell worker instances from other EC2 instances running in your environment by their names — all worker instances deployed by Veeam Backup for AWS to perform backup and restore operations have the same name — VBA\_Worker, all worker instances deployed by Veeam Backup for AWS to perform EFS indexing have the same name — EFS\_Worker. |

In This Section

* [Managing Worker Configurations](worker_settings.md)
* [Managing Worker Profiles](worker_profiles.md)
* [Adding Worker Tags](worker_tags.md)

Page updated 1/5/2026

Page content applies to build 10.0.0.232
