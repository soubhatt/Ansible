# Ansible

## Ansible classes and practice
- **Day 1**: Setting up ansible worker nodes and master node
- **Day 2**: Ad-hoc command and add/ remove user playbook
- **Day 3**: Learning about Variable/ansible-vault/webserver playbook
### Documentation
The `ansible-doc` command is a command-line utility within Ansible used to access and display documentation for Ansible modules and plugins.

🔗 [Official Doc Page](https://docs.ansible.com/ansible/latest/command_guide/cheatsheet.html)

<p align="center">
  <img src="https://upload.wikimedia.org/wikipedia/commons/2/24/Ansible_logo.svg" alt="Ansible Logo" width="110">
</p>

<h1 align="center">Ansible</h1>
<p align="center">Classes & Practice Notes</p>

<p align="center">
  <img alt="Tool" src="https://img.shields.io/badge/Tool-Ansible-blue?logo=ansible&logoColor=white">
  <img alt="Status" src="https://img.shields.io/badge/Status-Practice%20Repo-success">
</p>

---

## Table of Contents
- [Overview](#overview)
- [Prerequisites](#prerequisites)
- [Quick Start](#quick-start)
- [Classes & Practice](#classes--practice)
- [Handy Commands](#handy-commands)
- [Project Structure (Suggested)](#project-structure-suggested)
- [Docs & Resources](#docs--resources)
- [Notes](#notes)
- [License](#license)

---

## Overview
This repository tracks my Ansible learning journey—daily notes, playbooks, and small lab exercises.

---

## Prerequisites
- Python 3.x
- Ansible (latest stable)
- SSH access from controller to managed nodes (preferably with SSH keys)

**Install on Ubuntu (either option):**
```bash
# Option A: apt
sudo apt update && sudo apt install -y ansible

# Option B: pip (often newer)
python3 -m pip install --user ansible

# 1) Verify Ansible is installed
ansible --version

# 2) Set up inventory and test connectivity
ansible all -i inventory/hosts.ini -m ping

# 3) Run a playbook (check mode first)
ansible-playbook -i inventory/hosts.ini site.yml --check
ansible-playbook -i inventory/hosts.ini site.yml

Classes & Practice

Use this checklist and link each day to its folder.

 Day 1 — Setting up controller & managed nodes (SSH keys, inventory)

Folder: ./day-01/

 Day 2 — Ad-hoc commands; add/remove user playbook

Folder: ./day-02/

 Day 3 — Variables, Ansible Vault, webserver playbook

Folder: ./day-03/

# List all modules
ansible-doc -l

# Show help for a module
ansible-doc service
ansible-doc user

# Run an ad-hoc command
ansible all -i inventory/hosts.ini -m shell -a "uptime"

# Run a playbook with extra vars
ansible-playbook -i inventory/hosts.ini site.yml -e "env=dev"

# Ansible Vault quickies
ansible-vault create group_vars/prod/vault.yml
ansible-vault encrypt_string 's3cr3tP@ss' --name 'db_password'
ansible-playbook -i inventory/hosts.ini site.yml --ask-vault-pass

.
├── ansible.cfg
├── inventory/
│   └── hosts.ini
├── day-01/
├── day-02/
├── day-03/
├── roles/
│   └── webserver/            # example role (tasks/, handlers/, templates/, files/, vars/)
└── site.yml

Docs & Resources

🔗 Official Cheatsheet: https://docs.ansible.com/ansible/latest/command_guide/cheatsheet.html

🔗 User Guide: https://docs.ansible.com/ansible/latest/user_guide/index.html

🔗 Module Index: https://docs.ansible.com/ansible/latest/collections/index_module.html

🔗 Best Practices (Playbooks): https://docs.ansible.com/ansible/latest/tips_tricks/sample_setup.html

The ansible-doc command is a CLI utility to view documentation for modules and plugins directly from your terminal.