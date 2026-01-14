---
title: "role_permissions_backup_vpc"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/role_permissions_backup_vpc.html"
last_updated: "2/10/2025"
product_version: "10.0.0.232"
---


In this article

Veeam Backup for AWS uses VPC Configuration Backup IAM roles to perform the following operations:

* To enumerate resources added to a backup policy.
* To create VPC configuration backups of AWS Regions.

* To create backup copies, and so on.

To perform these operations, IAM roles specified in the [organization settings](organization_add_settings.md) or in the [VPC configuration backup policy settings](vpc_policy_regions.md) must meet the following requirements:

1. The backup appliance must be granted permissions to assume the IAM roles. For more information on the requirements for adding IAM roles, see [Before You Begin](byb_roles.md).

1. The IAM roles must be granted the following permissions:

|  |
| --- |
| {     "Version": "2012-10-17",     "Statement": [         {             "Effect": "Allow",             "Action": [                 "ec2:DescribeAddresses",                 "ec2:DescribeClientVpnAuthorizationRules",                 "ec2:DescribeClientVpnEndpoints",                 "ec2:DescribeClientVpnRoutes",                 "ec2:DescribeClientVpnTargetNetworks",                 "ec2:DescribeCustomerGateways",                 "ec2:DescribeDhcpOptions",                 "ec2:DescribeEgressOnlyInternetGateways",                 "ec2:DescribeInstances",                 "ec2:DescribeInternetGateways",                 "ec2:DescribeManagedPrefixLists",                 "ec2:DescribeNatGateways",                 "ec2:DescribeNetworkAcls",                 "ec2:DescribeNetworkInterfaces",                 "ec2:DescribeRegions",                 "ec2:DescribeRouteTables",                 "ec2:DescribeSecurityGroups",                 "ec2:DescribeSubnets",                 "ec2:DescribeTransitGatewayAttachments",                 "ec2:DescribeTransitGatewayMulticastDomains",                 "ec2:DescribeTransitGatewayPeeringAttachments",                 "ec2:DescribeTransitGatewayRouteTables",                 "ec2:DescribeTransitGatewayVpcAttachments",                 "ec2:DescribeTransitGateways",                 "ec2:DescribeVpcAttribute",                 "ec2:DescribeVpcEndpointServiceConfigurations",                 "ec2:DescribeVpcEndpoints",                 "ec2:DescribeVpcPeeringConnections",                 "ec2:DescribeVpcs",                 "ec2:DescribeVpnConnections",                 "ec2:DescribeVpnGateways",                 "ec2:GetManagedPrefixListEntries",                 "ec2:GetTransitGatewayPrefixListReferences",                 "ec2:GetTransitGatewayRouteTableAssociations",                 "ec2:GetTransitGatewayRouteTablePropagations",                 "ec2:SearchTransitGatewayRoutes",                 "elasticloadbalancing:DescribeListeners",                 "elasticloadbalancing:DescribeLoadBalancers",                 "elasticloadbalancing:DescribeTags",                 "elasticloadbalancing:DescribeTargetGroups",                 "elasticloadbalancing:DescribeTargetHealth",                 "iam:GetContextKeysForPrincipalPolicy",                 "iam:ListAccountAliases",                 "iam:SimulatePrincipalPolicy",                 "ram:GetResourceShares",                 "ram:ListPrincipals",                 "ram:ListResourceSharePermissions",                 "ram:ListResources"             ],             "Resource": "\*"         }     ]  } |

To learn how to create IAM roles and assign them the required permissions, see [Appendix A. Creating IAM Roles in AWS](create_iam_policy_role.md).

Page updated 2/10/2025

Page content applies to build 10.0.0.232
