---
page_title: "btp_globalaccount_role_collections Data Source - terraform-provider-btp"
subcategory: ""
description: |-
  List all role collections.
---

# btp_globalaccount_role_collections (Data Source)

List all role collections.

## Example Usage

```terraform
data "btp_globalaccount_role_collections" "all" {}
```

<!-- schema generated by tfplugindocs -->
## Schema

### Read-Only

- `values` (Attributes List) (see [below for nested schema](#nestedatt--values))

<a id="nestedatt--values"></a>
### Nested Schema for `values`

Read-Only:

- `description` (String) The description of the role collection.
- `name` (String) The name of the role collection.
- `read_only` (Boolean) Whether the role collection is readonly.
- `role_references` (Attributes List) (see [below for nested schema](#nestedatt--values--role_references))

<a id="nestedatt--values--role_references"></a>
### Nested Schema for `values.role_references`

Read-Only:

- `description` (String) The description of the referenced role
- `name` (String) The name of the referenced role.
- `role_template_app_id` (String) The name of the referenced template app id
- `role_template_name` (String) The name of the referenced role template.