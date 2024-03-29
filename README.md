# linux-update.yml
This repo contains a short Ansible playbook to automatically patch and update several mainstream Linux distros across your entire environment. This playbook has been tested and working on Ansible 2.8, the most recent Ansible version as of September 2019.

## Usage:
`ansible-playbook -i inventory linux-update.yml`

## Requirements: 
You must have Ansible installed with Ansible Facts enabled, as the playbook requires them to learn the package manager your distro uses. You must also have an Ansible inventory file listing hostnames or IPs of all devices to be upgraded. 

## Common Issues:
1. Ansible requires superuser permissions to run OS patches and upgrades in Linux. Be sure your ansible user on each host is in the wheel or sudoers group, or make a manual visudo entry.
2. Ansible 2.8 continues the gradual migration of nearly all Ansible functionality from Python 2 to Python 3. This can cause some issues when updating newer Linux distros with older versions of Ansible, or vice versa. For example, Fedora 30 will not recognize Ansible's Python 2 plugin, so this playbook won't upgrade Fedora properly on older versions of Ansible unless you customize the ansible.cfg file. Refer to https://github.com/ansible/ansible/issues/54855 for more information.
