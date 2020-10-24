# alfresco-process-springboot-service-deployment

[![Build Status](https://travis-ci.org/Alfresco/alfresco-process-springboot-service-deployment.svg?branch=develop)](https://travis-ci.org/Alfresco/alfresco-process-springboot-service-deployment)
[![pre-commit](https://img.shields.io/badge/pre--commit-enabled-brightgreen?logo=pre-commit&logoColor=white)](https://github.com/pre-commit/pre-commit)

[Docker](https://www.docker.com/) and [Helm](https://helm.sh/) tooling for a generic [Spring Boot](https://spring.io/projects/spring-boot) based service.

## CI/CD

Running on Travis, requires the following environment variable to be set:

| Name | Description |
|------|-------------|
| GITHUB_TOKEN | GitHub token to clone/push helm repo |
