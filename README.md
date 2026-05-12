# NGINX Installation using Ansible Galaxy and Handlers

Automate NGINX installation across multiple AWS servers (Ubuntu & Amazon Linux) using Ansible roles and handlers.

---

## 📁 Project Structure

```
nginx-Installation-using-Ansible-Galaxy-and-Handlers/
├── README.md
├── ansible.cfg
├── inventory/
│   └── hosts
├── ngnix_setup.yaml
└── roles/
    └── nginx/
        ├── README.md
        ├── defaults/
        │   └── main.yml
        ├── files/
        ├── handlers/
        │   └── main.yml
        ├── meta/
        │   └── main.yml
        ├── tasks/
        │   └── main.yml
        ├── templates/
        ├── tests/
        │   ├── inventory
        │   └── test.yml
        └── vars/
            └── main.yml
```

---

## ⚙️ Prerequisites

- Ansible installed on control node
- AWS EC2 instances (Ubuntu & Amazon Linux)
- PEM key file with correct permissions

```bash
chmod 400 ~/k8s.pem
```

---

## 🚀 How to Run

**1. Clone the repository:**
```bash
git clone https://github.com/Ahad9049/nginx-Installation-using-Ansible-Galaxy-and-Handlers.git
cd nginx-Installation-using-Ansible-Galaxy-and-Handlers
```

**2. Update inventory file:**
```bash
nano inventory/hosts
```
```ini
[servers]
ubuntu ansible_host=<ubuntu-ip> ansible_user=ubuntu
amazon ansible_host=<amazon-ip> ansible_user=ec2-user

[servers:vars]
ansible_ssh_private_key_file=~/k8s.pem
ansible_python_interpreter=/usr/bin/python3
```

**3. Run the playbook:**
```bash
ansible-playbook ngnix_setup.yaml
```

---

## ✅ What It Does

- Updates Ubuntu and Amazon Linux servers automatically
- Installs NGINX on both servers
- Handlers restart NGINX automatically when configuration changes
- Works across multiple OS types with one playbook

---

## 🛠️ Tech Stack

- Ansible
- Ansible Galaxy
- AWS EC2
- Ubuntu & Amazon Linux
- NGINX

---

## 👨‍💻ل Author

**Abdul Ahad** — [@Ahad9049](https://github.com/Ahad9049)
