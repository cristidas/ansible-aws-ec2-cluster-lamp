# Ansible: AWS EC2 cluster with simple LAMP application

This set of roles and playbooks provisions AWS VPC and EC2 related resources to run a simple LAMP application with default configuration.

Characteristics of the infrastructure raised with this:
  - 1 VPC
  - 2 AZs, with 1 public Subnet each
  - 1 Application Load balancer
  - 1 Auto Scaling Group with 2 EC2 instances
  - LAMP stack will be installed at instance creation, via userdata

## Requirements

  - An AWS account
  - SSH key created, present in AWS and its name defined in the group_vars/prd.yml var file
  - Domain registered, hosted zone created in Route53 and related variables defined in the group_vars/prd.yml


## Usage

First the VPC needs to be created:

```
ansible-playbook provision-vpc.yml
```

Then we can create the EC2 cluster with the LAMP application:

```
ansible-playbook provision-ec2.yml
```
