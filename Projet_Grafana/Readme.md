## Projet Grafana

Pour le projet sur l'utilisation de grafanaet le monitoring qu'il permets, je me renseigne dans un premier temps avec la documentation : 
- Sur leur site 
- Sur youtube avec des videos explicative. 

Pour telecharger une image de grafana, il suffit de lancer la commande : 

```docker run  -d -p 30000:3000 --name Grafana grafana/grafana-oss ```

En cherchant sur internet, on trouve une image avec grafana, loki et prometheus. 
on la récupere de la maniere suivant : 
``` git clone https://github.com/shadinua/demo-grafana-loki-prometheus```

``` cd demo-grafana-loki-prometheus```  
``` docker-compose up```  