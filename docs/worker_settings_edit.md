---
title: "worker_settings_edit"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/worker_settings_edit.html"
last_updated: "7/4/2025"
product_version: "10.0.0.232"
---


In this article

For each worker configuration, you can modify settings specified while adding the worker configuration to Veeam Backup for AWS:

1. Switch to the Configuration page.

1. Navigate to Workers > Network.
2. Switch to the necessary tab.
3. Select the worker configuration and click Edit.
4. Complete the Edit Worker Configuration wizard:

1. To change the VPC network and subnet to which the related worker instances are connected, and the security group associated with the instances, follow the instructions provided in section [Adding Configurations for Backup Account](worker_configurations_backup.md) (step 3) or in section [Adding Configurations for Production Accounts](worker_configurations_prod.md#region) (step 3).
2. To specify another key and value of the AWS tag associated with the security group, VPC network and subnet to which worker instances are connected, follow the instructions provided in section [Adding Configurations for Production Accounts](worker_configurations_prod.md#region) (step 3).
3. At the Summary step of the wizard, review configuration information and click Finish to confirm the changes.

|  |
| --- |
| Note |
| If any worker instances are currently deployed in the selected AWS Region, the changes will be applied only when Veeam Backup for AWS removes the instances from infrastructure (that is, when the running backup or restore process completes). |

[![Editing Worker Configuration](images/edit_worker_settings.webp)](images/edit_worker_settings.webp "Editing Worker Configuration")

Page updated 7/4/2025

Page content applies to build 10.0.0.232
