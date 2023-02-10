# Research Playbooks
Ansible playbooks for deploying Research projects in Kubernetes.

## Setup
The playbooks run on a host reserved for Ansible use only.  Ansible resources (playbooks, inventory, secrets, etc) reside in the **/ansible** directory on that host.  These playbooks can be used to deploy/remove research projects.

## Usage
```
ansible-playbook ./research-playbooks/<playbook name>.yml -i ../inventory/hosts-solea.ini -l rsch_master_node --private-key ~/path/to/key
```

Playbooks available:
```
deploy-app.yml # This will deploy an application into a Kubernetes cluster.
    Required extra-vars:
        branch
        git_repo_name
        routehost
    Optional extra-vars:
        none
remove-app.yml # This will remove an application from a Kubernetes cluster.
    Required extra-vars:
        branch
        git_repo_name
        routehost
    Optional extra-vars:
        none
```