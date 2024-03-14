# Kubernetes Deployment Pipeline

This Jenkins pipeline script allows users to execute different deployment actions on Kubernetes clusters based on their selected pipeline choice.

## Parameters

- **pipeline_choice**: Select the pipeline to execute. Choices include:
  - New-Installation: For deploying a new installation.
  - Teardown-Installation: For tearing down an existing installation.
  - Upgradation: For upgrading the existing installation.
- **tarfile_version**: Select the version of the tarfile to use.
- **DEPLOY_TO_CLUSTER_1** to **DEPLOY_TO_CLUSTER_7**: Boolean parameters to indicate whether to deploy to each Kubernetes cluster.
- **SSH_CREDENTIALS**: SSH credentials for connecting to the remote server.

## Stages

### Execute Selected Pipeline

This stage executes the selected pipeline based on the user's choice.

#### Steps

1. **Script**: Executes Groovy script to handle the pipeline execution logic.
   - Obtains the selected pipeline choice and prints it.
   - Prints the selected tarball version.
   - Prints whether each Kubernetes cluster deployment option is selected.
   - Executes the corresponding pipeline based on the selected choice:
     - If 'New-Installation' is selected, triggers the 'New-Installation' job with specified parameters.
     - If 'Teardown-Installation' is selected, triggers the 'Teardown-Installation' job with specified parameters.
     - If 'Upgradation' is selected, triggers the 'Upgradation' job with specified parameters.

