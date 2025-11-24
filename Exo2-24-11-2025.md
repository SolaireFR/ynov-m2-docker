# Modification fichier dans Alpine

```bash
docker run -it --name mon_alpine alpine sh
apk add git
git clone https://github.com/SolaireFR/ynov-m2-docker
apk add nano
cd ynov-m2-docker/
echo 'Avant ^_^' > exo2-24-11-2025-testfile.txt
cat exo2-24-11-2025-testfile.txt
# Affiche Avant ^_^
nano exo2-24-11-2025-testfile.txt
# Effectuer les modifs
# Ctrl-S Ctrl-X
cat exo2-24-11-2025-testfile.txt
```

Si besoin de le modifier apres fermeture du terminale :
```bash
docker exec -it mon_alpine sh
```
