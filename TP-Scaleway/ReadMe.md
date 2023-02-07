Skip to content
Product
Solutions
Open Source
Pricing
Search
Sign in
Sign up
bhaloot
/
Devops_TP_Ynov
Public
Code
Issues
Pull requests
Actions
Projects
Security
Insights
Update readme + question TP
 main
@bhaloot
bhaloot committed 3 weeks ago 
1 parent 9757b17 commit c1f6ee60141a5310ef74ef1b4027559b430a68d8
Showing 1 changed file with 83 additions and 0 deletions.
 83  
tp_docker_2_devops/ReadMe.md
@@ -0,0 +1,83 @@
## TP Scaleway 

- Après avoir rejoint Scaleway et copié le TP2, on se connecte grace à la commande sur le TP 

```docker login rg.fr-par.scw.cloud/ynov-devops-container-registry -u nologin --password 56632f00-b4e9-43fd-bf72-05ca1c370b7b```
- on crée un dockerFile dans lequel on rajoute :
 ``` ENV PORT 3000  ``` ET ``` EXPOSE 3000 ```
 - on rajoute dans *server.js* : 
 
 ```app.listen(process.env.PORT || 3000 ``` 
 - on crée un dockerignore pour eviter de recuperer les node_modules enre autre. 
 - on publie ensuite l'image sur SCALEWAY : 
 ``` docker push rg.fr-par.scw.cloud/ynov-devops-container-registry/scaleway:latest```
 ## Q1:
 - C'est important car cela permet une plus grande évolutivité, l'application pouvant facilement traiter plusieurs demandes provenant de différents utilisateurs en même temps sans interférer les unes avec les autres. En outre, les applications sans état sont plus tolérantes aux pannes, car l'absence d'informations d'état signifie qu'aucune donnée ne peut être perdue ou corrompue en cas de défaillance d'un serveur
 ## Q2 : 
 - Oui, il est possible de créer des volumes et de les lier à un conteneur sans serveur. Bien que le *serverless* se réfère généralement à la capacité d'exécuter du code sans provisionner ou gérer des serveurs, cela ne signifie pas qu'il n'y a pas d'infrastructure sous-jacente
 ## Q4 : 
 - Le cout varie en fonctio de l'utlisation des ressources utilisés, donc si l'application est nouvelle et en test, le cout est moindre. 
 En revanche, si le besoin de calcul est plus elevé, alors il faut comparer regulierement pour profiter du plus avantageux. 
 ## Q5 : 
 - le dimensionnage des ressources pour gerer le pics de charge. 
 - la durée d'éxécution, 
 - la latence, des temps de réponse plus élévé car il y a un demarrage a chaque invocation 
 - le monitoring, pour journaliser les informations et résoudre les problemes
 ## Q6 : 
- Utiliser Scaleway's Object Storage pour stocker les fichiers statiques de l'application.
- Utiliser Scaleway's Virtual Cloud Instances pour héberger les instances de l'application.
- Utiliser un service de base de données cloud tiers pour héberger la base de données de l'application. 
- Utiliser Scaleway's Load Balancer pour répartir les requêtes entre les différentes instances de l'application.
- Utiliser Scaleway's Managed Kubernetes pour gérer les conteneurs de l'application et les instances de bases de données.
- Utiliser Scaleway's Monitoring et Logging pour surveiller les performances de l'application
- Utiliser Scaleway's Security Groups pour protéger les accès à l'application, les instances et les bases de données.
- Utiliser Scaleway's Cloud Firewall pour protéger les accès à l'application, les instances et les bases de données contre les attaques courantes.
## Q7: 
- On preferera utiliser une BDD cloud pour : une meilleure disponibilité, la sécurité, la flexibilité pour adapter au besoins changeant de l'application et la réduction des coûts
## Q8 : 
 les avantages sont : 
 - la possibilité d'evolution 
 - la flexibilité pour s'adadpter au besoins 
 - les couts 
 - la securité
- la maintenance
les inconveniants : 
- la dépendance 
- les couts ( lorsque l'applicaiton prends de l'ampleur)
- le transfert de données. 
## Q9 : 
- Oui, Dans mon cas, Sopra Steria utilise des services tels que AWS, Azure et Google cloud platform. 
Mais je ne sais pas pourquoi ils les utilisent je n'y suis pas confronté. 
0 comments on commit c1f6ee6
Please sign in to comment.
Footer
© 2023 GitHub, Inc.
Footer navigation
Terms
Privacy
Security
Status
Docs
Contact GitHub
Pricing
API
Training
Blog
About
Update readme + question TP · bhaloot/Devops_TP_Ynov@c1f6ee6 · GitHub