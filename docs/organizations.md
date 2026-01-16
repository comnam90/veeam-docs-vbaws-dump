---
title: "organizations"
product: "vbaws"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/organizations.html"
last_updated: "5/30/2025"
product_version: "10.0.0.232"
---


In this article

Veeam Backup for AWS allows you to protect AWS resources that belong to AWS accounts within AWS Organizations. To ensure flexibility in data protection, you can provide Veeam Backup for AWS full or limited access to account resources across organizational units.

How To Protect Resources Within AWS Organizations

To be able to perform data protection operations with AWS resources within an AWS Organization, perform the following steps:

1. [Check limitations and prerequisites](limitations.md#organizations).
2. [Create at least 2 IAM role templates](organization_template_add.md) that will help you configure IAM roles whose permissions will be used to perform the following actions:

* Organization rescan IAM role — permissions of this role will be used to collect information on the organization. Note that you will then have to create the role in the AWS account that is used to manage the organization (that is, the [management account](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_getting-started_concepts.html#management-account) or a [delegated administrator account](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_getting-started_concepts.html#delegated-admin)).
* Backup and restore IAM role — permissions of this role will be used to perform backup and restore operations with resources of the organization. Note that you will then have to create the role in each AWS account that contains resources you plan to protect within the organization.
* [Optional] Production worker IAM role — permissions of this role will be used to communicate with worker instances deployed in production accounts. The role will be attached to the worker instances to index EFS file systems, and to perform operations with EC2 and RDS resources within the AWS Organization. Note that you will then have to create the role in each AWS account that contains resources you plan to protect within the organization.

As soon as you create the templates, Veeam Backup for AWS will export them to your workstation as .CFORM or .JSON files.

1. Create the necessary IAM roles in AWS:

* For templates in the CloudFormation format, upload the files to the AWS CloudFormation service and use these files to create the necessary IAM roles automatically, as described in [AWS Documentation](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/what-is-cfnstacksets.html).
* For templates in the JSON format, use the files to create IAM policies in the IAM console and attach the policies to the necessary IAM roles manually, as described in [Appendix A. Creating IAM Roles in AWS](create_iam_policy_role.md) and [Appendix B. Creating IAM Policies in AWS](create_iam_policy.md).

1. [Add the Organization rescan IAM role to Veeam Backup for AWS](iam_roles_add.md).
2. [Add the AWS Organization to Veeam Backup for AWS](organizations_add.md). You will be able to choose whether you want to protect resources across the entire organization or across a limited scopes of organizational units.
3. [[Optional] Configure worker instance settings to deploy workers while indexing EFS file systems and processing EC2 and DB instance data](workers.md).
4. [Create a backup policy and specify the AWS Organization as the data protection scope](performing_backup_web_ui.md). You will be able to protect either the entire organization or a limited scope of organizational units.

|  |
| --- |
| Note |
| To learn how to perform disaster recovery operations with AWS resources within protected AWS Organizations, see [Performing Restore](recovery.md). |

Page updated 5/30/2025

Page content applies to build 10.0.0.232
