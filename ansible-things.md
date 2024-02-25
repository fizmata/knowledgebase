### how to print the variables to console 

```
- debug:
    msg: "{{ ansible_facts.architecture }}"
```

### Installing ansible


```
# Create a virtual environment named "ansible-venv" in the home folder
python3 -m venv ~/ansible-venv

# Activate the virtual environment
source ~/ansible-venv/bin/activate

# Install Ansible within the virtual environment
pip install ansible

# Deactivate the virtual environment
deactivate

# Create aliases for Ansible binaries in the virtual environment
for file in ~/ansible-venv/bin/*ansible*; do
    binary_name=$(basename "$file")
    echo "alias $binary_name=\"$file\"" >> ~/.bashrc
done

# Reload the bashrc file to apply the aliases
source ~/.bashrc
```

### Createing repo structure for ansible: 

```
#!/bin/bash

# Ask the user for the vault password
read -sp "Enter the Ansible Vault password: " vault_password
echo

# Create the directory structure
mkdir -p group_vars
touch group_vars/all.yaml
touch hosts
mkdir -p roles/ping/tasks
touch roles/ping/tasks/main.yaml
touch ping.yaml

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
cat << EOF > roles/ping/tasks/main.yaml
---
- name: Ping the remote hosts
  ping:
EOF

# Create a playbook that uses the ping role
cat << EOF > ping.yaml
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

### Ansible.cfg
You can generate a fully commented-out example ansible.cfg file, for example:
```
$ ansible-config init --disabled > ansible.cfg
```
You can also have a more complete file that includes existing plugins:
```
$ ansible-config init --disabled -t all > ansible.cfg
```
You can use these as starting points to create your own ansible.cfg file.

### hosts file entry example
```
vm-1 ansible_host=193.40.156.86 ansible_port=4922 ansible_ssh_user=ubuntu ansible_python_interpreter=python3
```
