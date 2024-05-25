# status.forgejo.dev DevOps

Automation to create/configure the infrastructure for all services related to [status.forgejo.dev](https://status.forgejo.dev).


## Prerequisites

This project depends on an existing monitoring server available at [status.1uhosting.de](https://status.1uhosting.de).


## Setup (client/workstation)

- Install all dependencies:
    - [Ansible](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html)
- Copy `vars/uptime-kuma.yml.example` to `vars/uptime-kuma.yml`
    - Replace the dummy values with the real ones


## Ansible

Ansible is used to configure the VMs and create/configure all necessary services.

- To create/configure/update all services on the VMs, simply run:
    - `$ export ANSIBLE_CONFIG=./ansible.cfg`
    - `$ ansible-playbook playbook.yaml`

### Limit Ansible to specific hosts only

- To create/configure/update all services only on ony specific VM, run:
    - `$ export ANSIBLE_CONFIG=./ansible.cfg`
    - `$ ansible-playbook playbook.yaml --limit status`

### Ansible Lint

- Installation: `$ pip3 install ansible-lint`
- Usage: `$ ansible-lint --offline -p ./*.yml`
