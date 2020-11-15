# ansible-zsx-srv2

Configuration used on a personal server.

## Installation

Install prerequisites:
```sh
ansible-galaxy install -r requirements.yml
```

Create the Ansible Vault pass file:
```sh
echo 'xxxxxxxxxx' > .vault_pass
```

## Usage

Run the `server.yml` playbook over the server:
```sh
ansible-playbook server.yml 
```

You can use various level of verbosity:
```sh
ansible-playbook server.yml -vvv
```
