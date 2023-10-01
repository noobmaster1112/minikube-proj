## Installation
- sudo apt-get update
- sudo apt-get install ca-certificates curl gnupg
- sudo install -m 0755 -d /etc/apt/keyrings
- curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
- sudo chmod a+r /etc/apt/keyrings/docker.gpg
- `echo \
  "deb [arch="$(dpkg --print-architecture)" signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  "$(. /etc/os-release && echo "$VERSION_CODENAME")" stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null`
- sudo apt-get update
- sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
- sudo groupadd docker
- sudo usermod -aG docker $USER
- sudo systemctl start docker.service
- curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
- sudo install minikube-linux-amd64 /usr/local/bin/minikube
- minikube start
- cat 'alias kubectl="minikube kubectl --"' >> ~/.bashrc
- cat 'eval $(minikube -p minikube docker-env)' >> ~/.bashrc
- Put minikube-dashboard.service and minikube-tunnel.service in /etc/systemd/system/
- Append `user ALL=(ALL) ALL, NOPASSWD: /usr/bin/ip` in visudo file for minikube-tunnel.service to work properly.
- Enable and start both the services.
- To access the dashboard goto http://localhost:8081
