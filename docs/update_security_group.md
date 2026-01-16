---
title: "update_security_group"
product: "vbaws"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/update_security_group.html"
last_updated: "10/10/2025"
product_version: "10.0.0.232"
---


In this article

To allow inbound traffic to the backup appliance from the on-premises network, update the security group for the appliance VPC:

1. In the Amazon VPC console, navigate to Security > Security Groups.
2. In the Security Group list, choose the default security group and click Actions > Edit Inbound Rules.
3. In the Edit inbound rules wizard, click Add rule, add a new inbound rule for the SSH, RDP and ICMP protocols, and click Save rules.

To learn how to add security group rules, see [AWS Documentation](https://docs.aws.amazon.com/vpc/latest/userguide/security-group-rules.html#working-with-security-group-rules).

Page updated 10/10/2025

Page content applies to build 10.0.0.232
