# Create TIG Stack for Telemetry Streaming

Pre-Reqs:
1. Install Ubuntu 20.04
2. Install xrdp, ssh, curl
3. Install Docker Compose <https://docs.docker.com/compose/install/>
4. Install Portainer <https://www.portainer.io/installation/>
5. Open Portainer and verify that it is linked to your Docker installation


TIG Deployment:
1. Add docker volumes during initial setup
- 'docker volume create --name=grafana-volume'
- 'docker volume create --name=influxdb-volume'
2. Set docker to swarm mode, 'docker swarm init'
3. Set passwords for .env file for initial database creation.
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

