# Vaultwarden-Demo
Easy setup for Vaultwarden: an unofficial reinterpretation of Bitwarden in Rust
## Dependencies
This project assumes that you have the following:
- Docker installed: Follow [this](https://docs.docker.com/get-docker/) tutorial if you do not have this requirement fulfilled
- caddy binary in your working directory: To work with this repository, you must install caddy [here](https://caddyserver.com/download). Include your platform and the DuckDNS plugin in your binary
- firewall rules that allow ingress traffic to ports 80/443 
## Usage
Make sure to follow the instructions in the docker-compose file to edit the appropriate labels. For a quick instance using docker compose, run the following command: <br />
`docker compose up -d` <br />
I recommend you use a container orchestration technology if you plan on using this project as a template for production. Docker swarm is able to use docker-compose files using the following command:<br />
`docker network create -d overlay test-network && docker stack deploy --compose-file docker-compose.yml test-network` <br />
## Issues and Considerations
<b>**This deployment is not recommended for public use. Note the following issues with using this repository in production**</b>
- Caddy container is running as root
- Vaultwarden container is running as root
- Several offline backups should be taken and stored securely 
- 24/7 Availability should be ensured when self-hosting your own password manager
