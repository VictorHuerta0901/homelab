# Docker NGINX Server

Environment
Proxmox VM cloned from ubuntu-base template.

Steps

Install Docker
sudo apt install docker.io -y

Run container
sudo docker run -d -p 8080:80 nginx

Result
Web server successfully deployed inside Docker container.

Access
http://VM-IP:8080
