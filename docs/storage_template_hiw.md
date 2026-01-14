---
title: "storage_template_hiw"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/storage_template_hiw.html"
last_updated: "9/3/2025"
product_version: "10.0.0.232"
---


In this article

A storage template is a collection of settings that allows you to define target locations for backups and archived backups. A target location is a backup repository where an SLA-based backup policy stores restore points; it can be the same repository for all AWS Regions protected by the policy, or you can specify separate repositories for each region.

Using region-specific backup repositories allows you to avoid cross-region transaction costs associated with data transfer between AWS Regions during backup and archive operations, while using a single default repository may help you ensure data protection regardless of the source location.

Related Topics

[Adding Storage Templates](storage_add.md)

Page updated 9/3/2025

Page content applies to build 10.0.0.232
