# Azure_Devops_Project1
## Introduction
This is the first project of Udacity Azure DevOps. In this project, i write a Packer and a Terraform  to deploy a customizable, scalable web server in Azure.

## Getting Started
1. Clone this repository

2. Create your infrastructure as code

3. Update this README to reflect how someone would use your code.
## Dependencies

1. Create an [Azure Account](https://portal.azure.com) 
2. Install the [Azure command line interface (Azure CLI )](https://docs.microsoft.com/en-us/cli/azure/install-azure-cli?view=azure-cli-latest)
3. Install [Packer](https://www.packer.io/downloads)
4. Install [Terraform](https://www.terraform.io/downloads.html)
## Deploy

### Export the variable

Add to your .bashrc (or .zshrc) file:

```
export AZ_CLIENT_ID=00000000-0000-0000-0000-000000000000
export AZ_CLIENT_SECRET=000000000000000000000
export AZ_TENANT_ID=00000000-0000-0000-0000-000000000000
export AZ_SUSCRIPTION_ID=00000000-0000-0000-0000-000000000000
```

(remember change the value match with your project.)

### Deploy the policy

Deploy the policy (you can do it on Azure Portal) and assign it to the resource group.
### Create the Packer image

```
$ packer build packer/server.json
```
![Parker_Build_Image](./Image/Packer_Build.PNG)
### Initialize Terraform deployment

```
$ terraform init
```
![Terrform_Init_Image](./Image/Terraform_Init.PNG)
### Terraform execution plan
```
$ terraform plan -out solution.plan
```
![Terrform_Plan_Out](./Image/Terraform_Plan_Out.PNG)
### Deploy with Terraform
```
$ terraform apply solution.plan
```
![terrform_apply](./Image/Terraform_apply.PNG)
## How to customize vars.tf

Ex: When you want to deploy on another servers, you much be change values in vars.tf file
```
  variable "server_names"{
  type = list
  default = ["<Server>"]
}
```

## After

###Destroy the infrastructure 
```
$ terraform deploy
```
Terraform will perform
![terraform out put](./Image/Output.PNG)
