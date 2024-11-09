# CASI Local Installation Manual

### Recommended Requirements:
 - 3 Web Servers
 - Database Server
 - MQTT Broker Server

#### Server Requirements:
| API | API2 | Frontend App | MQTT Broker | Database Server |
|--|--|--|--|--|
| 4 vCPUs | 2 vCPUs | 1 vCPU | 2 vCPUs | 2 vCPUs |
| 16GB RAM | 8GB RAM | 1GB RAM | 4GB RAM | 4GB RAM |
| 50GB Storage | 50GB Storage | 8GB Storage | 8GB Storage | 100GB Storage (To be scaled with usage growth) |
| Intel 64bit CPU Architecture | Intel 64bit CPU Architecture | Intel 64bit CPU Architecture  | Intel 64bit CPU Architecture  | Intel 64bit CPU Architecture  |
| Ubuntu 20.04 | Ubuntu 20.04 | Ubuntu 20.04 | Ubuntu 20.04 | Ubuntu 20.04 |

### API Installation
1. Connect to the server via SSH or go to terminal.
3. Run the following command and follow the instructions to launch the mqtt broker.
   ```
   curl -sSL -o casi_script.sh https://gist.githubusercontent.com/janith-jware/3e61a463f7a88d72f6051672e53123e2/raw/c8c6f3ac99714fcebd6ee4e5202e41f30012b0bc/casi-local-instant-installation.sh && sudo bash casi_script.sh
   ```

   Notes:
   - You will be asked to enter the frontend server IP address or hostname once you run the command above. If it is a public server, you may either mention the public IP address of the server or any domain name that is pointed to that server. If you intend access the system across your Local Area Network (LAN), mention the local IP address of your server within the LAN. If you wish to use the app in the same local computer only, mention either `127.0.0.1` or `localhost`.
    
2. Visit `http://frontend-server-ip-address-or-hostname:8000/` and activate your license.
3. Run the following command to reload the app.
   ```
   sudo docker restart casi-backend
   ```
4. Visit `http://frontend-server-ip-address-or-hostname/`.
   
    
