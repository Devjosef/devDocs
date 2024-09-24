# Terraform

## Introduction
Terraform is an open-source infrastructure as code (IaC) tool that allows you to define and provision infrastructure using a high-level configuration language.

## Basic Syntax
```hcl
# Example of a basic Terraform configuration
provider "aws" {
  region = "us-west-2"
}

resource "aws_instance" "example" {
  ami           = "ami-0c55b159cbfafe1f0"
  instance_type = "t2.micro"

  tags = {
    Name = "example-instance"
  }
}
```

## Common Use Cases
- Provisioning cloud infrastructure
- Managing infrastructure as code
- Automating infrastructure deployment
- Multi-cloud deployments

## Advanced Features
- **Modules**: Reusable configurations that can be shared and versioned.
- **State Management**: Track the state of your infrastructure.
- **Provisioners**: Execute scripts or commands on resources.
- **Workspaces**: Manage multiple environments.

## Code Snippets
### Using Modules
```hcl
# main.tf
module "vpc" {
  source = "terraform-aws-modules/vpc/aws"
  version = "2.77.0"

  name = "my-vpc"
  cidr = "10.0.0.0/16"
  azs  = ["us-west-2a", "us-west-2b", "us-west-2c"]
  ...
}
```

### State Management
```bash
# Initialize Terraform
terraform init

# Apply configuration
terraform apply

# Show current state
terraform show
```

## Tips & Best Practices
- **Version Control**: Store Terraform configurations in version control systems like Git.
- **State Management**: Use remote state backends to share state between team members.
- **Modular Configurations**: Use modules to organize and reuse configurations.
- **Plan and Apply**: Always run `terraform plan` before `terraform apply` to review changes.

## External Resources
- [Terraform Official Documentation](https://www.terraform.io/docs/)
- [Terraform Registry](https://registry.terraform.io/)
- [Terraform Best Practices](https://www.terraform.io/docs/cloud/guides/recommended-practices.html)