---
# generated by https://github.com/hashicorp/terraform-plugin-docs
page_title: "orcasecurity_shift_left_project Resource - orcasecurity"
subcategory: ""
description: |-
  Provides a Shift Left project resource. Projects allow you to organize code risk findings within Orca. You can create projects for certain repos, apps, or environments. You can learn more here https://docs.orcasecurity.io/docs/shift-left-security-projects.
---

# orcasecurity_shift_left_project (Resource)

Provides a Shift Left project resource. Projects allow you to organize code risk findings within Orca. You can create projects for certain repos, apps, or environments. You can learn more [here](https://docs.orcasecurity.io/docs/shift-left-security-projects).

## Example Usage

```terraform
// Shift Left project
resource "orcasecurity_shift_left_project" "shift_left_project_1" {
  name             = "Project 1"
  description      = "Project for all repos"
  key              = "project-1"
  default_policies = true
}
```

<!-- schema generated by tfplugindocs -->
## Schema

### Required

- `default_policies` (Boolean) Whether or not the Orca built-in policies are attached to the project.
- `description` (String) Shift Left project description.
- `key` (String) Shift Left key.
- `name` (String) Shift Left project name.

### Optional

- `exceptions_ids` (List of String) Exception lists to attach to this project, specified by their IDs.
- `git_default_baseline_branch` (String) By default, the main or master branch is used to capture the baseline. If you need to select a different branch that will serve as your project's/repository's main (protect) branch, specify it here. You can read more [here](https://docs.orcasecurity.io/docs/shift-left-baseline).
- `policies_ids` (List of String) Policies to attach to this project, specified by their IDs.
- `support_code_comments_via_cli` (String) Controls whether IaC code comments (for suppressing findings) should be allowed, ignored, or blocked. You can read more about it [here](https://docs.orcasecurity.io/docs/managing-iac-exceptions). Possible values are BLOCK, ALLOW, and IGNORE.
- `support_cve_exceptions_via_cli` (String) Control whether CVEs exception management via code should be allowed or blocked. Possible values are BLOCK and ALLOW. ALLOW: an exception file can be passed to the CLI execution in order to suppress issues. BLOCK: the scan will fail when exceptions are defined and specified in the CLI execution.
- `support_secret_detection_suppression_via_cli` (String) Control whether code comments or exception handling via config file to suppress found secrets should be allowed, ignored, or blocked. Possible values are BLOCK, ALLOW, and IGNORE. If BLOCK is specified, the scan will fail if issues are found that are ignored via code comments or the exception configuration file.

### Read-Only

- `id` (String) Shift Left project ID.
