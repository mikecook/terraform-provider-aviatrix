---
layout: "aviatrix"
page_title: "Aviatrix: aviatrix_arm_peer"
sidebar_current: "docs-aviatrix-resource-arm-peer"
description: |-
  Creates and manages Aviatrix ARM Peering
---

# aviatrix_arm_peer

The ARMPeer resource allows the creation and management of Aviatrix ARM Peering.

## Example Usage

```hcl
# Create Aviatrix ARM Peering
resource "aviatrix_arm_peer" "test_armpeer" {
  account_name1             = "test1-account"
  account_name2             = "test2-account"
  vnet_name_resource_group1 = "vpc-abcd1234"
  vnet_name_resource_group2 = "vpc-rdef3333"
  vnet_reg1                 = "us-east-1"
  vnet_reg2                 = "us-west-1"
}
```

## Argument Reference

The following arguments are supported:

* `account_name1` - (Required) This parameter represents the name of an Azure Cloud-Account in Aviatrix controller.
* `account_name2` - (Required) This parameter represents the name of an Azure Cloud-Account in Aviatrix controller.
* `vnet_name_resource_group1` - (Required) VNet-Name of Azure cloud. Example: "VNet_Name:Resource_Group_Name", etc...
* `vnet_name_resource_group2` - (Required) VNet-Name of Azure cloud. Example: "VNet_Name:Resource_Group_Name", etc...
* `vnet_reg1` - (Required) Region of Azure cloud. Example: "East US 2", etc...
* `vnet_reg2` - (Required) Region of Azure cloud. Example: "East US 2", etc...

The following arguments are computed - please do not edit in the resource file:

* `vnet_cidr1` - List of VNet CIDR of vnet_name_resource_group1.
* `vnet_cidr2` - List of VNet CIDR of vnet_name_resource_group2.

## Import

Instance arm_peer can be imported using the vnet_name_resource_group1 and vnet_name_resource_group2, e.g.

```
$ terraform import aviatrix_aws_peer.test vnet_name_resource_group1~vnet_name_resource_group2
```