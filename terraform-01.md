---
cover: /static/terraform-01.png
date: 2022-04-15
datetime: 2022-04-15 00:00:00+00:00
description: 'I I Here We start with the '
edit_link: https://github.com/edit/main/pages/blog/terraform-01.md
jinja: false
long_description: 'I I Here We start with the '
now: 2022-06-25 12:28:31.767855
path: pages/blog/terraform-01.md
slug: terraform-01
status: draft
tags:
- homelab
templateKey: blog-post
title: Terraform-01
today: 2022-06-25
year: 2022
---

I've started using [Terraform](https://www.terraform.io/) to manage Snowflake infrastructure at work.

I'm still a noobie but I've got a workflow that I think makes sense...

Here's the directory setup for a simple project with some databases, schemas, and tables to manage.

```bash
terraform-dir
├── .auto.tfvars
├── databases.tf
├── main.tf
├── schemas.tf
├── tables.tf
├── .terraform
│   └── providers
│       └── registry.terraform.io
│           └── chanzuckerberg
│               └── snowflake
│                   ├── 0.25.6
│                   │   └── linux_amd64
│                   │       ├── LICENSE
│                   │       ├── README.md
│                   │       └── terraform-provider-snowflake_v0.25.6
│                   └── 0.31.0
│                       └── linux_amd64
│                           ├── CHANGELOG.md
│                           ├── LICENSE
│                           ├── README.md
│                           └── terraform-provider-snowflake_v0.31.0
├── .terraform.lock.hcl
├── terraform.tfstate
```


We start with the `main.tf` and I have in here [providers](https://www.terraform.io/language/providers) and [variables](https://www.terraform.io/language/values/variables)

```terraform
terraform {
  required_providers {
    snowflake = {
      source  = "chanzuckerberg/snowflake"
      version = "0.31.0"
    }
  }
}

provider "snowflake" {
  // required
  username = "SNOWFLAKE_USER"
  account  = "URL"

  password = var.snowflake_password
  role     = "ROLE WITH DBA LIKE PERMISSIONS"
}

variable "snowflake_password" {
  type      = string
  sensitive = true
}

variable "public" {
  type = map(any)
}

variable "environment" {
  type = map(any)
}

variable "roles" {
  type = map(any)
}

```