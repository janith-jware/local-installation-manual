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
1. Connect to the MQTT broker server via SSH.
2. Run the following command and follow the instructions to launch the mqtt broker.
   `curl https://gist.githubusercontent.com/casi-devops-team/31a5680df02c9632830a574ec895db37/raw/268b9dfbae398a169c70f33400ed50ade4588343/local-casi-mqtt.sh | sudo bash`
3. Run the following command in a server to launch the frontend web server:
`curl https://gist.githubusercontent.com/casi-devops-team/91fc7200de48d65cf61214973f30cf2e/raw/db255bc2907ba19c3d135269e5911a82b80aa376/local-casi-frontend.sh | sudo bash`
5. Connect to API server via SSH.
6. Run the following command in a server to launch the backend web server:
`curl https://gist.githubusercontent.com/casi-devops-team/60cd0a7efc4a831aa10005aee5cc31a3/raw/88297145731fe5ff34f756b955d5c7301d5c03a7/local-casi-backend.sh | sudo bash`
7. Connect to Second API server via SSH.
5. Connect to Database server via SSH.

    
