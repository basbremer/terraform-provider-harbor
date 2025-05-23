---
# generated by https://github.com/hashicorp/terraform-plugin-docs
page_title: "harbor_project_member_groups Data Source - terraform-provider-harbor"
subcategory: ""
description: |-
  
---

# harbor_project_member_groups (Data Source)

<!-- schema generated by tfplugindocs -->

## Example Usage

```terraform
data "harbor_project_member_groups" "example" {
  project_id = "1"
}

output "project_member_group_ids" {
  value = [data.harbor_project_member_groups.example.project_member_groups.*.id]
}
```

## Schema

### Required

- `project_id` (String) The id of the project within harbor.

### Read-Only

- `id` (String) The ID of this resource.
- `project_member_groups` (List of Object) (see [below for nested schema](#nestedatt--project_member_groups))

<a id="nestedatt--project_member_groups"></a>

### Nested Schema for `project_member_groups`

A list of project member group matching the previous arguments. Each `project_member_group` object provides the attributes documented below.

Read-Only:

- `id` (Number) The ID of this resource.
- `project_id` (String) The id of the project that the group has access to.
- `group_name` (String) The name of the group.
- `role` (String) The permissions that the group is granted.

This data source retrieves a list of Harbor project member groups and filters them based on the `project_id` argument. It returns a list of `project_member_group` objects, each containing the `id`, `project_id`, `group_name` and `role` attributes of a project member group that matches the filter criteria.
