---
title: "add_policy_finish_redshift_serverless"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/add_policy_finish_redshift_serverless.html"
last_updated: "9/23/2025"
product_version: "10.0.0.232"
---


In this article

At the Summary step of the wizard, it is recommended that you run the backup policy configuration check before you click Finish — to do that, click Test Configuration. Depending on the option selected at [step 3](add_policy_scope_redshift_serverless.md) of the wizard, the following will happen:

* If you have selected the Account option, the configuration check will verify whether IAM roles specified in the backup policy settings have all the permissions required to perform the backup operation.
* If you have selected the Organization option, the configuration check will verify whether IAM roles specified in the [organization settings](organization_add_settings.md) have all the permissions required to perform the backup operation.

Veeam Backup for AWS will display the Test policy configuration window where you can track the progress and view the results of the configuration check. If some permissions of any IAM role are missing or if the policy settings are not configured properly, the check will complete with errors. You can grant the missing permissions either in the Veeam Backup for AWS Web UI (for IAM roles specified in the backup policy settings) as described in section [Checking IAM Role Permissions](iam_roles_check.md), or in the AWS Management Console (for IAM roles specified in the organization settings) as described in [Appendix B. Creating IAM Policies in AWS](create_iam_policy.md).

|  |
| --- |
| Tip |
| To help you grant missing permissions in the AWS Management Console, Veeam Backup for AWS allows you to download the full list of these permissions as a single JSON policy document. To do that, click Export Missing Permissions. |

[![Creating Redshift Serverless Backup Policy](images/backup_add_finish_redshift_serverless.webp)](images/backup_add_finish_redshift_serverless.webp "Creating Redshift Serverless Backup Policy")

Page updated 9/23/2025

Page content applies to build 10.0.0.232
