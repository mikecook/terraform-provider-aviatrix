---
layout: "aviatrix"
page_title: "Aviatrix: aviatrix_aws_peer"
sidebar_current: "docs-aviatrix-resource-aws-peer"
description: |-
  Creates and manages Aviatrix AWS Peering
---

# aviatrix_aws_peer

The AWSPeer resource allows the creation and management of Aviatrix AWS Peering.

## Example Usage

```hcl
# Create Aviatrix AWS Peering
resource "aviatrix_aws_peer" "test_awspeer" {
  account_name1 = "test1-account"
  account_name2 = "test2-account"
  vpc_id1       = "vpc-abcd1234"
  vpc_id2       = "vpc-rdef3333"
  vpc_reg1      = "us-east-1"
  vpc_reg2      = "us-west-1"
  rtb_list1     = ["rtb-abcd1234"]
  rtb_list2     = ["rtb-wxyz5678"]
}
```

## Argument Reference

The following arguments are supported:

* `account_name1` - (Required) This parameter represents the name of an AWS Cloud-Account in Aviatrix controller.
* `account_name2` - (Required) This parameter represents the name of an AWS Cloud-Account in Aviatrix controller.
* `vpc_id1` - (Required) VPC-ID of AWS cloud. Example: AWS: "vpc-abcd1234", etc...
* `vpc_id2` - (Required) VPC-ID of AWS cloud. Example: AWS: "vpc-abcd1234", etc...
* `vpc_reg1` - (Required) Region of AWS cloud. Example: AWS: "us-east-1", etc...
* `vpc_reg2` - (Required) Region of AWS cloud. Example: AWS: "us-east-1", etc...
* `rtb_list1` - (Optional) List of Route table ID. Valid Values: ["all"] OR ["rtb-abcd1234"] OR ["rtb-abcd1234,rtb-wxyz5678"] etc...
* `rtb_list2` - (Optional) List of Route table ID. Valid Values: ["all"] OR ["rtb-abcd1234"] OR ["rtb-abcd1234,rtb-wxyz5678"] etc...

The following arguments are computed - please do not edit in the resource file:

* `rtb_list1_output` - List of route table ID of vpc_id1.
* `rtb_list2_output` - List of route table ID of vpc_id2.

## Import

Instance aws_peer can be imported using the vpc_id1 and vpc_id2, e.g.

```
$ terraform import aviatrix_aws_peer.test vpc_id1~vpc_id2
```