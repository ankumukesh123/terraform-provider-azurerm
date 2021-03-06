---
subcategory: "Monitor"
layout: "azurerm"
page_title: "Azure Resource Manager: azurerm_monitor_diagnostic_categories"
description: |-
  Gets information about an the Monitor Diagnostics Categories supported by an existing Resource.

---

# Data Source: azurerm_monitor_diagnostic_categories

Use this data source to access information about the Monitor Diagnostics Categories supported by an existing Resource.

## Example Usage

```hcl
data "azurerm_key_vault" "example" {
  name                = azurerm_key_vault.example.name
  resource_group_name = azurerm_key_vault.example.resource_group_name
}

data "azurerm_monitor_diagnostic_categories" "example" {
  resource_id = data.azurerm_key_vault.example.id
}
```

## Argument Reference

* `resource_id` - The ID of an existing Resource which Monitor Diagnostics Categories should be retrieved for.

## Attributes Reference

* `id` - The ID of the Resource.

* `logs` - A list of the Log Categories supported for this Resource.

* `metrics` - A list of the Metric Categories supported for this Resource.

## Timeouts

~> **Note:** Custom Timeouts are available [as an opt-in Beta in version 1.43 & 1.44 of the Azure Provider](/docs/providers/azurerm/guides/2.0-beta.html) and will be enabled by default in version 2.0 of the Azure Provider.

The `timeouts` block allows you to specify [timeouts](https://www.terraform.io/docs/configuration/resources.html#timeouts) for certain actions:

* `read` - (Defaults to 5 minutes) Used when retrieving the Monitor Diagnostics Categories.
