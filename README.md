# CASI Local Installation Manual

### Recommended Requirements:
 - Ubuntu Web Server

#### Server Requirements:
- 4 vCPUs
- 16GB RAM
- 50GB Storage
- Intel 64bit CPU Architecture
- Ubuntu 20.04

### Installation
1. Connect to the server via SSH or go to terminal.
3. Run the following command and follow the instructions to launch the mqtt broker.
   ```
   curl -sSL -o casi_script.sh https://gist.githubusercontent.com/janith-jware/3e61a463f7a88d72f6051672e53123e2/raw/c0f6a4ea4a939450552f44280751d13a2d70192f/casi-local-instant-installation.sh && sudo bash casi_script.sh
   ```

   Notes:
   - You will be asked to enter the frontend server IP address or hostname once you run the command above. If it is a public server, you may either mention the public IP address of the server or any domain name that is pointed to that server. If you intend access the system across your Local Area Network (LAN), mention the local IP address of your server within the LAN. If you wish to use the app in the same local computer only, mention either `127.0.0.1` or `localhost`.
    
2. Visit `http://frontend-server-ip-address-or-hostname:8000/` and activate your license.
   - The server must accept inbound traffic through port 8000. Configure the firewall to enable these ports. We recommend you to get support of a professional for firewall configuaration.
4. Run the following command to reload the app.
   ```
   sudo docker restart casi-backend
   ```
5. Visit `http://frontend-server-ip-address-or-hostname/`.
   
    
