---
layout:     post
title:      Terraform Basics
date:       2017-09-19
summary:    Infrastructure as code.
categories: terraform iac
---

Files and folders:
* *.tfstate* This stores the current configuration of your infrastructure.
* *.tf* This is a terraform configuration file which defines what your infrastructure should be like.
* *.terraform* This is a folder which stores your local state.
* *.tfstate.backup* Stores the result of a terraform plan? Not sure about the purpose.


Initialise a working directory with the .tf configuration files you've written. This creates the .terraform folder and a remote .tfstate if you've configured a [backend](https://www.terraform.io/docs/backends) in your .tf files.
```
terraform init
```

Import state into your local from your existing infrastructure. Check the correct syntax at [the docs](https://www.terraform.io/docs/commands/import.html).  
```
terraform import [parameters] ID
```

Check your local state against where your remote state is.
```
terraform plan
```

Apply the changes from terraform plan.
```
terraform apply
```
