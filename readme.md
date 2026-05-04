markdown
# 🖥️ Ansible Monitoring Dashboard

Ansible playbook to deploy a real-time server monitoring dashboard for CPU, RAM, and Disk usage.

---

## 📌 Overview

This project automates the deployment of a web-based monitoring dashboard on Ubuntu servers using Ansible. It collects system metrics and displays them in a modern, color-coded interface.

---

## 🚀 Features

- **Fully automated** deployment with Ansible
- **Lighttpd** lightweight web server
- **Real-time metrics** (CPU, RAM, Disk)
- **Color-coded health status** (Healthy / Warning / Danger)
- **Responsive dark-themed UI**
- **Custom variables** (e.g., student name in footer)

---

## 📂 Project Structure
ansible-monitoring-dashboard/
├── site.yml # Main playbook
├── services.yml # Web server setup
├── monitoring.yaml # Dashboard deployment
├── files/
│ ├── metrics.sh # Metrics collection script
│ └── style.css # Dashboard styling
├── templates/
│ └── index.html.j2 # HTML template (Jinja2)
├── inventory/
│ └── hosts.ini # Target hosts
└── README.md

text

---

## 🛠️ Prerequisites

- Ansible installed on control node
- SSH access to target Ubuntu servers
- `become` privileges (sudo)

---

## ⚙️ Installation & Usage

### 1. Clone the repository

```bash
git clone https://github.com/your-username/ansible-monitoring-dashboard.git
cd ansible-monitoring-dashboard
2. Update inventory file
Edit inventory/hosts.ini with your server IPs:

ini
[webservers]
192.168.148.130 ansible_user=ubuntu
3. Run the playbook
bash
ansible-playbook -i inventory/hosts.ini site.yml
You will be prompted to enter your full name (displayed in the dashboard footer).

4. Access the dashboard
Open a browser and navigate to:

text
http://<server-ip>
📊 Dashboard Preview
Status	Color	Condition
Healthy	🟢 Green	< 70%
Warning	🟡 Yellow	70% - 90%
Danger	🔴 Red	> 90%
Screenshots can be found in the /screenshots folder (if added).

🧠 How It Works
services.yml – Installs and starts Lighttpd

monitoring.yaml – Copies metrics.sh, runs it, and generates the dashboard using the Jinja2 template

metrics.sh – Collects CPU, RAM, and Disk stats from the target machine

index.html.j2 – Renders the dashboard with real data

🧪 Example Output
text
========================================
        Server Status Dashboard
========================================
Node: ubuntu-server-01
CPU: 10.0%    [ Healthy ]
RAM: 58.6%    [ Healthy ]
DISK: 98.0%   [ Danger ]
========================================
Last Sync: 20:02:09
Student: Menna Mohamed
🤝 Contributing
Feel free to fork this repo, open issues, or submit PRs with improvements.

📄 License
MIT License — free for learning and production use.

👩‍💻 Author
Menna – Junior DevOps Engineer