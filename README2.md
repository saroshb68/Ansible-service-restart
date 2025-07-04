# 🚀 Ansible Service Restart & Code Deployment Playbook

This project contains an Ansible playbook to automate restarting Apache or Tomcat services and pulling updated code from a Git repository across multiple servers.

## 📌 Features
- Stops service safely
- Pulls code from a specified Git repository
- Restarts the service
- Works across all servers listed in `inventory.ini`

## 🛠 Technologies Used
- Ansible
- Git
- Apache/Tomcat
- YAML

## 📂 Project Structure
```
ansible-service-restart/
├── inventory.ini
├── playbook.yml
└── README.md
```

## ▶️ How to Run
```bash
ansible-playbook -i inventory.ini playbook.yml
```

## 📄 Sample Playbook Snippet
```yaml
- name: Restart Apache and deploy code
  hosts: webservers
  become: yes
  tasks:
    - name: Stop Apache
      service:
        name: apache2
        state: stopped
    - name: Pull latest code
      git:
        repo: 'https://github.com/yourrepo.git'
        dest: /var/www/html
    - name: Start Apache
      service:
        name: apache2
        state: started
```

## ✅ Outcome
Fully automated deployment and restart flow, reducing manual steps and minimizing service downtime.
