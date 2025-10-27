# Ansible Playbook for OpenVPN + FileBrowser Setup

# Install Ansible in Python virtual environment
apt install python3 python3-venv -y 
python3 -m venv ansible_env 
source ansible_env/bin/activate
pip install ansible 

#Project structure was automatically generated using setup script:
#!/bin/bash
set -e

echo "[INFO] Creating ansible structure"

# main directories 
sudo mkdir -p /etc/ansible/{roles,playbooks,files,templates,group_vars,host_vars}

sudo touch /etc/ansible/{inventory,ansible.cfg}
sudo touch /etc/ansible/playbooks/site.yml

# roles and folders
for role in docker nginx openvpn; do
  sudo mkdir -p /etc/ansible/roles/install/$role/{tasks,handlers,templates,defaults,meta}
  sudo touch /etc/ansible/roles/install/$role/{tasks,handlers,templates,defaults,meta}/main.yml
done

Structure: 
├── ansible.cfg
├── files
├── group_vars
│   └── users.yml
├── inventory
├── playbooks
│   └── site.yml
├── roles
│   └── install
│       ├── docker
│       │   ├── defaults
│       │   │   └── main.yml
│       │   ├── handlers
│       │   │   └── main.yml
│       │   ├── meta
│       │   │   └── main.yml
│       │   ├── tasks
│       │   │   └── main.yml
│       │   └── templates
│       │       └── main.yml
│       ├── nginx
│       │   ├── defaults
│       │   │   └── main.yml
│       │   ├── handlers
│       │   │   └── main.yml
│       │   ├── meta
│       │   │   └── main.yml
│       │   ├── tasks
│       │   │   └── main.yml
│       │   └── templates
│       │       └── main.yml
│       └── openvpn
│           ├── defaults
│           │   └── main.yml
│           ├── handlers
│           │   └── main.yml
│           ├── meta
│           │   └── main.yml
│           ├── tasks
│           │   └── main.yml
│           └── templates
│               └── main.yml
└── templates

