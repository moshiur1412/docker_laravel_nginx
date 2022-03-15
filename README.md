### MySQL Access Problem:
========================================================
```sh
1a) Connect to mysql (via localhost)

mysql -uroot -p

1b) If the mysql server is running in Kubernetes (K8s) and being accessed via a NodePort

kubectl exec -it [pod-name] -- /bin/bash
mysql -uroot -p

2) Create user

CREATE USER 'root'@'%' IDENTIFIED BY 'password';

3) Grant permissions

 GRANT ALL PRIVILEGES ON *.* TO 'user'@'%' WITH GRANT OPTION;

4) Flush priviledges

FLUSH PRIVILEGES;

docker exec -it mysql bash
mysql -uroot -p
CREATE USER 'root'@'%' IDENTIFIED BY 'root'; GRANT ALL PRIVILEGES ON *.* TO 'root'@'%' WITH GRANT OPTION;
GRANT ALL PRIVILEGES ON *.* TO 'root'@'%' IDENTIFIED BY 'password';

```

### Winpty problem solved
===========================
```sh
echo 'alias python="winpty python.exe"' >> ~/.bashrc
source ~/.bashrc
```


### Folder full permission
==============================
```sh
php artisan cache:clear
chmod -R 777 storage/
composer dump-autoload
```

# How to Do a Clean Restart of a Docker Instance
================================================
```sh
docker-compose down

Delete all containers:
docker rm -f $(docker ps -a -q)

Delete all volumes:
docker volume rm $(docker volume ls -q)

Restart the container:
docker-compose up -d
```
