# Terraform AWS ACM

Terraform module which creates ACM certificates and validates them using Route53 DNS.

[![](https://img.shields.io/github/license/terraform-module/terraform-aws-acm)](https://github.com/terraform-module/terraform-aws-acm)
![](https://img.shields.io/github/v/tag/terraform-module/terraform-aws-acm)
[![](https://img.shields.io/github/workflow/status/terraform-module/terraform-aws-acm/validate/master)](https://github.com/terraform-module/terraform-aws-acm/actions?query=is%3Acompleted)
![](https://github.com/terraform-module/terraform-aws-acm/workflows/Validator/badge.svg)
![](https://img.shields.io/issues/github/terraform-module/terraform-aws-acm)
![](https://img.shields.io/github/issues/terraform-module/terraform-aws-acm)
![](https://img.shields.io/github/issues-closed/terraform-module/terraform-aws-acm)
[![](https://img.shields.io/github/languages/code-size/terraform-module/terraform-aws-acm)](https://github.com/terraform-module/terraform-aws-acm)
[![](https://img.shields.io/github/repo-size/terraform-module/terraform-aws-acm)](https://github.com/terraform-module/terraform-aws-acm)
![](https://img.shields.io/github/languages/top/terraform-module/terraform-aws-acm?color=green&logo=terraform&logoColor=blue)
![](https://img.shields.io/github/commit-activity/m/terraform-module/terraform-aws-acm)
![](https://img.shields.io/github/contributors/terraform-module/terraform-aws-acm)
![](https://img.shields.io/github/last-commit/terraform-module/terraform-aws-acm)

## Usage example

Here's the gist of using it directly from github.

```hcl
module acm {
  source  = "terraform-module/acm/aws"
  version = "2.1.0"

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
## Requirements

| Name | Version |
|------|---------|
| terraform | >= 0.12 |

## Providers

| Name | Version |
|------|---------|
| aws | n/a |

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| allow\_overwrite\_records | Allow creation of this record in Terraform to overwrite an existing record, if any. | `bool` | `true` | no |
| domain\_name | A domain name for which the certificate should be issued | `string` | `""` | no |
| subject\_alternative\_names | A list of domains that should be SANs in the issued certificate | `list(string)` | `[]` | no |
| tags | A mapping of tags to assign to the resource | `map(string)` | `{}` | no |
| ttl | The TTL of the record. | `number` | `60` | no |
| validate\_certificate | Whether or not certificate should be validated | `bool` | `true` | no |
| validation\_method | Which method to use for validation. DNS or EMAIL are valid, NONE can be used for certificates that were imported into ACM and then into Terraform. | `string` | `"DNS"` | no |
| zone\_id | The ID of the hosted zone to contain this record. | `string` | `""` | no |

## Outputs

| Name | Description |
|------|-------------|
| arn | Certificate ARN. |
| distinct\_domain\_names | Distinct domain names. |

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


### :memo: Guidelines

 - :memo: Use a succinct title and description.
 - :bug: Bugs & feature requests can be be opened
 - :signal_strength: Support questions are better asked on [Stack Overflow](https://stackoverflow.com/)
 - :blush: Be nice, civil and polite ([as always](http://contributor-covenant.org/version/1/4/)).

## License

Copyright 2019 Ivan Katliarhcuk

MIT Licensed. See [LICENSE](./LICENSE) for full details.

## How to Contribute

Submit a pull request

# Authors

Currently maintained by [Ivan Katliarchuk](https://github.com/ivankatliarchuk) and these [awesome contributors](https://github.com/terraform-module/terraform-module-blueprint/graphs/contributors).

[![ForTheBadge uses-git](http://ForTheBadge.com/images/badges/uses-git.svg)](https://GitHub.com/)

## Terraform Registry

- [Module](https://registry.terraform.io/modules/terraform-module/acm/aws)