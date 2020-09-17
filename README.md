# Create TIG Stack for Telemetry Streaming

Pre-Requisites:
1. Install Ubuntu 20.04
2. Install xrdp, ssh, curl, git
3. Install Docker.
4. Make sure you can run docker commands without sudo.
5. Initiate a Docker Swarm.
6. Install Docker Compose.

TIG Stack Deployment:
1. Create a folder anywhere to put your Git repository.
2. Navigate to the new directory and run 'git clone <this repository>'
3. Navigate to the new repository folder.
4. Add Docker volumes for your new containers:
- 'docker volume create --name=grafana-volume'
- 'docker volume create --name=influxdb-volume'
5. Set Docker to Swarm Mode, 'docker swarm init'
6. Create a new .env file by running 'nano .env' and add your eviornment variables:
 
INFLUXDB_ADMIN_USER=admin
INFLUXDB_ADMIN_PASSWORD=Welcome1
INFLUXDB_DB=telegraf
INFLUXDB_USER=telegraf
DYNACONF_EXPRESSWAY_USER=admin
DYNACONF_EXPRESSWAY_PASSWORD=admin

7. Review your docker-compose.yml file to be sure it's mounting to the right containerd and telegraf.conf
8. Start the containers by running 'docker-compose up -d'
9. Login to grafana @ http://localhost:3000 ('admin:admin'). Set a new password.
10. Setup a new database
 - URL: http://influxdb:8086
 - Basic Auth: Enabled
 - User: telegraf
 - Password: telegraf
 - Database: telegraf
 - UserDB: telegraf
 - PasswordDB: Welcome1
 - HTTP Method: GET
11. Save!
12. Setup your dashboards

References: Creating a TIG Stack: https://dev.to/project42/install-grafana-influxdb-telegraf-using-docker-compose-56e9)
Creating a TIG Stack: https://codeofconnor.com/2019/11/deploying-the-telegraf-influxdb-grafana-tig-stack-with-docker-to-monitor-a-linux-host/
Troubleshooting: 'docker-compose logs -f'

