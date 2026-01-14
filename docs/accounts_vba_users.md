---
title: "accounts_vba_users"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/accounts_vba_users.html"
last_updated: "10/24/2025"
product_version: "10.0.0.232"
---


In this article

Veeam Backup for AWS controls access to its functionality with the help of user roles. A role defines what operations users can perform and what range of data is available to them in Veeam Backup for AWS.

There are 4 user roles that you can assign to users working with Veeam Backup for AWS. Actions a user can perform depend on the role.

* Portal Administrator — can perform all configuration actions, and can also act as a Portal Operator and Restore Operator.
* Portal Operator — can create and edit backup policies, perform backup and restore operations, manage protected data and track session statistics.
* Restore Operator — can only perform restore operations and track session statistics.
* Read-Only User — can only view backup policies, monitor protected data and track session statistics.

|  |
| --- |
| Important |
| * The list of portal users may display user accounts with the Company Administrator role assigned — these accounts are intended to be used for the integration of Veeam Backup for AWS and Veeam Service Provider Console, and are created using the [Veeam Service Provider Console plug-in](https://helpcenter.veeam.com/docs/vac/provider_admin/integration_clouds.html?ver=70). It is not recommended that you perform any actions with these users. * Note that users with the Company Administrator role assigned have full access to AWS Organizations and can retrieve the organization structure. |

The following table describes the functionality available to users with different roles in the Veeam Backup for AWS UI.

| Tab | Functionality | Portal Administrator | Portal Operator | Restore Operator | Read-Only User |
| --- | --- | --- | --- | --- | --- |
| Overview | Dashboard | Full | Full | N/A | Full |
| Resources | Infrastructure | Full | Full | N/A | N/A |
| Policies | Backup policies | Full | Full | N/A | Read only |
| Backup repositories | Full | Full | N/A | Read only |
| Protected Data | Restore | Full | Full | Full | N/A |
| File-level recovery | Full | Full | Read only | N/A |
| Remove | Full | Full | N/A | N/A |
| Sessions | Session log | Full | Full | Full | Full |
| Stop session execution | Full | Full | N/A | N/A |
| Configuration | | | | |  |
| Accounts | IAM roles, SMTP accounts, Portal Users | Full | N/A | N/A | N/A |
| Repositories | Backup repositories | Full | N/A | N/A | N/A |
| Workers | Worker instances | Full | N/A | N/A | N/A |
| Settings | General settings | Full | N/A | N/A | N/A |
| Licensing | Licensing | Full | N/A | N/A | N/A |
| Support Information | Updates and logs | Full | N/A | N/A | N/A |

In This Section

* [Adding User Accounts](accounts_vba_users_create.md)
* [Editing User Account Settings](accounts_vba_users_manage.md)
* [Changing User Passwords](accounts_vba_users_password.md)
* [Enabling Multi-Factor Authentication](accounts_vba_users_mfa.md)

Page updated 10/24/2025

Page content applies to build 10.0.0.232
