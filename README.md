# ansible-zsx-srv2

Configuration used on a personal server.

## Prerequisites

Make sure you're using an Ansible version at least equal to 2.9.

## Installation

Install dependencies:
```sh
ansible-galaxy install -r requirements.yml
```

Create the Ansible Vault pass file:
```sh
echo 'xxxxxxxxxx' > .vault_pass
```

## Provisioning

For the first provisioning, you'll need to use the root user, and will be prompted its password:
```sh
ansible-playbook server.yml -e ansible_user=root -kK
```

For the next times, simply use the playbook (which will be run with the defined admin user. You may also use various level of verbosity:
```sh
ansible-playbook server.yml -vvv
```

You can provision a single tag, this will be faster and easier:
```sh
ansible-playbook server.yml --tags=users
```

# Deploy

Use the `deploy.yml` playbook to deploy a site. Before to do so, you must load your SSH key on MacOS:
```sh
ssh-add -K && ansible-playbook deploy.yml -e site=<site>
```
