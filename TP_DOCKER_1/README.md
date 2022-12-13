# COMPTE RENDU TP DOCKER 1
--- 
1. a.  

**Commande utilisé :** 

`docker pull nginx`

Récupération de l'image d'Nginx.
b. 

Pour verifier la présence en local on execute : 

`docker images`
 
 c. / d.

En suivant la documentation, on fait la commande suivante pour lancer le serveur sur le bon port: 

`` docker run -d -p8080:80 --name first_server -v ${PWD}\html:/usr/share/nginx/html nginx``

**ATTENTION:** Utilisation de ${PWD} (Print Working Directory) pour avoir le bon chemin de fichier qui est : *C:\Users\Edouard Abgrall\Documents\YNOV\Cours\DEVOPS\Devops_TP1_Ynov\TP_DOCKER_1\html*

f. 

 on relance avec la commande: 
 `docker run --name some_nginx -d -p8080:80  nginx`
 puis 
 ` docker cp ${PWD}\html some_nginx:/usr/share/nginx/html`


 4. a.

Pour builder une image, on utilise la commande 

` docker build -t webserver .`

le resultat qui retourne en console est 

`[+] Building 0.2s (7/7) FINISHED
 => [internal] load build definition from Dockerfile  0.0s
 => => transferring dockerfile: 31B                                                              0.0s
 => [internal] load .dockerignore                                                                0.0s
 => => transferring context: 2B                                                                  0.0s
 => [internal] load metadata for docker.io/library/nginx:latest                                  0.0s
 => [internal] load build context                                                                0.0s
 => => transferring context: 60B                                                                 0.0s
 => [1/2] FROM docker.io/library/nginx:latest                                                    0.0s
 => CACHED [2/2] COPY /html /usr/share/nginx/html/                                               0.0s
 => exporting to image                                                                           0.0s
 => => exporting layers                                                                          0.0s
 => => writing image sha256:24339bec065ed1f7956e695b607e97737906a2f8160a3a45a91e72e806022d69     0.0s
 => => naming to docker.io/library/webserver                                                     0.0s
`

A partir de cela, on peut voir dans nos images sur docker desktop la présence d'une image appelé ici 'webserver'. 

Il suffit de lancer ensuite la commande 

` docker run -it --rm -d -p 8080:80 --name web webserver`

on a maintenant un server web qui fonctionne.

b. 

En allant sur http://localhost:8080 on retrouve le hello world. 

c. 

La prinicipale difference est qu'avec un *dockerfile* on peut faire executement des commande dans l'ordre voulu et en une fois, ce qui permets au fur et a mesure de recréer une image sans avoir à la reconfigurer du début. 


5. a. 

Pour recuperer l'image Mysql on entre la commande ` docker pull mysql`. 

Pour executer le conteneur : 
` docker run --name mysql-TP -e MYSQL_ROOT_PASSWORD=my-secret-pw -d mysql`


Même chose pour recuperer l'image de PhpMyAdmin : 
`docker pull phpmyadmin`

b.

Après avoir récuperé l'image de PhpMyAdmin, il faut ensuite la run en la liant avec l'image de MySQL : 

` docker run --name phpmyadmin -d --link mysql-TP:db -p 8080:80 phpmyadmin`

*Se referer a l'image `MyAdmin.png`* 

6. a. 

La commande `docker compose` permet de lancer plusieur images, contenu dans un dockerfile. ce qui permet de builder une application et ses dependances e nune fois sans avoir a tout relancer un par un, à l'instar de `docker run` ou il faudrait rentrer un par un les images.

b.

Pour lancer : `docker compose up`

Pour stopper : `docker compose down`






