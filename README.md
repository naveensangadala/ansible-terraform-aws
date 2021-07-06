ansible-terraform-aws
======================

Ansible+Terraform integration: provision the aws infrastructure by using terraform through ansible playbooks 

Integration steps:
==================

Ansible , terraform & aws cli should be installed in your redhat linux machine,once the installation is done proceed with the below steps. 

1.	Create a directory called “ansible-terraform” in your ansible control machine 
2.	Create another directory called “terraform-aws” inside your “ansible-terraform”
Terraform-aws (contains your terraform configuration files to provision the ec2 instance in aws).
3.	ansible-terraform --> terraform-aws -->  first-ts-ec2.tf 
5.	once the terraform configuration file is created to provision the ec2 instance in aws , the below commands need to be executed under “terraform-aws” directory

terraform validate  --> to check the syntax errors

terraform init  --> to install the required plugins for aws provider

5.	Now Ansible-terraform directory , you should create a yaml file called ansible-terraform.yml to call the terraform configuration file.

ansible-terraform --> ansible-terraform.yml

Execute the ansible playbook 

ansible-playbook ansible-terraform.yml -vvv

ansible-playbook ansible-terraform.yml --extra-vars="terraform_dir=/home/terraform/" -vvv

Note: pass the 'terraform_dir' variable vaule while executing the playbook or specify it in the group_vars

