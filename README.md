## linux-update.yml
This repo contains a short Ansible playbook to automatically patch and update several mainstream Linux distros across your entire environment. This playbook has been tested and working on Ansible 2.8, the most recent Ansible version as of September 2019.

Requirements: You must have Ansible installed with Ansible Facts enabled, as the playbook requires them to learn the package manager your distro uses. You must also have an Ansible inventory file listing hostnames or IPs of all devices to be upgraded. 

Common
