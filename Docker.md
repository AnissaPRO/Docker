#Executer un serveur web

- Dans un premier temps nous allons récupérér une image officielle sur le Docker HUB.

Grâce à la commande suivante :

```sh
docker pull nginxinc/nginx-unprivileged
```
- Je vérifie que l'image est bien présente en locale avec la commande :
```sh
docker images
```
Nous créeons un fichier index.html

- Nous allons démarrer un conteneur grâce à la commande :
```sh
docker run -d -p 8080:8080 -v C:/Users/Anissa/Desktop/Licence/Ynov/DevOps/Docker:/usr/share/nginx/html nginxinc/nginx-unprivileged:latest
```
 (ici la deuxième valeur est 8080 car l'image choisie spécifie que le port par défaut n'est plus 80 mais 8080)
 
 - Pour arrêter un conteneur on fera 
 ```sh
 docker  IdConteneur
 ```
 
 - Pour récupérer son id on se rend dans la liste des conteneurs. Pour rappelle pour afficher les conteneurs existants :
 ```sh
 docker ps -a
 ```
 - Pour supprimer un docker :
 ```sh
 docker rm IdDocker
 ```
 - Pour afficher le contenu d'un fichier avec son chemin sur mon terminal
 ```sh
 cat
 ```
 - Nous allons ensuite supprimer le conteneur précédent, créer un nouveau conteneur Sans volume :
 ```sh
 docker run -d -p 8080:8080  nginxinc/nginx-unprivileged:latest
 ```
 - Puis on va copier notre fichier index.html dans notre conteneur avec la commande :
 ```sh
 docker cp C:/Users/Anissa/Desktop/Licence/Ynov/DevOps/Docker/index.html 7cba0f1692d5:/usr/share/nginx/html
 ```