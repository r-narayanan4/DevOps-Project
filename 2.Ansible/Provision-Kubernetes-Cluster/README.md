# Kubernetes Cluster Setup

This repository contains an Ansible Playbook for configuring a Kubernetes cluster. The playbook is designed to set up one master node and two worker nodes. Before you proceed, make sure you have met the following prerequisites:

## Prerequisites

1. **Machine Setup**:
   - Set up the machines you intend to use for your Kubernetes cluster. Each machine should have a static IP address and a unique hostname based on your requirements.

2. **Ansible Installation**:
   - Ansible should be installed on the machine from which you intend to execute the playbook. This machine is typically the master or control plane node.
   - *Note*: This playbook is based on CentOS machines. If you use a different operating system, you may need to make adjustments.

3. **Host Configuration**:
   - Ensure that the hostnames of the machines are correctly set in the Ansible hosts file located in the `inventory` directory. If you change the hostname of any machine, update the corresponding entry in the hosts file.

4. **Variable Configuration**:
   - If you need to customize any values for your cluster setup, check the `var.yaml` file located in the `groupvars` directory. Adjust any variables as required.

## Getting Started

Follow these steps to set up your Kubernetes cluster:

1. Clone this repository to your local machine:

   To get started, clone this repository to your local machine:

   ```bash
   git clone https://github.com/r-narayanan4/Kubernetes-cluster-setup.git
   ```

2. Testing Connectivity

    To test the connectivity to your machines and ensure they are reachable, use the following Ansible command:

    ```bash
   ansible -m ping all
   ```

 If the result shows success for all machines, proceed to the next step.


3. Running the Ansible Playbook

   To configure your Kubernetes cluster, run the Ansible playbook using the following command:

    ```bash
    ansible-playbook setup.yaml
    ```

This command will initiate the setup process for your Kubernetes cluster.

After running the playbook, follow the instructions to complete the configuration.

If you encounter any issues or need to make further customizations, refer to the playbook and variable files to adjust the configuration as needed.

## Conclusion

After completing the above steps, your Kubernetes cluster should be configured and ready for use. You can now start deploying and managing your applications on the cluster.

If you encounter any issues or need to make further customizations, refer to the playbook and variable files to adjust the configuration as needed.

**Note:** Ensure that you have a good understanding of Kubernetes and Ansible before proceeding with this setup. Additionally, always exercise caution when making changes to your infrastructure.
