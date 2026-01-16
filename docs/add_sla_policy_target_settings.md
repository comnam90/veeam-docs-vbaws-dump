---
title: "add_sla_policy_target_settings"
product: "vbaws"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/add_sla_policy_target_settings.html"
last_updated: "1/8/2026"
product_version: "10.0.0.232"
---


In this article

At the Protection Settings step of the wizard, select an SLA and a storage template that will be assigned to the policy:

1. From the SLA template list, select an SLA template whose snapshot, snapshot replica, backup and archived backup settings the policy will use to protect EC2 instances specified at [step 4](add_sla_policy_source_settings.md#resources) of the wizard.

For an SLA template to be displayed in the list, it must be added to Veeam Backup for AWS as described in section [Adding SLA Templates](sla_add.md). If you have not added the necessary SLA template to Veeam Backup for AWS beforehand, you can do it without closing the SLA-Based Policy wizard. To do that, click Add and complete the Add SLA Template wizard.

|  |
| --- |
| Note |
| If you create the backup policy during active data protection windows configured for the selected SLA template, Veeam Backup for AWS will run the policy immediately after it is created. |

1. From the Storage template list, select a storage template whose target location settings the policy will use to store backed-up data.

For a storage template to be displayed in the list, it must be added to Veeam Backup for AWS as described in section [Adding Storage Templates](storage_add.md). If you have not added the necessary storage template to Veeam Backup for AWS beforehand, you can do it without closing the SLA-Based Policy wizard. To do that, click Add and complete the Add Storage Template wizard.

|  |
| --- |
| Important |
| The backup and archived backup settings configured for the selected SLA template must match the target location settings configured for the selected storage template. That is, if backups are configured for the selected SLA template, make sure you configured backup location settings for the storage template, and if archive backups are configured for the selected SLA template, make sure you configured archived backup location settings for the storage template. |

[![Creating SLA-Based EC2 Policy](images/add_sla_policy_templates.webp)](images/add_sla_policy_templates.webp "Creating SLA-Based EC2 Policy")

Page updated 1/8/2026

Page content applies to build 10.0.0.232
