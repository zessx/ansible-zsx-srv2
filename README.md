# ansible-zsx-srv2

Configuration used on a personal server.

## Installation

Install prerequisites:
```sh
ansible-galaxy install -r requirements.yml
brew install esolitos/ipa/sshpass
```

Create the Ansible Vault pass file:
```sh
echo 'xxxxxxxxxx' > .vault_pass
```

## Usage

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
