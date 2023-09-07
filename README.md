# CASI Local Installation Manual

### Recommended Requirements:
 - 3 Web Servers
 - MySQL Server
 - InfluxDB Server

#### Server Requirements:
| API | Frontend App | MQTT Broker |
|--|--|--|
| 4 vCPUs | 1 vCPU | 2 vCPUs |
| 16GB RAM | 1GB RAM | 4GB RAM |
| 50GB Storage | 8GB Storage | 8GB Storage |
| Intel 64bit CPU Architecture | Intel 64bit CPU Architecture | Intel 64bit CPU Architecture  |
| Ubuntu 20.04 | Ubuntu 20.04 | Ubuntu 20.04 |

### API Installation
1. Connect to the API server via SSH.
2. Run the following commands:
`curl -sL https://deb.nodesource.com/setup_14.x | sudo -E bash -`
`sudo apt-get install -y nodejs`
`sudo apt-get update`
`sudo npm install -g pm2`
`sudo pm2 startup systemd`
`sudo apt-get install -y nginx`
`sudo ufw allow OpenSSH`
`sudo ufw allow 'Nginx Full'`
`sudo ufw --force enable`
`sudo git clone https://github.com/casi-devops-team/industrial-dashboard-backend.git /opt/back-end`
Provide your GitHub credentials if required.
`cd /opt/back-end && sudo npm install`
`sudo pm2 start index.js --name main-api` 
`sudo git clone https://github.com/casi-devops-team/industrial-dashboard-backend-cellular.git /opt/back-end2`
`cd /opt/back-end2 && sudo npm install`
`sudo pm2 start index.js --name cellular-api`

    
