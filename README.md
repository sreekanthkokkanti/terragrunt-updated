# Google BigQuery Terraform Configuration

This Terraform configuration manages Google BigQuery datasets, views, and access controls.

## Prerequisites

- Terraform installed (version x.x.x)
- Google Cloud Platform (GCP) account
- Appropriate permissions to create and manage BigQuery resources

## Getting Started

1. Clone this repository to your local machine:

   ```bash
   git clone https://github.com/your-username/your-repo.git
   cd your-repo
   Initialize Terraform and download the required providers:
terraform init
Customize the variables in terraform.tfvars file according to your project requirements.

Configuration Structure
main.tf: Defines the Google BigQuery dataset and access configurations.
variables.tf: Declares input variables used in the configuration.
terraform.tfvars: Contains values for input variables. Customize this file as needed.
README.md: Documentation for the Terraform configuration.
Variables
dataset_id: The ID of the BigQuery dataset.
description: Description of the dataset.
region: The region where the dataset will be located.
delete_contents_on_destroy: Whether to delete the contents of the dataset when destroying.
default_table_expiration_ms: Default table expiration time in milliseconds.
default_partition_expiration_ms: Default partition expiration time in milliseconds.
project_id: GCP Project ID.
custom_cmek: Custom Cloud KMS key for encryption (optional).
labels: Labels to apply to the dataset.
Auth View
AuthView: List of objects representing authorized views.
project_id: ID of the project containing the authorized view.
dataset_id: ID of the dataset containing the authorized view.
table_id: ID of the authorized view.
Auth Dataset
AuthDataset: List of objects representing authorized datasets.
project_id: ID of the project containing the authorized dataset.
dataset_id: ID of the authorized dataset.
Usage
Review and customize the configuration variables.

Execute Terraform commands:

bash
Copy code
terraform plan
terraform apply
Access Control
Access to the dataset is managed through google_bigquery_dataset_access resources.

user_access: Grants access to individual users.
group_access: Grants access to Google Groups.
Customize the group_dataset_access variable in terraform.tfvars to define user and group access.

Cleanup
To destroy the created resources, run:

bash
Copy code
terraform destroy
