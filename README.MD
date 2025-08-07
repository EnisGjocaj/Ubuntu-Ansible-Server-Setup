# 🐧 Ubuntu Server Setup — Automated with Ansible

This repository contains a **production-ready Ansible configuration** that automates the complete setup of a fresh Ubuntu VPS server for web application hosting.

---

## 📦 What's Included

This playbook sets up a secure and ready-to-deploy environment with:

### ✅ System Essentials
- Updates & upgrades all packages
- Installs tools: `curl`, `git`, `unzip`, `build-essential`, `ufw`

### 👤 User Management
- Creates a secure `appuser` with sudo privileges
- Adds SSH key authentication

### 🧠 Application Stack
- **Node.js 22** (via NVM)
- **PM2** process manager for Node apps
- **PHP** + Composer + Laravel Installer
- **Python 3** + pip + venv + Django

### 🌐 Web Servers
- **Nginx** (pre-configured with sample frontend site)
- **Apache2** (sample virtual host setup)

### 🔐 Security
- UFW firewall with common ports open (SSH, HTTP, HTTPS)
- Certbot for free HTTPS (Let's Encrypt)

---

## 📁 Folder Structure
```
C:.
├───group_vars
└───roles
    ├───apache
    │   └───tasks
    ├───common
    │   └───tasks
    ├───firewall
    │   ├───files
    │   └───tasks
    ├───nginx
    │   └───tasks
    ├───node
    │   └───tasks
    ├───php
    │   └───tasks
    ├───pm2
    │   └───tasks
    ├───python
    │   └───tasks
    └───user
        └───tasks
```
---

## 🚀 How to Use

### 1. 📥 Clone the Repository

```bash
git clone https://github.com/your-org/ansible-server-setup.git
cd ansible-server-setup 
```

### 2. 🖊️ Edit the Inventory File

Open or create the missing `inventory.ini` as we have the example sample format, and set your server IP and SSH user:

```ini
[web]
your.server.ip.here ansible_user=root
```

### Then generate the inventory:

```
python3 generate\_inventory.py
```
### 3. 🔐 Ensure SSH Access

Make sure your SSH key is added to your agent and you're able to SSH into the server:

```
ssh root@your.server.ip.here
```

### 4. 🧪 Dry Run (Optional)

Run a dry-run check before applying:

```
ansible-playbook playbook.yml -i inventory.ini --check --diff
```

### 5. ⚙️ Run the Playbook

To apply the full server setup:

```
ansible-playbook playbook.yml -i inventory.ini
```

🧠 Tips

📌 You can add more roles as needed.

🐳 Docker role can be added separately.

🧪 Always use --check before deploying to production.

🔄 Re-run the playbook anytime to patch or update the server.

💡 Requirements

Ansible 2.14+

Python 3 (on your local machine)

SSH key-based login to your Ubuntu VPS

🛡️ Security Notice

Your IP address in inventory.ini is not sensitive.

Never commit private SSH keys or passwords.

Use .gitignore to exclude credentials or secrets.

📬 Contact

Made with ❤️ by \[Your Name or Team\]

For questions, feel free to open an issue or email us.

Let me know if you want it branded with your org name (e.g., Dolphins Group) or your GitHub URL.

yaml

Copy

Edit

\---

You can copy-paste this directly into your README.md, and it will render perfectly on GitHub or any Markdown viewer.

Want me to generate the entire README this way?