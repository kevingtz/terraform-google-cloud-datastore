# Module for Google Cloud firestore

This modules helps you to manage [Google Cloud firestore](https://cloud.google.com/firestore/docs/).

Currently, it supports **index creation** by shelling out to gcloud.

## Compatibility

This module is meant for use with Terraform 0.12. If you haven't [upgraded](https://www.terraform.io/upgrade-guides/0-12.html) and need a Terraform 0.11.x-compatible version of this module, the last released version intended for Terraform 0.11.x
is [0.2.0](https://registry.terraform.io/modules/terraform-google-modules/cloud-firestore/google/0.2.0).

## Usage

```
module "firestore" {
  source      = "terraform-google-modules/cloud-firestore/google"
  credentials = "sa-key.json"
  project     = "my-project-id"
  indexes     = "${file("index.yaml")}"
}
```

### Module Inputs

Argument Reference:

- source: Path to the module's folder
- credentials: File path of a service account with access to managing firestore.
- project: The project id to manage firestore indexes for.
- indexes: The contents of an [index file](https://cloud.google.com/firestore/docs/tools/indexconfig#firestore_About_index_yaml).
  This can be extracted from a file on disk using "${file(var.index_file_path)}"

<!-- BEGINNING OF PRE-COMMIT-TERRAFORM DOCS HOOK -->
## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|:----:|:-----:|:-----:|
| indexes | The contents of a index.yaml file, to apply indexes from | string | n/a | yes |
| project | The project id | string | n/a | yes |

<!-- END OF PRE-COMMIT-TERRAFORM DOCS HOOK -->
