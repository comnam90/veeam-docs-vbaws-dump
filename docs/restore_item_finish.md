---
title: "restore_item_finish"
product: "vbaws"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/restore_item_finish.html"
last_updated: "9/29/2025"
product_version: "10.0.0.232"
---


In this article

At the Summary step of the wizard, review summary information and click Finish.

As soon as you click Finish, Veeam Backup for AWS will close the File-level Recovery wizard, start a recovery session and display the FLR Running Sessions window. During the recovery session, Veeam Backup for AWS will deploy a worker instance and attach EBS volumes of the processed EC2 instance to it.

|  |
| --- |
| Tip |
| If you accidentally close the FLR Running Sessions window, navigate to Protected Data > EC2 and click the link in the File-Level Recovery URL column to open the window again. |

In the FLR Running Sessions window you can track the progress of the recovery session. As soon as worker instance is deployed, Veeam Backup for AWS will display a link to the file-level recovery browser in the URL column of the window. You can use the link in either of the following ways:

* Click the link to open the file-level recovery browser on your local machine while the recovery session is running.
* Copy the link, close the FLR Running Sessions window and open the file-level recovery browser on another machine.

|  |
| --- |
| Important |
| When you click Copy URL, Veeam Backup for AWS copies the following information to the clipboard:   * A link to the file-level recovery browser includes a public DNS name or private IP address of the worker instance hosting the browser and authentication information used to access the browser. * A thumbprint of a TLS certificate installed on the worker instance hosting the file-level recovery browser.   To avoid a man-in-the-middle attack, before you start recovering files and folders, check that the certificate thumbprint displayed in the web browser from which you access the file-level recovery browser matches the provided certificate thumbprint. |

[![Restoring EC2 Files and Folders](images/restore_item_flr_session_view.webp)](images/restore_item_flr_session_view.webp "Restoring EC2 Files and Folders")

Page updated 9/29/2025

Page content applies to build 10.0.0.232
