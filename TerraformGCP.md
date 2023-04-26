# Terrafrom with GCP

## Workflow of IaC:
1. Scope - Scope the requirement for the GCP and plan how they will be connected
1. Author - Write the Terraform configuration code for the infra that needs to be deployed
1. Initialize - *terraform init* - plugins or modules are installed 
1. Plan - *terraform plan* - review the plan before applying it to the infra
1. Apply - *terraform apply* - Apply the plan and provision the cloud resources

## Intro to Terraform:
Terraform is an IaC tool with With Terraform, you can provision, manage and automate your infrastructure resources in a declarative way, ensuring that the desired state of your resources is maintained.
Multicloud support, open source, define the desired state, dependacies.

## Authenticate with GCP:
- On your workstation:
  - Authenticate using the gcloud cli cmd - *gcloud auth application-default login*
- In a vm on GCP:
  - configure the vm to use service account
- Outside GCP:
  - Service account, downlaoad the json file and use it in terraform
  
 ## Author Phase
 - main.tf    -> Root module
    - foldername(server)/ ->Child module
      - main.tf
      - providers.tf
      -etc.tf
      
###  HCL synex:
```
<BLOCK TYPE> "<BLOCK LABEL>" "<BLOCK LABLE>"{
  #Block body
  <IDENTIFIER> = <EXPRESSION> #Arguemnt
}
```

### Terms and concepts:
#### main.tf
resource blocks to define components of your infrastructure
```
resource "resource_type"{
  #Resource spesific argumetns 
}
```
#### providers.tf
provider block configures the specified provider, in this case google
```
terraform {
  required_providers {
    google = {
      source = "hashicorp/google"
      version = "4.51.0"
    }
  }
}

provider "google" {
  project = "<PROJECT_ID>"
  region  = "us-central1"
}
```
#### variables.tf
```
variable "<VAR_NAME>" {
  default = "<VALUE>"
}
```
and then in the code itself : 
```var.<VAR_NAME>```

#### output.tf:
way to expuse information

#### terraform.tfstate
the state of resourses that are managed in the state file - **DO NOT TOUCH**

#### modules:
set of configuration files in single directory 
