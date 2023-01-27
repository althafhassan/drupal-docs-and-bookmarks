---
title: 'Copying container locally'
---

1. Accessing the Container. In this case mariadb.

docker exec -it mariadbtest bash

https://mariadb.com/kb/en/installing-and-using-mariadb-via-docker/#accessing-the-container

2. Get container id
 
 docker ps.

3. Copy Container to local.

docker cp bb3c39.....:/var/lib/mysql /{PATHTOCOPY}