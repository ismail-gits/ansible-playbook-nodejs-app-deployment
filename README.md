# Ansible Playbook Nodejs Web App Deployment with Terraform

This repository contains automation scripts and configurations for deploying a Node.js web application using Ansible and Terraform.

## Directory Structure

- **nodejs-web-app**: Directory containing the Node.js application code.
    - **app**: Subdirectory containing the Node.js application files.
        - **server.js**: Node.js server script for serving the web application.
        - **index.html**: HTML file containing the web application layout and content.
    - **images**: Subdirectory containing images used in the web application.
    - **package.json**: Node.js application metadata and dependencies file.
    - **Dockerfile**: Dockerfile for building a Docker image for the Node.js application.
- **terraform-ec2-instance**: Terraform configuration directory for provisioning AWS resources.
    - **main.tf**: Terraform configuration file defining AWS resources like VPC, subnets, security groups, and EC2 instances.
    - **terraform.tfvars**: Terraform variables file containing configuration parameters such as VPC CIDR block, subnet CIDR block, etc.
- **ansible.cfg**: Ansible configuration file specifying settings like inventory and remote user.
- **deploy-node.yaml**: Ansible playbook for installing Node.js, npm, and deploying the Node.js web application.
- **deploy-node-vars.yaml**: Ansible variables file containing configuration parameters used in the playbook.
- **hosts**: Ansible inventory file specifying web server IP address and SSH key location.

## Usage

1. **Terraform Configuration**:
   - Navigate to the `terraform-ec2` directory.
   - Update the `terraform.tfvars` file with desired configurations.
   - Run `terraform init`, `terraform plan`, and `terraform apply` to provision EC2 instance(s) on AWS.

2. **Ansible Configuration**:
   - Update `ansible.cfg` with necessary settings.
   - Ensure that the inventory file `hosts` contains correct web server information.
   - Adjust the playbook `deploy-node.yaml` and variables file `deploy-node-vars.yaml` if needed for custom configurations.

3. **Deploy Node.js Web Application**:
   - Execute the Ansible playbook `deploy-node.yaml` to install Node.js, npm, and deploy the Node.js web application on the provisioned EC2 instance(s).
   - Verify the deployment by accessing the web application using the server's public IP address.

## Notes
- This setup automates the deployment of a Node.js web application on AWS infrastructure using Ansible and Terraform.
- Customize the Terraform and Ansible configurations according to your infrastructure and deployment requirements.
- Ensure proper AWS credentials are configured for Terraform to provision resources.
- Review and modify the Node.js application code and Dockerfile as needed for your specific application requirements.
- You can optionally deploy the application using Docker by building the Docker image and running containers instead of deploying directly on EC2 instances.