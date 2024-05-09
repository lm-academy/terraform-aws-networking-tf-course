# terraform-aws-networking-tf-course
Networking module created during Lauro Müller's Terraform course: https://www.lauromueller.com/courses/mastering-terraform

This module manages the creation of VPCs and Subnets, allowing for the creation of both private and public subnets.

Example usage:
```
module "vpc" {
  source = "./modules/networking"

  vpc_config = {
    cidr_block = "10.0.0.0/16"
    name       = "your_vpc"
  }

  subnet_config = {
    subnet_1 = {
      cidr_block = "10.0.0.0/24"
      az         = "eu-west-1a"
    }
    subnet_2 = {
      cidr_block = "10.0.1.0/24"
      public     = true
      az         = "eu-west-1b"
    }
  }
}
```

**Check my other courses:** 

- 👉 Mastering GitHub Actions: From Beginner to Expert - https://www.lauromueller.com/courses/mastering-github-actions
- 👉 Write better code: 20 code smells and how to get rid of them -  https://www.lauromueller.com/courses/writing-clean-code
