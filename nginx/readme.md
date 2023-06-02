# Web Service with Traefik

This is just an example web service. You can take this template and apply it to any other web service you would want to start.

With Traefik, there is no need to specify or expose ports in the container. Traefik will automatically route to it. 

However, your services need to talk to each other (like with Wordpress), then create a new Docker network and have your services communicate through this network.

### To Apply to Another Web Service

In your docker compose file, under the label argument add the following;

```yml
labels:
      - "traefik.enable=true"
      - "traefik.docker.network=traefik-proxy"
      - "traefik.http.routers.whoami.rule=Host(`domain.name`)"
      - "traefik.http.routers.whoami.entrypoints=websecure"
      - "trafeik.http.routers.whoami.tls=true"
      - "traefik.http.routers.whoami.tls.certresolver=production" # May want to try staging before production as production has a rate limit
```
Make sure to change the `domain.name` to domain name you want that web service to route to. 
This allow Traefik to connect to this container.

### Run

To run, change `domain.name` to your own domain for this web service. Afterwards run `docker compose up -d` 

### Stop

To stop, run `docker compose down`