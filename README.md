# OpenMRS on Azure
This repository contains automation to deploy [OpenMRS](https://openmrs.org/), (Open Medical Records System) on Azure. Great work being done on this project on the [OpenMRS Repo](https://github.com/openmrs/openmrs-core).

## All-in-one:
### OpenMRS+MySQL Containers with Docker Compose on an Azure IaaS Virtual Machine

[//]: # (The short URLs below are to show impact of this solution by tracking number of deployments. You can use the direct link if you wish - https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fmatthansen0%2Fazure-openemr%2Fmain%2Fall-in-one%2Fazuredeploy.json)

[![Deploy To Azure](https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/1-CONTRIBUTION-GUIDE/images/deploytoazure.svg?sanitize=true)](https://urls.hansencloud.com/openmrs-allinone)
[![Visualize](https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/1-CONTRIBUTION-GUIDE/images/visualizebutton.svg?sanitize=true)](http://armviz.io/#/?load=https%3A%2F%2Fraw.githubusercontent.com%2Fmatthansen0%2Fazure-openmrs%2Fmain%2Fall-in-one%2Fazuredeploy.json)
	

This template allows you to deploy an Ubuntu Server 18.04-LTS VM with Docker
and starts an OpenMRS container listening an port 8080 which uses MySQL database running
in a separate but linked Docker container, which are created using Docker Compose. The shell script validates service functionality before finishing; the deployment typically takes about 10 minutes. The docker-compose file is using the ``demo`` docker image tag, it is recommended to change this to ``latest`` if you are deploying into anything besides a lab or demo environment.

This deployment will listen on HTTP/8080 by default and has a public IP resources associated with it, if this is for an internal deployment please [dissociate the public IP address](https://docs.microsoft.com/en-us/azure/virtual-network/remove-public-ip-address-vm) from the VM.

When the deployment is complete you can access the system by going to ``http://PublicIPAddress:8080/openmrs`` or ``http://AzureDNSname:8080/openmrs``. The tomcat configuration in the official openmrs container (currently) points to the root webapp and needs the ``/openmrs`` path appended.

The ***default credentials*** for this deployment are in the [docker-compose.yml file](all-in-one/docker-compose.yml) and by default the login for OpenMRS is ``admin/Admin123``. You can change these credentials using the steps below.


## Contributing: 

PRs and issues welcome! 