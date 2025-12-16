# Création d’une image Docker pour un projet web avec Nginx

## Le Dockerfile

```dockerfile
FROM nginx:alpine

# GIT
RUN apk add --no-cache git

# SUPPRESSION ANCIEN HTML
RUN rm -rf /usr/share/nginx/html/*

# CLONE /usr/share/nginx/html
RUN git clone https://github.com/withaarzoo/3D-Rotate-Tube.git /usr/share/nginx/html

# PORT 80
EXPOSE 80
```

## Démarrer le conteneur

```bash
# DEBUT
docker build -t rotate-tube-website .
docker run --name rotate-tube-website -d -p 8080:80 rotate-tube-website

# ACCES
http://localhost:8080

# FIN
docker stop rotate-tube-website
docker rm rotate-tube-website
docker rmi rotate-tube-website
```
