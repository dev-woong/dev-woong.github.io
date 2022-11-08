---
date: 9999-01-01
tags: [ Note , Server]
---

# Docker Container
1. TeamCity Server
	docker run --network yunwoopc-dev -it -d --name server -u root -v data:/data/teamcity_server/datadir -v logs:/opt/teamcity/logs -p 8112:8111 j
etbrains/teamcity-server
2. MariaDB Server
	docker run --detach --network yunwoopc-dev --name mariadb --env MARIADB_USER=yunwoo --env MARIADB_PASSWORD="<PASSWORD>" --env MARIADB_ROOT_PASSWORD="<ROOT PASSWORD>"  mariadb:latest