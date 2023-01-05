<!-- BEGIN_TF_DOCS -->
# Terraform ACI Tenant SPAN Source Group Module Example

To run this example you need to execute:

```bash
$ terraform init
$ terraform plan
$ terraform apply
```

Note that this example will create resources. Resources can be destroyed with `terraform destroy`.

```hcl
module "aci-tenant-span-source-group" {
  source  = "netascode/tenant-span-source-group/aci"
  version = "0.0.1"

  name        = "SPAN1"
  tenant      = "ABC"
  description = "My Test Tenant Span Source Group"
  admin_state = false
  sources = [
    {
      name                = "SRC1"
      description         = "Source1"
      direction           = "both"
      endpoint_group      = "EPG1"
      application_profile = "AP1"
    }
  ]
  destination_name        = "DESTINATION1"
  destination_description = "My Destination"
}
```
<!-- END_TF_DOCS -->