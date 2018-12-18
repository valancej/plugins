# Codefresh Anchore Plugin

Anchore is a service that analyzes Docker images and generates a detailed manifest of the image, a virtual ‘bill of materials’ that includes official operating system packages, unofficial packages, configuration files, and language modules and artifacts. Anchore policies can they be defined to govern security vulnerabilities, package whitelists and blacklists, configuration file contents, presence of credentials in image, manifest changes, exposed ports or any user defined checks. These policies can be deployed site wide or customized for specific images or categories of applications.

For more information view the github repo here: https://github.com/anchore/anchore-engine

## Prerequisites

- Codefresh subscription
- Anchore Engine service

## Usage

In this example, we will scan an image built by Codefresh. Depending on the result of the Anchore policy evaluation, we will choose to push the image to Dockerhub or not. 

### Reference

- Example `codefresh.yml`: https://raw.githubusercontent.com/valancej/plugins/master/plugins/anchore/codefresh.yml
- Github repo containing Dockerfile: https://github.com/valancej/node_critical_fail

### Setup

#### Environment Variables

Set these up within Codefresh pipeline config.

```
ANCHORE_CLI_URL=http://<url-of-anchore-engine>:8228/v1
ANCHORE_CLI_USER=<anchore-username>
ANCHORE_CLI_PASS=<anchore-password>
QA_IMAGE=<image-name>
ANCHORE_FAIL_ON_POLICY=<True or False>
dockerhubUsername=<dockerhub-username>
dockerhubPassword=<dockerhub-password>
```