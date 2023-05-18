## Kubernetes Ephemeral Environments
![Kubernets](https://img.shields.io/badge/-Kubernetes-326CE5?style=for-the-badge&logo=Kubernetes&logoColor=white)
###### This repository contains the demo explained in the article [Ephemeral Kubernetes Environments: A Cost-Effective Solution for Streamlining Minor Environments and Multi-Tenancy](https://amralaayassen.medium.com/ephemeral-kubernetes-environments-a-cost-effective-solution-for-streamlining-minor-environments-d23a00c9f66f)



##### Project layout

```
nodejs-microservices-example
│   package-lock.json
│   package.json
│   README.md
│
├───.githubAmrAlaaYassen/problem-solving.git
│   └───workflows 
│           gateway.yaml             -> CICD Pipeline to build and deploy the gateway microservice from any branch on an ephemeral
|                                       environment.
│           worker.yaml              -> CICD Pipeline to build and deploy the worker microservice from any branch on an ephemeral
|                                       environment.
|           pr-gateway.yaml          -> CICD pipeline to build and deploy the gateway microservice for a specific PR.
|           pr-destroy-gateway.yaml  -> Pipeline to destroy the environment created for a specific PR on pull request close or merge for
|                                       the gateway microservice.
|           pr-worker.yaml           -> Pipeline o build and deploy the worker microservice for a specific PR.
|           pr-destroy-worker        -> Pipeline to destroy the environment created for a specific PR on pull request close or merge for
|                                       the gateway microservice.
|
│
├───db-fixture              -> Loads database fixtures into the database.
│
├───gateway                 -> Code and Docker files for the gateway microservice.
│   │   Dockerfile
│   │   nodemon.json
│   │   package-lock.json
│   │   package.json
│   │   README.MD
│   │
│   └───src
│           index.js
│
├───scripts                 -> Deployment helper scripts.
│   │   build-image.sh        -> Builds a Docker image.
│   │   push-image.sh         -> Publishes a Docker image.
│   │
│   └───kubernetes          -> Kubernetes configuration files.
│           db.yaml           -> Database configuration.
│           gateway.yaml      -> Gateway microservice configuration.
│           worker.yaml       -> Worker microservice configuration.
│
└───worker                  -> Code and Docker files for the worker microservice.
    │   .dockerignore
    │   Dockerfile
    │   nodemon.json
    │   package-lock.json
    │   package.json
    │   README.MD
    │
    └───src
            index.js
```
