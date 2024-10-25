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
   curl -sSL -o casi_script.sh https://gist.githubusercontent.com/janith-jware/a237771cb043e34143ae6324acf69e2f/raw/015917f560e41e9743e6b8828713b6b212ac261c/casi-consolidated-local-installation.sh && sudo bash casi_script.sh
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
     3. sss

7. Copy InfluxDB Organization ID:
   * Visit `http://influxDB-server-ip-address-or-hostname:8086` as mentioned above.
   - Go to **About** section of your organization
     ![Select About section](https://github.com/casi-devops-team/local-installation-manual/assets/136977780/61f80b7c-7032-4177-927d-d8633583889d)
   - Copy the Organization ID and store it securely. You will need this Organization ID in the following steps.
8. Generate INFLUX QUERY TOKEN:
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
9. Connect to second backend API server via SSH or open the terminal on the second backend API server:
10. Run the following command in a server to launch the second backend API server:
   ```
   curl -sSL -o casi_script.sh https://gist.githubusercontent.com/casi-devops-team/8f73570ddc96088faa38fe6b96b38933/raw/601b756366ddecff93f1fdfa18df21583a0103f9/local-casi-backend-cellular.sh && sudo bash casi_script.sh
   ```
11. Connect to backend API server via SSH or open the terminal on the backend API server:
12. Run the following command in a server to launch the backend API web server:
    ```
    curl -sSL -o casi_script.sh https://gist.githubusercontent.com/casi-devops-team/60cd0a7efc4a831aa10005aee5cc31a3/raw/76d77aaca7cad6f7e8092d38d6a4ffab06e6b71b/local-casi-backend.sh && sudo bash casi_script.sh
    ```
    - Then, visit `http://backend-api-server-ip-address-or-hostname:8000` to activate the licence.
13. Run the following command in a server to launch the frontend web server:
    ```
    curl -sSL -o casi_script.sh https://gist.githubusercontent.com/casi-devops-team/91fc7200de48d65cf61214973f30cf2e/raw/d8933de7dd0c9bec418bbba2789dc26fac3d2a90/local-casi-frontend.sh && sudo bash casi_script.sh
    ```
14. Visit `http://frontend-server-ip-address-or-hostname/`

    
