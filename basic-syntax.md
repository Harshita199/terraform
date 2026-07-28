VERY BASIC SYNTAX FOR THE TERRAFORM

block parameters {
ARGUMENTS
}

### Example for aws s3 bucket creation:


```hcl
resource "aws_s3_bucket" "example" {
  bucket = "your-unique-bucket-name"
}
```

- `resource` : Terraform resource block type.

- `"aws_s3_bucket"` : Resource type.
  - `aws` is the provider prefix.
  - `s3_bucket` is the resource type provided by the AWS provider.

- `"example"` : Resource name (local identifier).
  - Used to reference this resource elsewhere in the Terraform configuration.
  - Example:
    ```hcl
    aws_s3_bucket.example.id
    aws_s3_bucket.example.arn
    ```

- `bucket = "your-unique-bucket-name"` : Resource argument that specifies the name of the S3 bucket to create.

BUT STILL THIS WILL NOT WORK, AS BY DEFAULT ONLY LOCAL PROVIDER IS THERE, WE STILL NEED TO INSTALL THE AWS PROVIDER. BELOW IS FOR AWS PROVIDER INSTALLATION:
```hcl
terraform {
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "~> 5.0"
    }
  }
}

provider "aws" {
  region = "us-east-1"
}
```

- `terraform` : Terraform configuration block used to define settings required by Terraform itself.

- `required_providers` : Specifies the providers that Terraform needs for this configuration.

- `aws` : Local name of the provider used throughout the Terraform configuration.

- `source = "hashicorp/aws"` : Specifies the provider source. Here, Terraform downloads the AWS provider maintained by HashiCorp.

- `version = "~> 5.0"` : Specifies the provider version constraint.
  - `~> 5.0` means use version **5.0 or any compatible newer 5.x version**, but **not 6.0 or later**.

- `provider "aws"` : Configures the AWS provider.

- `region = "us-east-1"` : Specifies the AWS region where resources will be created unless overridden.
