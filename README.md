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
1. Connect to the MQTT broker server via SSH or go to terminal.
2. Run the following command and follow the instructions to launch the mqtt broker.
   ```
   bash <(curl -s https://gist.githubusercontent.com/casi-devops-team/31a5680df02c9632830a574ec895db37/raw/687b145aa23db4bc4b50f93c6a3ea94b263323a7/local-casi-mqtt.sh)
   ```
   Now you can access the mqtt broker server at `http://server-ip-address/` or at `http://server-hostname/`. The server must accept inbound traffic through ports `1883,8083,8084,8883,18083`. Configure the firewall to enable these ports. We recommend you to get support of a professional for firewall configuaration.
3. Connect to the database server via SSH or go to terminal:
4. Run the following command in a server to launch the database server:
   ```
   curl -sSL -o casi_script.sh https://gist.githubusercontent.com/casi-devops-team/6ec4887a4b022a1d1818f5958a86147a/raw/00299fcfbeef744c0d2c3b6c8b92ae72b07c8ff7/local-casi-database.sh && sudo bash casi_script.sh
   ```
   Now you can access influxDB at `http://server-ip-address-or-hostname:8086` and MySQL server via port `3307`.
   The server must accept inbound traffic through ports `8086, 3307`. Configure the firewall to enable these ports. We recommend you to get support of a professional for firewall configuaration.
5. Connect to backend API server via SSH or open the terminal on the backend API server:
8. Run the following command in a server to launch the backend web server:
   ```
   curl -sSL -o casi_script.sh https://gist.githubusercontent.com/casi-devops-team/60cd0a7efc4a831aa10005aee5cc31a3/raw/88297145731fe5ff34f756b955d5c7301d5c03a7/local-casi-backend.sh && sudo bash casi_script.sh
   ```
10. Run the following command in a server to launch the frontend web server:
`curl https://gist.githubusercontent.com/casi-devops-team/91fc7200de48d65cf61214973f30cf2e/raw/db255bc2907ba19c3d135269e5911a82b80aa376/local-casi-frontend.sh | sudo bash`
11. Connect to API server via SSH.

12. Connect to Second API server via SSH.
5. Connect to Database server via SSH.

    
