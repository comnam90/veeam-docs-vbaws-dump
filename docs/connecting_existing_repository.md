---
title: "connecting_existing_repository"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/connecting_existing_repository.html"
last_updated: "11/30/2023"
product_version: "10.0.0.232"
---


In this article

When you connect to a backup appliance, all repositories that have already been configured on the appliance are automatically added to the backup infrastructure.

If an existing repository is not displayed under the External Repositories node or if you have recently configured a new repository on the backup appliance that is already connected to the backup server, do the following:

1. In the Veeam Backup & Replication console, open the Backup Infrastructure view.
2. Navigate to Managed Servers.
3. Select a backup appliance that manages the necessary repository and click Edit Appliance on the ribbon.

Alternatively, you can right-click the backup appliance and select Properties.

1. In the Edit Veeam Backup for AWS Appliance wizard, do the following:

1. Navigate to the Repositories step of the wizard and complete the step as described in section [Connecting to Existing Veeam Backup for AWS Appliances](connect_appliance_repo.md) (step 7).

1. Complete the Edit Veeam Backup for AWS Appliance wizard as described in section [Connecting to Existing Veeam Backup for AWS Appliances](connect_appliance.md) (steps 8-9).

Open the Backup Infrastructure view to verify that the repository is displayed under the External Repositories node.

|  |
| --- |
| Note |
| If you do not specify access keys of an IAM user for a standard backup repository, you will only be able to use the Veeam Backup & Replication console to perform [entire EC2 instance restore](restore_to_google.md) from backups stored in this repository. Moreover, information on the repository displayed in the Backup Infrastructure view under the External Repositories node will not include statistics on the amount of storage space that is currently consumed by restore points created by Veeam Backup for AWS. |

Page updated 11/30/2023

Page content applies to build 10.0.0.232
