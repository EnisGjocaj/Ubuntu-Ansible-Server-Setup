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

ansible-server-setup/
├── inventory.ini # Server IP and SSH user
├── playbook.yml # Main playbook entry
├── roles/
│ ├── common/ # System tools and user setup
│ ├── nodejs/ # NVM + Node.js + PM2
│ ├── nginx/
│ ├── apache/
│ ├── php/
│ ├── python/
│ ├── certbot/
│ └── ufw/
├── files/ # Static config files (nginx.conf etc.)
├── .env # (Optional) For dynamic IP injection
├── generate_inventory.py # (Optional) Generates inventory.ini from .env
├── .gitignore
└── README.md



---

## 🚀 How to Use

### 1. 📥 Clone the Repository

```bash
git clone https://github.com/your-org/ansible-server-setup.git
cd ansible-server-setup

## 2. 🖊️ Edit the Inventory File

Open or create the misssing `inventory.ini` as we have the example samle format, and set your server IP and SSH user:

```ini
[web]
your.server.ip.here ansible_user=root

Absolutely! Here's the section you want, fully formatted as Markdown:

md

Copy

Edit

\## 2. 🖊️ Edit the Inventory File

Open \`inventory.ini\` and set your server IP and SSH user:

\`\`\`ini

\[web\]

your.server.ip.here ansible\_user=root

Or use the optional .env + script method:

env

Copy

Edit

\# .env

SERVER\_IP=your.server.ip.here

Then generate the inventory:

bash

Copy

Edit

python3 generate\_inventory.py

3\. 🔐 Ensure SSH Access

Make sure your SSH key is added to your agent and you're able to SSH into the server:

bash

Copy

Edit

ssh root@your.server.ip.here

4\. 🧪 Dry Run (Optional)

Run a dry-run check before applying:

bash

Copy

Edit

ansible-playbook playbook.yml -i inventory.ini --check --diff

5\. ⚙️ Run the Playbook

To apply the full server setup:

bash

Copy

Edit

ansible-playbook playbook.yml -i inventory.ini

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