# Terraform AWS S3 Module

This module creates an AWS S3 bucket with configurable versioning and public access block settings.

## Usage

```hcl
module "s3_bucket" {
    source = "./"

    bucket_name       = "my-bucket"
    versioning_status = "Enabled"
    tags = {
        Environment = "dev"
        Project     = "example"
    }
}
```

## Resources

- `aws_s3_bucket`: Creates the S3 bucket.
- `aws_s3_bucket_versioning`: Manages versioning for the bucket.
- `aws_s3_bucket_public_access_block`: Restricts public access to the bucket.

## Inputs

| Name              | Description                        | Type   | Default | Required |
|-------------------|------------------------------------|--------|---------|----------|
| bucket_name       | Name of the S3 bucket              | string | n/a     | yes      |
| versioning_status | Versioning status ("Enabled"/"Suspended") | string | "Suspended" | no   |
| tags              | Tags to apply to the bucket        | map    | {}      | no       |

## Outputs

| Name        | Description                |
|-------------|----------------------------|
| bucket_id   | The ID of the S3 bucket    |
| bucket_arn  | The ARN of the S3 bucket   |

## Example

See [Usage](#usage) above.

## License

MIT