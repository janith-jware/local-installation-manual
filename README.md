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
   - If you are asked to enter mqtt broker admin username and password please use the following:
     - Default admin credentials for MQTT Broker
       - username: `admin`
       - password: `public`
   - At this point you can access the mqtt broker server at `http://server-ip-address:18083/` or at `http://server-hostname/:18083` and feel free to setup a new password and enter instead of default credentials.
   - The server must accept inbound traffic through ports `1883,8083,8084,8883,18083,8086,3307,8000`. Configure the firewall to enable these ports. We recommend you to get support of a professional for firewall configuaration.
   - If you are asked to Enter Influx Organization ID, follow the instrcutions below to obtain the organization ID:
     1. access influxDB portal at `http://server-ip-address-or-hostname:8086`
        - Default credentials for InfluxDB portal
          - username: influx_user
          - password: SADafr562c
     3. Go to **About** section of your organization
        ![Select About section](https://github.com/casi-devops-team/local-installation-manual/assets/136977780/61f80b7c-7032-4177-927d-d8633583889d)
     4. Copy the Organization ID and store it securely. You will need this Organization ID in the following steps.
    
4. Visit `http://frontend-server-ip-address-or-hostname:8000/` and activate your license.
5. Run the following command to reload the app.
   ```
   sudo docker restart casi-backend
   ```
7. Visit `http://frontend-server-ip-address-or-hostname/`.
   
8. Generate INFLUX QUERY TOKEN(optional):
   - Visit `http://influxDB-server-ip-address-or-hostname:8086` as mentioned above and Go to **API Tokens** as shown below.
     ![Go to API Tokens](https://github.com/casi-devops-team/local-installation-manual/assets/136977780/5956f7af-fb12-4a71-8206-39af7a4f8b63)
   - Click **GENERATE API TOKEN**.
     ![Click GENERATE API TOKEN](https://github.com/casi-devops-team/local-installation-manual/assets/136977780/97833c4a-aa39-4516-b51d-3a19e897df7f)
   - Select **Custom API Token**.
     ![Select Custom API Token](https://github.com/casi-devops-team/local-installation-manual/assets/136977780/f175fb71-2a95-4ba9-9cf3-2ce3c2c8b77e)
   - Allow Read and Write permission for All buckets and All Telegrafs.
     ![Screenshot (23)](https://github.com/casi-devops-team/local-installation-manual/assets/136977780/0922571e-81f6-4793-9656-c4dce568ce68)
   - Click **GENERATE**.
   - Copy API Token and store it securely. You will need this INFLUX QUERY TOKEN in the following steps.
     ![Screenshot (24)](https://github.com/casi-devops-team/local-installation-manual/assets/136977780/575da537-3f8c-4dd1-9e50-5c2eb102222a)

    
