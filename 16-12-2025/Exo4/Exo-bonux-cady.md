# Création d’une image Docker pour un projet web avec Caddy

## Le Dockerfile

```dockerfile
FROM caddy:alpine

# GIT
RUN apk add --no-cache git

# SUPPRESSION ANCIEN HTML
RUN rm -rf /usr/share/caddy/*

# CLONE /usr/share/caddy
RUN git clone https://github.com/withaarzoo/3D-Rotate-Tube.git /usr/share/caddy

# PORT 80
EXPOSE 80
```

## Démarrer le conteneur

```bash
# DEBUT
docker build -f Dockerfile.cady -t rotate-tube-caddy .
docker run --name rotate-tube-caddy -d -p 8081:80 rotate-tube-caddy

# ACCES
http://localhost:8081

# FIN
docker stop rotate-tube-caddy
docker rm rotate-tube-caddy
docker rmi rotate-tube-caddy
```
