---
layout: "cloud"
page_title: "Sentinel - Terraform Cloud"
---

# Sentinel Overview

[Sentinel](https://www.hashicorp.com/sentinel) is an embedded policy-as-code
framework integrated with the HashiCorp Enterprise products. It enables
fine-grained, logic-based policy decisions, and can be extended to use
information from external sources.

To learn how to use Sentinel and begin writing policies with the Sentinel
language, see [the Sentinel
documentation](https://docs.hashicorp.com/sentinel/writing/).

You can also use the
[`tfe_sentinel_policy`](/docs/providers/tfe/r/sentinel_policy.html) resource
from the [Terraform Enterprise provider](/docs/providers/tfe/) to upload a
policy using Terraform itself.

## Sentinel in Terraform Cloud

~> Sentinel now supports native VCS integration and direct policy set uploads.
   See [Managing policies for organizations](./manage-policies.html) for details
   or to read about the [migration utility](./manage-policies.html#migration-utility).

Using Sentinel with Terraform Cloud involves:

- [Defining the policies](./import/index.html) - Policies are defined using the
  [policy language](https://docs.hashicorp.com/sentinel/concepts/language) with
  imports for parsing the Terraform plan, state and configuration.
- [Managing policies for organizations](./manage-policies.html) -
  Organization owners add policies to their organization by configuring VCS
  integration or uploading policy sets through the API. They also define which
  workspaces the policy sets are checked against during runs.
- [Enforcing policy checks on runs](./enforce.html) - Policies are checked when
  a run is performed, after the `terraform plan` but before it can be confirmed
  or the `terraform apply` is executed.
- [Mocking Sentinel Terraform data](./mock.html) - Terraform Cloud provides the
  ability to generate mock data for any run within a workspace. This data can be
  used with the [Sentinel CLI](https://docs.hashicorp.com/sentinel/commands/) to
  test policies before deployment.

### Standard Imports

The Terraform integration for HashiCorp Sentinel implements all of the
available [standard imports](https://docs.hashicorp.com/sentinel/imports/).
