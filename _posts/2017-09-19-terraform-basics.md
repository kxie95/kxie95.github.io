---
layout:     post
title:      Terraform Basics
date:       2017-09-19
summary:    Infrastructure as code.
categories: terraform iac
---

#### Files and Folders
* `.tfstate` Stores the current configuration of your infrastructure. This can be local and remote (see: [terraform backend](https://www.terraform.io/docs/backends)).
* `.tf` Terraform configuration file which defines the parameters of your infrastructure.
* `.terraform` This is a folder which stores your state.
* `.tfstate.backup` Stores the result of a terraform plan? Not entirely sure of the purpose.

#### Commands

```
terraform init
```
Initialises a `.terraform` working directory and a blank `.tfstate`.


```
terraform import [parameters] ID
```
Imports state into your `.tfstate` from your existing infrastructure. Check the correct syntax at [the docs](https://www.terraform.io/docs/commands/import.html).
  


```
terraform plan
```
Checks your `.tfstate` against what you've configured in your `.tf` files.


```
terraform apply
```
Applies the changes from terraform plan.

