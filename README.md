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
1. Connect to the MQTT broker server via SSH or go to terminal.
2. Run the following command and follow the instructions to launch the mqtt broker.
   ```
   bash <(curl -s https://gist.githubusercontent.com/casi-devops-team/31a5680df02c9632830a574ec895db37/raw/2c15e056bcc1bf463c6542103c953adff389010b/local-casi-mqtt.sh)
   ```
   Now you can access the mqtt broker server at `http://server-ip-address:18083/` or at `http://server-hostname/:18083`. The server must accept inbound traffic through ports `1883,8083,8084,8883,18083`. Configure the firewall to enable these ports. We recommend you to get support of a professional for firewall configuaration.
3. Connect to the database server via SSH or go to terminal:
4. Run the following command in a server to launch the database server:
   ```
   curl -sSL -o casi_script.sh https://gist.githubusercontent.com/casi-devops-team/6ec4887a4b022a1d1818f5958a86147a/raw/00299fcfbeef744c0d2c3b6c8b92ae72b07c8ff7/local-casi-database.sh && sudo bash casi_script.sh
   ```
   Now you can access influxDB at `http://server-ip-address-or-hostname:8086` and MySQL server via port `3307`.
   The server must accept inbound traffic through ports `8086, 3307`. Configure the firewall to enable these ports. We recommend you to get support of a professional for firewall configuaration.
5. Copy InfluxDB Organization ID:
   * Visit `http://influxDB-server-ip-address-or-hostname:8086` as mentioned above.
   - Go to **About** section of your organization
     ![Select About section](https://github.com/casi-devops-team/local-installation-manual/assets/136977780/61f80b7c-7032-4177-927d-d8633583889d)
   - Copy the Organization ID and store it securely. You will need this Organization ID in the following steps.
6. Generate INFLUX QUERY TOKEN:
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
7. Connect to second backend API server via SSH or open the terminal on the second backend API server:
8. Run the following command in a server to launch the second backend API server:
   ```
   curl -sSL -o casi_script.sh https://gist.githubusercontent.com/casi-devops-team/8f73570ddc96088faa38fe6b96b38933/raw/601b756366ddecff93f1fdfa18df21583a0103f9/local-casi-backend-cellular.sh && sudo bash casi_script.sh
   ```
9. Connect to backend API server via SSH or open the terminal on the backend API server:
10. Run the following command in a server to launch the backend API web server:
    ```
    curl -sSL -o casi_script.sh https://gist.githubusercontent.com/casi-devops-team/60cd0a7efc4a831aa10005aee5cc31a3/raw/bc84f79d01d2432df3086bbfb8d7ba7c01a8765e/local-casi-backend.sh && sudo bash casi_script.sh
    ```
11. Run the following command in a server to launch the frontend web server:
    ```
    curl -sSL -o casi_script.sh https://gist.githubusercontent.com/casi-devops-team/91fc7200de48d65cf61214973f30cf2e/raw/09c1ad72793a4510f1e86b9d0caacf162ba069f2/local-casi-frontend.sh && sudo bash casi_script.sh
    ```
13. Visit `http://frontend-server-ip-address-or-hostname/`

    
