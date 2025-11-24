# TP

## Partie 1

```bash
docker run -d --name game-2048 -p '2048:80' fanvinga/docker-2048
http://localhost:2048
docker run -d --name game-2048-2 -p '20482:80' fanvinga/docker-2048
http://localhost:20482

docker ps
docker stop game-2048 game-2048-2
docker ps -a
docker start game-2048-2
http://localhost:20482

docker stop game-2048 game-2048-2
docker rm game-2048 game-2048-2
docker rmi fanvinga/docker-2048
```

## Partie 2
```bash
docker run -d --name nginx-web -p '80:80' nginx:1.29.3
http://localhost

docker exec -it nginx-web sh
cd /usr/share/nginx/html/
apt update
apt install nano -y
nano index.html
# UPDATES...
# Ctrl-S Ctrl-X
http://localhost
exit

docker stop nginx-web

docker run -d --name apache-web -p '80:80' httpd:2.4.65
http://localhost

docker exec -it apache-web sh
cd /usr/local/apache2/htdocs
apt update
apt install nano -y
nano index.html
# UPDATES...
# Ctrl-S Ctrl-X
http://localhost
exit
docker stop apache-web

docker rm nginx-web apache-web
docker rmi nginx:1.29.3 httpd:2.4.65
```

## Partie 3
```bash
docker run -d --name nginx-web3 -p '83:80' nginx:1.29.3
docker run -d --name nginx-web4 -p '84:80' nginx:1.29.3
docker run -d --name nginx-web5 -p '85:80' nginx:1.29.3

docker cp html5up-editorial-m2i.zip nginx-web3:/usr/share/nginx/html/
docker cp html5up-massively.zip nginx-web4:/usr/share/nginx/html/
docker cp html5up-paradigm-shift.zip nginx-web5:/usr/share/nginx/html/

docker exec nginx-web3 sh -c "apt update && apt install -y unzip && unzip -o /usr/share/nginx/html/html5up-editorial-m2i.zip -d /usr/share/nginx/html/"
docker exec nginx-web4 sh -c "apt update && apt install -y unzip && unzip -o /usr/share/nginx/html/html5up-massively.zip -d /usr/share/nginx/html/"
docker exec nginx-web5 sh -c "apt update && apt install -y unzip && unzip -o /usr/share/nginx/html/html5up-paradigm-shift.zip -d /usr/share/nginx/html/"

http://localhost:83/html5up-editorial
http://localhost:84
http://localhost:85
```
