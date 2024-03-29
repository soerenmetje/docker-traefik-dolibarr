# Dolibarr

> :warning: **Update:** now a similar setup is available in [tuxgasys' repository](https://github.com/tuxgasy/docker-dolibarr/tree/master/examples/with-rp-traefik).

Setup for [**Dolibarr**](https://www.dolibarr.org/) running inside a **Docker Container** connected to [**Traefik:v2.4**](https://doc.traefik.io/traefik/v2.4/) (reverse proxy). 

This setup is for an external webserver serving Dolibarr. 
Dolibarr will be available by a subdomain f. e. doli.domain.com. 
Corresponding certificates for **https** are automatically generated by Traefik. 
This ensures the secure data transmission. A **MariaDB** stores Dolibarrs' data persistently.

[tuxgasys' Dolibarr Docker images](https://hub.docker.com/r/tuxgasy/dolibarr) are used. 
Therefor Dolibarr will be installed automatically on first start.

## Prerequisites
- Your subdomain points to your webserver
- Docker installed
- Docker-Compose installed 

## Setup
1. Clone this repository: 
```git clone https://github.com/soerenmetje/docker-traefik-dolibarr.git```
2. Traefik
   1. Change dir to `traefik`
   2. Insert your configuration to `docker-compose.yml`  (lines are marked by TODO)
   3. Start Container ```docker-compose up -d```
   4. Wait until start is finished
3. Dolibarr & DB
   1. Change dir to `dolibarr`
   2. Insert your configuration to `docker-compose.yml`  (lines are marked by TODO)
   3. Start Container ```docker-compose up```
   4. Make a Tee and wait until auto-install of Dolibarr is finished (can take 5 to 10 min)
4. Check if Dolibarr is reachable
   
## Additional Information
- In order to add additional arbitrary services to Traefik:
   1. Add `traefik-net` to this service
   2. Add customized labels to the `labels` section of this service
## TODOs
- Add and test volume (/var/www/documents) to store generated documents persistently

## References
- https://hub.docker.com/r/tuxgasy/dolibarr - Thanks to Garcia MICHEL (tuxgasy)
- https://github.com/tuxgasy/docker-dolibarr 
- https://doc.traefik.io/traefik/v2.4/