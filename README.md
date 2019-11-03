# Terraform AWS ACM

Terraform module which creates ACM certificates and validates them using Route53 DNS.

## Usage example

Here's the gist of using it directly from github.

```hcl
module acm {
  source = "git@github.com:terraform-module/terraform-aws-acm.git"

  domain_name = "example.com"
  zone_id     = "Z0FK2F3K10ACF0"

  validation_method = "DNS"

  subject_alternative_names = [
      "*.example.com"
  ]

  tags = {}
}

```

## Assumptions

## Available features

Will not allow to add new SANS due to bug that shoulb de fixed [here](https://github.com/terraform-providers/terraform-provider-aws/pull/8708)

## Module Variables

<!-- BEGINNING OF PRE-COMMIT-TERRAFORM DOCS HOOK -->
## Inputs


<!-- END OF PRE-COMMIT-TERRAFORM DOCS HOOK -->

## Commands

<!-- START makefile-doc -->
```
$ make help
hooks                          Commit hooks setup
validate                       Validate with pre-commit hooks
changelog                      Update changelog
release                        Create release version
```
<!-- END makefile-doc -->


## License

Copyright 2019 ivankatliarhcuk

MIT Licensed. See [LICENSE](./LICENSE) for full details.

## How to Contribute

Submit a pull request

# Authors

Currently maintained by [Ivan Katliarchuk](https://github.com/ivankatliarchuk) and these [awesome contributors](https://github.com/terraform-module/terraform-aws-acm/graphs/contributors).
