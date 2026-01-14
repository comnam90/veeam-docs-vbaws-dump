---
title: "sla_storage_remove"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/sla_storage_remove.html"
last_updated: "11/4/2025"
product_version: "10.0.0.232"
---


In this article

Veeam Backup for AWS allows you to permanently remove a policy template from the configuration database if you no longer need it:

1. Switch to the Configuration page.
2. Navigate to Policy Templates.
3. Switch to the necessary tab and select the template.
4. Click Remove.

|  |
| --- |
| Important |
| You cannot remove a template that is used by any SLA-based backup policy. [Modify the settings of all the related policies](ec2_sla_create.md) to remove references to the template — and then try removing the template again. |

[![Removing Policy Templates](images/policy_templates_remove.webp)](images/policy_templates_remove.webp "Removing Policy Templates")

Page updated 11/4/2025

Page content applies to build 10.0.0.232
