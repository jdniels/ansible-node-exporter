# Folder Structure
```
.
├── README.md
├── inventory.yml
├── playbook.yml
└── role
    └── ansible
        ├── README.md
        ├── defaults
        │   └── main.yml
        ├── files
        ├── handlers
        │   └── main.yml
        ├── meta
        │   └── main.yml
        ├── tasks
        │   └── main.yml
        ├── templates
        │   └── node_exporter.service.j2
        ├── tests
        │   ├── inventory
        │   └── test.yml
        └── vars
            └── main.yml
```
### Add Host in inventory.yml file
```
all:
  vars:
    ansible_python_interpreter: /usr/bin/python3
  hosts:
    # Put your Ip Here 
    # eg: 10.10.10.1:
```

### Connect to Cloud with SSH 
- edit role/ansible/vars
```
---
# vars file for roles/node-exporter
ssh_key: ~/.ssh/<SSH_KEY.pem>
```
# How To Use

```
ansible-playbook -i inventory.yml playbook.yml
```