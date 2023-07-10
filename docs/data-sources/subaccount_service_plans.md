---
page_title: "btp_subaccount_service_plans Data Source - terraform-provider-btp"
subcategory: ""
description: |-
  Lists the plans of services that your subaccount is entitled to use in your environment.
---

# btp_subaccount_service_plans (Data Source)

Lists the plans of services that your subaccount is entitled to use in your environment.

## Example Usage

```terraform
# look up all service plans of a given subaccount
data "btp_subaccount_service_plans" "all" {
  subaccount_id = "6aa64c2f-38c1-49a9-b2e8-cf9fea769b7f"
}

# look up all services available on sapbtp environment in a given subaccount
data "btp_subaccount_service_plans" "sapbtp" {
  subaccount_id = "6aa64c2f-38c1-49a9-b2e8-cf9fea769b7f"
  environment   = "sapbtp"
}

# look up all services available on kubernetes environment in a given subaccount
data "btp_subaccount_service_plans" "k8s" {
  subaccount_id = "6aa64c2f-38c1-49a9-b2e8-cf9fea769b7f"
  environment   = "kubernetes"
}

# look up all services wich have certain label assigned in a given subaccount
data "btp_subaccount_service_plans" "labeled" {
  subaccount_id = "6aa64c2f-38c1-49a9-b2e8-cf9fea769b7f"
  labels_filter = "commercial_name eq 'application'"
}
```

<!-- schema generated by tfplugindocs -->
## Schema

### Required

- `subaccount_id` (String) The ID of the subaccount.

### Optional

- `environment` (String) Filter the response on the environment (sapbtp, kubernetes, cloudfoundry).
- `fields_filter` (String) Filters the response based on the field query.
- `labels_filter` (String) Filters the response based on the labels query.

### Read-Only

- `id` (String, Deprecated) The ID of the subaccount.
- `values` (Attributes List) (see [below for nested schema](#nestedatt--values))

<a id="nestedatt--values"></a>
### Nested Schema for `values`

Read-Only:

- `bindable` (Boolean) Shows whether the service plan is bindable.
- `catalog_id` (String) The ID of the service plan in the service broker catalog.
- `catalog_name` (String) The name of the associated service broker catalog.
- `created_date` (String) The date and time when the resource was created in [RFC3339](https://www.ietf.org/rfc/rfc3339.txt) format.
- `description` (String) The description of the service plan.
- `free` (Boolean) Shows whether the service plan is free.
- `id` (String) The ID of the service plan.
- `last_modified` (String) The date and time when the resource was last modified in [RFC3339](https://www.ietf.org/rfc/rfc3339.txt) format.
- `name` (String) The name of the service plan.
- `ready` (Boolean) Shows whether the service plan is ready.
- `serviceoffering_id` (String) The ID of the service offering.