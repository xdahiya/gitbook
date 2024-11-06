---
description: setup firewall in oracle cloud and open ports
---

# Firewall

sudo apt install firewalld -y

sudo systemctl enable firewalld

sudo firewall-cmd --permanent --zone=public --add-port=80/tcp

sudo firewall-cmd --permanent --zone=public --add-port=443/tcp

sudo firewall-cmd --permanent --zone=public --add-port=8000/tcp

sudo firewall-cmd --permanent --zone=public --add-port=3000/tcp

sudo firewall-cmd --permanent --zone=public --add-port=1-30000/tcp

sudo firewall-cmd --permanent --zone=public --add-port=1-30000/udp

sudo firewall-cmd --reload

\
