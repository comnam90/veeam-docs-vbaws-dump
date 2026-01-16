---
title: "accounts_database"
product: "vbaws"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/accounts_database.html"
last_updated: "8/20/2025"
product_version: "10.0.0.232"
---


In this article

To allow Veeam Backup for AWS to authenticate against PostgreSQL DB instances protected by backup policies, you must specify credentials of database accounts that will be used to access the databases when performing [image-level backup](add_policy_processing_settings_rds.md) and [restore operations](restore_rds_database_settings.md).

|  |
| --- |
| Note |
| After you upgrade Veeam Backup for AWS to version 10, the list of database accounts will be populated with policy credentials that were previously used to access protected databases. |

In This Section

* [Adding Database Accounts](accounts_database_create.md)
* [Editing Database Accounts](accounts_database_edit.md)
* [Removing Database Accounts](accounts_database_remove.md)

Page updated 8/20/2025

Page content applies to build 10.0.0.232
