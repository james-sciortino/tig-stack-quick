# Create TIG Stack for Telemetry Streaming

Pre-Reqs:
1. Install Ubuntu 20.04
2. Install xrdp, ssh, curl, git
3. Install Docker <https://www.digitalocean.com/community/tutorials/
4. Make sure you can run docker commands without sudo
5. Initiate a Docker Swarm (docker swarm init) 
6. Install Docker Compose (sudo apt install docker-compose)
7. Install Portainer



TIG Deployment:
1. Add docker volumes during initial setup
- 'docker volume create --name=grafana-volume'
- 'docker volume create --name=influxdb-volume'
2. Set docker to swarm mode, 'docker swarm init'
3. Set passwords for .env file for initial database creation. You need to run nano .env and add your variables.
4. Start the containers: 'docker-compose up -d'
5. Login to grafana @ http://localhost:3000 ('admin:admin')
6. Setup Database
 -db: telegraf
 -dbuser: telegraf
 -dbpassword: Welcome1
 -http://influxdb:8086
 -basic auth - checked
 -username / password 
 - HTTP Method: GET
7. Save!
8. Setup your dashboards

References: Creating a TIG Stack: https://dev.to/project42/install-grafana-influxdb-telegraf-using-docker-compose-56e9)
Troubleshooting: 'docker-compose logs -f'

