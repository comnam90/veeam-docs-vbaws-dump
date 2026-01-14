---
title: "restore_item_stop"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/restore_item_stop.html"
last_updated: "9/29/2025"
product_version: "10.0.0.232"
---


In this article

After you finish working with the file-level recovery browser, it is recommended that you stop the recovery session so that Veeam Backup for AWS can unmount and detach EBS volumes of the processed EC2 instance from the worker instance and remove the worker instance from Amazon EC2.

To stop the recovery session, click Stop recovery session in the FLR Running Sessions window. If you do not perform any actions in the file-level recovery browser for 30 minutes, Veeam Backup for AWS will stop the recovery session automatically.

|  |
| --- |
| Tip |
| If you accidentally close the FLR Running Sessions window, navigate to Protected Data > EC2 and click the link in the File-Level Recovery URL column to open the window again. |

[![Restoring EC2 Files and Folders](images/restore_item_flr_session_stop.webp)](images/restore_item_flr_session_stop.webp "Restoring EC2 Files and Folders")

Page updated 9/29/2025

Page content applies to build 10.0.0.232
