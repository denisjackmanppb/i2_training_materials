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

# Presentation Notes:
## Points of interest:
* I2 is a private cloud platform developed by Betfair in 2015.
* It is used by some of the wider Flutter organisation.
* I2 utilises Openstack specifically OSP 16 as the automation middleware for all infrastructure and Ansible for orchestrations.
* Each service has its own repository and is deployed in a mainly active/active manner.
* I2 adheres to a number of principles, including 
    - infrastructure as code, 
    - self-service model for development teams, 
    - immutable deployments, and 
    - fail fast approach to development.
* A number of tools are utilised in the automation of the platform, including 
    - JIRA, 
    - Gitlab,
    - GitHub,
    - Jenkins,
    - Artifactory,
    - Vault,
    - Docker,
    - Thoughtworks GoCD,
    - Python,
    - YAML, 
    - Ansible, 
    - Ruby, and 
    - CHEF.
* To onboard a service, a number of things need to happen, including:
    - Creating the service in JIRA
    - Creating a YAML file defining the service's infrastructure
    - Making changes to the YAML file and committing the changes to the Gitlab/GitHub repo
    - Raising a merge request for the changes
    - Once the merge request is merged, a Jenkins job will be triggered to create a package with a JSON manifest file
    - The manifest file is stored in Artifactory
    - The Ansible playbooks are run to deploy and configure the service on the target environment
## Expanded writing:
I2 is a private cloud platform that was developed by Betfair in 2015 to help alleviate the many problems that were being experienced using the then existing platform. It was adopted by the group and is used by some of the wider Flutter organisation. I2 utilises Openstack specifically OSP 16 as the automation middleware for all infrastructure and Ansible for orchestrations.

One of the key benefits of I2 is that it adheres to a number of principles, including infrastructure as code, self-service model for development teams, immutable deployments, and fail fast approach to development.

* **Infrastructure as code**: This means that the infrastructure for each service is defined in a code file, such as a YAML file. This makes it easy to deploy and manage the infrastructure, and it also makes it easy to version control the infrastructure.
* **Self-service model for development teams**: This means that development teams can deploy and manage their own services without having to rely on a separate infrastructure team. This makes development teams more agile and productive.
* **Immutable deployments**: This means that each deployment of a service is treated as a new version of the service. This makes it easy to roll back to a previous version of the service if there is a problem with the new version.
* **Fail fast approach to development**: This means that I2 is designed to fail quickly if there is a problem. This helps to prevent problems from propagating to other parts of the system.

I2 is a powerful and flexible private cloud platform that can be used to deploy a wide range of services. It is used by some of the largest and most successful companies in the world, and it is a key part of the Flutter technology stack.
## Additional thoughts:
* I2 is a complex platform, and this presentation does not cover all of the details. However, it provides a good overview of the platform and its key features.
* The presentation could be expanded to include more information about the following topics:
    - The I2 Framework
    - The automation process
    - The onboarding process
    - The different tools that are used with I2
    - Case studies of how I2 is being used by Flutter and other companies
The presentation could also be made more visually appealing by using more images and diagrams.