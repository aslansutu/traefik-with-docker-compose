# Traefik with Docker Compose

Traefik is a reverse proxy that will allow different subdomains to open different docker containers. This negates the need to add the port number to the end of your URL, all traffic is done through the standard 80 and 443 ports, and all connections are SSL encrypted.

## Purpose

The purpose is; 
- To have Traefik run as its own service so that we can start and stop other web services without affecting Traefik
- The Traefik dashboard to be routed through Traefik
- Our routed sites to be SSL certified
- Allow Traefik to route to other Docker containers (which are in other docker-compose files)
  
To learn more, read the readmes inside each folder. 
