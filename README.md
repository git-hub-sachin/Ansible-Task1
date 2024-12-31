# Ansible Automation Task

This repository contains Ansible playbooks and roles for automating the installation and configuration of Jenkins and Docker.

## Task Overview

- Install Jenkins and Docker.

## EC2 Instance Setup

1. **Provision EC2 Instance**:
   - Launch an EC2 instance to act as a Control node.
   - Launch an EC2 instance to act as a Target node.

2. **Install Ansible**:
   - Follow official Ansible documentation for installation.

3. **Configure Ansible Inventory**:
   - Add the EC2 instance to the inventory file.

4. **Manage PEM Key**:
   - Adjust permissions for the PEM key:
     ```bash
     chmod 400 /home/giit/Desktop/ubuntu.pem
     ```
   - Upload the PEM key to the EC2 instance:
     ```bash
     scp -i /home/giit/Desktop/ubuntu.pem /home/giit/Desktop/ubuntu.pem ubuntu@52.90.193.73:~/.ssh/
     ```
   - Locate the PEM key on the EC2 instance:
     ```bash
     sudo find / -name "ubuntu.pem"
     ```
   - Update permissions for the PEM key:
     ```bash
     chmod 400 /home/ubuntu/.ssh/ubuntu.pem
     ```
5. Created roles for Jenkins and Docker
6. Created Playbooks for Jenkins and Docker
7. Executed Playbooks

## Directory Structure

```plaintext
├── ansible.cfg
├── hosts
├── inventory
├── playbooks
│   ├── install_docker.yml
│   └── install_jenkins.yml
└── roles
    ├── docker
    │   ├── defaults
    │   │   └── main.yml
    │   └── tasks
    │       └── main.yml
    └── jenkins
        ├── defaults
        │   └── main.yml
        ├── meta
        ├── tasks
        │   └── main.yml
        └── vars
