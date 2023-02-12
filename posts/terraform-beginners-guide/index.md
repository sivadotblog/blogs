# Terraform Beginners Guide
## Introduction
Terraform is a tool for building, changing, and versioning infrastructure safely and efficiently. Terraform can manage existing and popular service providers as well as custom in-house solutions. Its main purpose is to provide a common language for teams to manage their infrastructure and services. Terraform is a tool for building, changing, and versioning infrastructure safely and efficiently. Terraform can manage existing and popular service providers as well as custom in-house solutions. Its main purpose is to provide a common language for teams to manage their infrastructure and services. Terraform is a tool for building, changing, and versioning infrastructure safely and efficiently. Terraform can manage existing and popular service providers as well as custom in-house solutions.

## Why should I care?
Most organisations lean towards cloud. The biggest challenge facing organisations is how to manage their cloud infrastructure. This is where Terraform comes in. If you are an architect, or a developer or an engineer, you should care about Terraform. 

In the early days of cloud, lets call it Cloud 1.0, teams created their own infrastructure and managed it themselves. This was a very manual process. A lot of questions need to be answered, how do you ensure that the infrasture between environments (production and qa) is consistent? How do you ensure that the infrastructure is secure? How do you ensure that the infrastructure is scalable? How do you ensure that the infrastructure is cost effective? How do you ensure that the infrastructure is reliable?  How do you ensure that the infrastructure is observable? How do you ensure that the infrastructure is recoverable? How do you ensure that the infrastructure is secure? How do you ensure that the infrastructure is compliant? How do you ensure that the infrastructure is auditable? How do you ensure that the infrastructure is repeatable? 

Terramform is a tool that helps you answer these questions. Most organisations have moved to Cloud 2.0. In Cloud 2.0, teams use Infrastructure as Code (IaC) to manage their infrastructure. Terraform is one of the tools that helps you achieve this.

## Simple rules

In this post, we will cover the basics of Terraform. We will run a few hands-on code and see how Terraform works.

Before we start, here are few things you need to know about Terraform.

1. Everything in terraform is an asset state - Consider a print statement in any programming language, say python:
    
     ```python print("hello world") ```

    will print "hello world". Lets say if you run it again? It will print "hello world". Each execution is isolated and unrelated.

    Lets try this in Terraform,
    ```terraform output "hello_world" { value = "hello world" } ```

    when you run it for the first time, you will see an message that says 1 new asset is created:
        
        ``` Apply complete! Resources: 1 added, 0 changed, 0 destroyed. ```

    The output "hello_world" is an asset state. Terraform will ensure that the state is always hello world. So, when you run it for the first time, an new asset called "hello_world" is created. When you try ruinning it again, since the asset already exists and since there is no change to the asset, you will see the following message:

    ``` No changes. Infrastructure is up-to-date. ```



2. In Terraform, everything is a resource or a data source. A resource is something that can be created, modified or destroyed. A data source is something that can be read. You can either create/update/destroy a resource or read about an existing resource. For example, a resource/data source can be a virtual machine, a database, a network, a load balancer, a security group, a key vault or a storage account. 

    ```terraform resource "azurerm_resource_group" "rg" { name = "my-rg" location = "westus" } ```

    will create a resource group called "my-rg" in the westus region. 

    ```terraform data "azurerm_resource_group" "rg" { name = "my-rg" } ```

    will read  about the resource group called "my-rg".

3.  If you want to use terraform , dont Google. Always Go to registry.terraform.io to begin with.


## Things you need to get started

1. Terraform CLI 
    [Here is a link to the Terraform download page](https://developer.hashicorp.com/terraform/tutorials/aws-get-started/install-cli).  If you are a windows user, I highly recommend using wsl (widoows subsystem for linux). You can follow this [link](https://docs.microsoft.com/en-us/windows/wsl/install-win10) to install wsl. Windows powershell/shell is not a good option for any programming in my opinion.


2. Terraform Cloud Account (optional)
    Create a free account in Terraform Cloud. You can follow this [link](https://app.terraform.io/) to create an account. 












   