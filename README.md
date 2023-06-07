# Overview

Ansible Automation Platform 2 (AAP2) + Terraform is a project created by ASA Red hat Colombia to provide Ansible students with a project that allows them to build a playbook stream where the following is done:
- IaC stage with (Terraform)
- Inventory verification stages (Ansible)
- NodeJS (Ansible) application deployment stage
- Stage to functional tests of the application. (Ansible)
Note: all tested to work on AZURE and AWS public clouds.

Usage
---------

. Enter the AAP2 URL provided by the instructor.
. Create an execution environment for terraform via the following container image: quay.io/nmartins/terraform_ee
. Create new credentials for AZURE or AWS in AAP2.
. create new credentials for the git repository if it is private (optional)
. Create an inventory named Azure Inventory or AWS Inventory.
. Within the created inventory, there is a tab called source: create one called Azure Source or AWS Source by entering the        previously created cloud credentials and the following suggestions in the following image.
7. Create a project in ansible where the following repository link will be entered: https://github.com/mpalacio2583/terrafom_cloud.git
