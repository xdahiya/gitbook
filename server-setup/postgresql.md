---
description: installation of postgresql in the ubuntu server
---

# Postgresql



```
sudo docker pull postgres 
docker volume create mernpgdata
sudo systemctl restart docker
```

```
sudo docker run --rm --name postgresql-db -e POSTGRES_USER=root -e POSTGRES_PASSWORD=Admin123 -v mernpgdata:/var/lib/postgresql/data -p 5432:5432 -d postgres
```

