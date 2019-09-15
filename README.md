# postgres-pgadmin-docker


Make a directory for volume: 

	$mkdir -p $HOME/docker/volumes/postgres

Run Postgres DB:

	$docker run --rm --name pg-docker -e POSTGRES_PASSWORD=docker -d -p 5432:5432 -v $HOME/docker/volumes/postgres:/var/lib/postgresql/data postgres

Run PgAdmin:

	$docker run -p 80:80  -e "PGADMIN_DEFAULT_EMAIL=user@domain.com" -e "PGADMIN_DEFAULT_PASSWORD=SuperSecret" -d dpage/pgadmin4
 
Find an IP address:

	$docker network ls
	$docker network inspect bridge
    "Name": "pg-docker",
    "EndpointID": "",
    "MacAddress": "",
    "IPv4Address": "172.17.0.2/16",

Browser:
	
	Type 0.0.0.0
	Email: user@domain.com
	PW: SuperSecret
  
Pgadmin-Connect Server
	
	Name: pg-docker
	Connection:
    Host name/address: 172.17.0.12
    Username: postgres
    PW: docker
  
  
Reference:
  https://hackernoon.com/dont-install-postgres-docker-pull-postgres-bee20e200198
  https://www.pgadmin.org/docs/pgadmin4/latest/container_deployment.html
