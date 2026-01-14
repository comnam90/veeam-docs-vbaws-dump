---
title: "install_unattended"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/install_unattended.html"
last_updated: "11/20/2025"
product_version: "10.0.0.232"
---


In this article

You can install or uninstall Veeam Plug-In for AWS in the unattended mode using the command line interface. The unattended mode does not require user interaction — the installation runs automatically in the background, and you do not have to respond to the installation wizard prompts. You can use it to automate processes in large-scale environments.

To install Veeam Plug-In for AWS in unattended mode, use either of the following options:

* If Veeam Plug-In for AWS is a part of Veeam Backup & Replication installation package, follow the instructions provided in the Veeam Backup & Replication User Guide, section [Installing Veeam Backup & Replication in Silent Mode](https://helpcenter.veeam.com/docs/backup/vsphere/install_vbr_answer_file.html?ver=120).
* If Veeam Plug-In for AWS is delivered as a separate .EXE file, use the instructions from this subsection.

Before You Begin

Before you start unattended installation, do the following:

1. Download the Veeam Plug-In for AWS .EXE file as described in section [Deploying Plug-In](installing_plugin.md) (steps 1–2).
2. Check compatibility of the Veeam Plug-In for AWS and Veeam Backup & Replication versions. For more information, see [System Requirements](system_requirements.md#versions).

Installation Command-Line Syntax

Open the command prompt and run the .EXE file using the following parameters:

|  |
| --- |
| %path% /silent /accepteula /acceptlicensingpolicy /acceptthirdpartylicenses /acceptrequiredsoftware [/uninstall] |

The following command-line parameters are used to run the setup file:

| Parameter | Required | Description |
| --- | --- | --- |
| %path% | Yes | Specifies a path to the installation .EXE file on the backup server or in a network shared folder. |
| /silent | Yes | Sets the user interface level to None, which means no user interaction is needed during installation. |
| /accepteula | Yes | Confirms that you accept the terms of the Veeam license agreement. |
| /acceptlicensingpolicy | Yes | Confirms that you accept the Veeam licensing policy. |
| /acceptthirdpartylicenses | Yes | Confirms that you accept the license agreement for 3rd party components that Veeam incorporates. |
| /acceptrequiredsoftware | Yes | Confirms that you accept the license agreements for each required software that Veeam will install. |
| /uninstall | No | Uninstalls the plug-in.  Example: ”AWSPlugin\_13.10.0.225.exe /silent /accepteula /acceptlicensingpolicy /acceptthirdpartylicenses /acceptrequiredsoftware /uninstall” |

Page updated 11/20/2025

Page content applies to build 10.0.0.232
