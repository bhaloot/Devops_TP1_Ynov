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


