﻿# Terraform
This module allows you to build an azure dashboard for all resources with the same type. 
The current templates allow you to build dashboard for some metrics but if you need to create some custom template that not in the list you need to do the following:
1.	Select the resource,  and required metrics in Azure portal. 
2.	Pin resource to the new azure dashboard.
3.	Download JSON from dashboard and cut and customize it according to examples in templates folder. 
4.	Save the template in the templates folder of azure_dashboard module.
5.	Update the Get-AzureRmResourceIds.ps1 script, add resource type to switch() block.
6.	Add new local variables to local block, set path to new template and include variable to  local variable resource_resource template _:


locals {
    database_template = “${var.resource_type == “database” ? “azure_database.json”: “”}”
    app_service_template = “${var.resource_type == “app_service” ? “azure_app_service.json”: “”}”
    app_service_plan_template = “${var.resource_type == “app_service_plan” ? “azure_app_service.json”: “”}”
    virtual_machine_template = “${var.resource_type == “virtual_machine” ? “azure_virtual_machine.json”: “”}”
    resource_template = “${local.database_template}${local.app_service_template}${local.app_service_plan_template}${local.virtual_machine_template}”
}
