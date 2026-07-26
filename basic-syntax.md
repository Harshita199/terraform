<block> <parameters> {
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
