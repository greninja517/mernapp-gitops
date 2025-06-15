This repository contains the Kubernetes manifests and Helm chart required for deploying and managing the MERN application on a GKE cluster using GitOps practices.

## Overview

- **Purpose:** Acts as the GitOps source of truth for the MERN application's deployment configuration.
- **Role in DevOps Project:** 
  - Works alongside the infrastructure-as-code (IaC) and application source code repositories.
  - Used by GitOps tools (ArgoCD) to continuously synchronize the desired state of the application in the Kubernetes cluster.
  - All changes to application deployment, configuration, and secrets are managed declaratively via version control.


## How it Works

- The CI pipeline (from the application code repository) updates image tags and pushes changes to this repository or any person makes changes to the repo to update the configuration.
- ArgoCD (GitOps controller) watches this repository and applies changes automatically to the GKE cluster.
- All application lifecycle operations (deploy, update, rollback) are managed through Git commits and pull requests.

## Related Repositories

- **Infrastructure:** [mernapp-infra](https://github.com/greninja517/mernapp-infra) — Terraform code for provisioning GCP resources and Kubernetes cluster.
- **Application:** [mernapp-code](https://github.com/greninja517/mernapp-code) — Source code for the MERN application.

