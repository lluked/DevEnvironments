# DevEnvironments

Ansible configuration to setup development environments with Debian and RHEL based distribution's. As I am always using new distributions and computers this was created to provide a base setup on a fresh system. This has been developed with Vagrant to allow for efficient testing, currently boxes with no desktop environment are defined in the Vagrantfile however this can be changed to your base box that has a desktop environment if you wish.

## Playbooks

Playbooks are used to update the base os and install required packages that are common between roles.

## Roles

This ansible configuration makes use of a variety of roles, these have been organised into a structure grouping similar roles together.

### Common:
```
 - ansible_facts (templates ansible_facts results to file to aid with development)
```

### Tools:
```
 - vscode
 - hashicorp (Terraform + Vagrant + Packer)
```

### Virtualisation:
```
 - virtualbox
```

### Container:
```
 - minikube (+kubectl)
 - podman
 - docker
```

### Cloud:
```
 - aws-cli
 - azure-cli
 - gcloud-cli
```

## Usage

### Local

Run ansible with `ansible-playbook ansible/site.yml` from the base directory.

### Vagrant

Edit the Vagrantfile to use your own Vagrant box and run with `vagrant up debian` or `vagrant up redhat` from the base directory.

Note: If `vagrant up` is used both boxes will be brought up however, the second box may fail due to port conflicts, this can be fixed by defining port mappings in the Vagrantfile.
