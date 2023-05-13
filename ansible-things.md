### how to print the variables to console 

```
- debug:
    msg: "{{ ansible_facts.architecture }}"
```

### Createing repo structure for ansible: 

```
#!/bin/bash

# Ask the user for the vault password
read -sp "Enter the Ansible Vault password: " vault_password
echo

# Create the directory structure
mkdir -p group_vars
touch group_vars/all.yml
touch hosts
mkdir -p roles/ping/tasks
touch roles/ping/tasks/main.yml
touch ping.yml

# Create the Ansible configuration file
cat << EOF > ansible.cfg
[defaults]
inventory = ./hosts
vault_password_file = ./vault_password.txt
EOF

# Create the vault password file and write the password
echo "$vault_password" > vault_password.txt

# Add the vault password file to .gitignore
echo "vault_password.txt" >> .gitignore

# Create a role named ping that uses the ping module
cat << EOF > roles/ping/tasks/main.yml
---
- name: Ping the remote hosts
  ping:
EOF

# Create a playbook that uses the ping role
cat << EOF > ping.yml
---
- name: Ping all machines
  hosts: all
  gather_facts: false
  roles:
    - ping
EOF

echo "Ansible repository structure created successfully!"
```

I put the file in home directory of the user with permissions `0771` and add alias to it in .profile.
This way I will have a simple command to initiate the ansible repo
