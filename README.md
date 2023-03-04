# Abbey Starter Kit Policies with Enforcement Levels Example

This example shows how to create a Grant Kit.
The example features requesting access to a [Snowflake Role Grant](https://registry.terraform.io/providers/Snowflake-Labs/snowflake/latest/docs/resources/role_grants)
from multiple reviewers, requiring only `one_of` the reviewers to approve the access.

However, this access request process will initiate only if the corresponding access `policies` check passes.
Grant Kit `policies` are built on top of [Open Policy Agent (OPA)](https://www.openpolicyagent.org/) and are
written in Rego.

In this example, the OPA policy evaluation will fail because
of the `deny[msg] { ... }` rule in the Rego code. If you want the OPA policy evaluation to pass the check,
then you can replace `deny` (mandatory enforcement) with `warn` (advisory enforcement).
If you want to disable the policy evaluation, then delete the `policies` block in the `grant_kit` resource.

## Usage

Visit this [Starter Kit's docs](https://docs.abbey.so/tutorials/policy-enforcement-levels/granting-access-to-snowflake-with-enforcement-levels) for a short usage walkthrough.

## :books: Learn More

To learn more about Grant Kits and Grant Workflows, visit the following resources:

- [Abbey Labs Documentation](https://docs.abbey.so) - learn about automating access management with Abbey Labs.
