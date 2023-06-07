# Overview

Ansible Automation Platform 2 (AAP2) + Terraform is a project created by ASA Red hat Colombia to provide Ansible students with a project that allows them to build a playbook stream where the following is done:
- IaC stage with (Terraform)
- Inventory verification stages (Ansible)
- NodeJS (Ansible) application deployment stage
- Stage to functional tests of the application. (Ansible)
Note: all tested to work on AZURE and AWS public clouds.

Usage
---------

1. Enter the AAP2 URL provided by the instructor.
2. Create an execution environment for terraform via the following container image: quay.io/nmartins/terraform_ee
3. Create new credentials for AZURE or AWS in AAP2.
4. create new credentials for the git repository if it is private (optional)
5. Create an inventory named Azure Inventory or AWS Inventory.
6. Within the created inventory, there is a tab called source: create one called Azure Source or AWS Source by entering the            previously created cloud credentials and the following parameters suggested in the following image.
7. Create a project called: Ansible-Terraform where the following repository link will be entered:                                     https://github.com/mpalacio2583/terrafom_cloud.git
8. create the following job template:

  - Terraform IaC. 
    - Inventory: Azure Inventory or AWS Inventory
    - Project: Ansible-Terraform 
    - Execution Environment: Terraform
    - Playbook: Terraform_Azure.yml or  Terraform_AWS.yml
    - Credential: Azure or AWS

  -  Check Inventory. 
    - Inventory: Azure Inventory or AWS Inventory
    - Project: Ansible-Terraform 
    - Execution Environment: Terraform
    - Playbook: add_host_to_Controller_inventory.yml
    - Credential: Controller Credential
