---
title: "accounts_smtp_create"
product: "vbaws"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/accounts_smtp_create.html"
last_updated: "7/25/2025"
product_version: "10.0.0.232"
---


In this article

To add an account that will be used to connect to an SMTP server, do the following:

1. Switch to the Configuration page.
2. Navigate to Accounts > SMTP Accounts.
3. Click Add.

Complete the Add Account wizard.

1. At the Account Name step of the wizard, specify a name and description for the SMTP account. The name must be unique in Veeam Backup for AWS and the length of the name must not exceed 255 characters. The description length must not exceed 255 characters.
2. At the Account step of the wizard, specify credentials of a user account that has permissions to access the SMTP server. Veeam Backup for AWS will use the specified credentials to authenticate against the SMTP server.
3. At the Summary step of the wizard, review summary information and click Finish.

[![Adding SMTP Account](images/accounts_smtp_finish.webp)](images/accounts_smtp_finish.webp "Adding SMTP Account")

Page updated 7/25/2025

Page content applies to build 10.0.0.232
