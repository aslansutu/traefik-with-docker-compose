# Traefik with Docker Compose

### Run

To run, edit the lines inside `traefik.yml` to include your email. Also copy `sample.env` as `.env` and edit the variable to reflect your own domain name that will get routed. Afterwards run `docker compose up -d` and then navigate to said url. When running for the first time, it may take a moment for the certificates to generate.

### What Will Happen

SSL certs will be generated inside the certs folder. 

Traefik will run according to the traefik.yml configuration file. When running Traefik with a `traefik.yml` file, you can make changes to the file and the changes will be reflected without restarting the container. 

If other docker-compose files have the same network as the network specified here, then those containers will also be able to take advantage of Traefik.

The label arguments allow the Traefik dashboard to be routed through Traefik so the default port of 8080 is not exposed. 

### Stop

To stop, run `docker compose down`