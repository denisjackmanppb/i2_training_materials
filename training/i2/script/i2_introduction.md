# What is I2?
## Introduction

I2 is the common name given to the heritage Paddy Power private cloud platform. tooling and framework. I2 stands for "Infrastructure Version 2" and was developed by Betfair in 2015 to help alleviates the many problems that were being experienced using the then existing platform. It was adopted by the group and is used by some of the wider Flutter organisation. It utilises Openstack specifically OSP 16 as the automation middleware for all infrastructure and Ansible for orchestrations. Within these services (colloquially knows as TLAs) are deployed. Each service has its own repository. Physically the infrastructure is hosted in two data centres. Each Data centre is capable of running a full development and full production environment. In addition, the development environments are exact copies of production in terms of infrastructure deployment. The scaling of the development environment and contention ratios are different between the development environment and production. This allows us to maintain the services in a mainly active/active manner. It also allows us to practice to practice A/B deployments. The platform also adheres to a number of principles. These are. 

* Infrastructure as code 
* self-service model for development teams
* Immutable deployments 
* Fail fast approach to development 

## Tools 
There are number of tools which are utilised in the automation of the platform. These are.
* JIRA 
* Gitlab
* GitHub
* Jenkins
* Artifactory
* Vault
* Docker
* Thoughtworks GoCD

In addition to this there are a number of other tools which are used for orchestration and automation. These are.
* Python
* YAML
* Ansible
* Ruby
* CHEF

## Onboarding Process. 
To onboard a service a number of things need to happen. 

## Automation 
At the core of the platform is the I2 Framework. This is a set of Ansible playbooks which are used to deploy the platform. The framework is made up of a number of roles. These are built using Ansible and Python and heavily utilise community and in-house modules to extend functionality. Each service has it's infrastructure defined in a YAML file. This is then used to deploy the service. These will configure VM's in Openstack, Security Groups, networks, load balancers, DNS entries and storage amongst other things. It will also manage the lifecycle of the application stack and its infrastructure. Once the automation deploys the service and configures the service it will also carry out any post deployment tasks that are need. This will include the installation of monitoring, logging and alerting.

## Process
Once the service has been created in JIRA and the YAML file has been created the process is as follows. An engineer makes some changes to the YAML. They then commit the changes to the Gitlab/GitHub repo. They raise a merge request for this. Once this is merged it will trigger a Jenkins job which will create a package which will have a JSON manifest file. This will contain a number of things. 
* The OS image details 
* Application details 
* ansible/chef details 
* SDN load balancer and other framework details 
This manifest allows you to revisit this particular build and rebuild it and deploy. This manifest is stored in Artifactory alongside any other artefacts that are created.
run the Ansible playbooks. The playbooks will then deploy and configure the service on the target environment.
