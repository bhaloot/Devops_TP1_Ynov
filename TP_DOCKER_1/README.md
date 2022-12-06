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

