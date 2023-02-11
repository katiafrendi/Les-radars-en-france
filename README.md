# ProjetDatavisualisation Les Radars en France 
<iframe width="853" height="480" src="https://www.youtube.com/embed/uB8g0dz_CA0" title="Comment fonctionnent les radars routiers ?" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
*Créateur : typhoonski, Droits d'auteur : typhoonski*

# Table des matières
## Choix du sujet 
La sécurité sur les routes est un enjeu majeur pour éviter les accidents et les blessures graves ou mortelles. C'est pourquoi il est important de respecter les règles de conduite. L'État a installé des radars pour surveiller les conducteurs, les contrôler et les sanctionner, dans le but de dissuader ceux-ci de rouler à des vitesses excessives.
Ma problématique vise à répondre aux questions suivantes :
- Comment sont répartis les radars en France ?
- Quels types de radars existent en France ?
- Est-ce qu'il existe une relation entre la baisse des accidents de la route et l'installation de radars ?
- Dans quels départements le taux d'accidents est-il le plus élevé ?

## Origine et traitement des données  <a id="som1"></a>
### A. Jeu de données n°1 : Répartition des radars en France <a id="som1a"></a> 

les données concernant les quelques 3000 radars automatiques en France. Informe de l'emplacement précis, de la route, de la direction, du type, de la vitesse contrôlée, de la date d'installation. Vous pouvez en apprendre plus sur une page dédiée sur le site de la sécurité routière.
Ce jeu de données utilise comme source le site du Ministère de l'Intérieur , que j'ai pu extraire à partir du site [data.gouv] (https://www.data.gouv.fr/fr/datasets/radars-automatiques/), j'ai pu effectuer un sprint qualité afin d'évaluer la qualité de ces données afin de les épurées. Les données sont de qualité nous remarquons l'absence de certaines données pour les dernières ligne de mon nfichier ce qui n'est pas très impactant car c'est relatif à la diretion auxquel sont rataché les radars. J'ai pu utiliser open refin afin d'effectuer certaines modification et de parveir à ce réultat final.
Extrait des données sur les radars.
<iframe title="Les radars de France" aria-label="Table" id="datawrapper-chart-9MmYJ" src="https://datawrapper.dwcdn.net/9MmYJ/1/" scrolling="no" frameborder="0" style="width: 0; min-width: 100% !important; border: none;" height="1608" data-external="1"></iframe><script type="text/javascript">!function(){"use strict";window.addEventListener("message",(function(e){if(void 0!==e.data["datawrapper-height"]){var t=document.querySelectorAll("iframe");for(var a in e.data["datawrapper-height"])for(var r=0;r<t.length;r++){if(t[r].contentWindow===e.source)t[r].style.height=e.data["datawrapper-height"][a]+"px"}}}))}();</script>
 
### B. Jeu de données n°2 :  les  les accidents corporels de la circulation routière (2010-2020) <a id="som1a"></a> 

Le second jeu de donnée va concerner les accidents corporels de la circulation routière enregistrés par les forces de l'ordre, ainsi que les victimes de ces accidents, en France métropolitaine et outre-mer, ces 10 dernières années jusqu'en 2020 (dernière année officielle). Les données sur les accidents de la route en France sont gérées par des organismes tels que l'Observatoire National Interministériel de la Sécurité Routière (ONISR) et téléchargé à partur sur site [Data.gouv] (https://www.data.gouv.fr/fr/datasets/bases-de-donnees-annuelles-des-accidents-corporels-de-la-circulation-routiere-annees-de-2005-a-2021/) 
 
## Visalaisation de la répartition des radars sur l'ensemble du teriitoir francais 
Utilisation de umap pour une visualisation dynamyque fonctionnalité de zoom plus performante 
 
 une concentration de radars plus en région francilienne 
<iframe width="100%" height="300px" frameborder="0" allowfullscreen src="//umap.openstreetmap.fr/fr/map/repartition-des-radars-en-france_867205?scaleControl=false&miniMap=false&scrollWheelZoom=false&zoomControl=true&allowEdit=false&moreControl=true&searchControl=null&tilelayersControl=null&embedControl=null&datalayersControl=true&onLoadPanel=undefined&captionBar=false&datalayers=2623604"></iframe><p><a href="//umap.openstreetmap.fr/fr/map/repartition-des-radars-en-france_867205">Voir en plein écran</a></p>

NB: la vitesse limité par le radar n'est pas renseigné pour les radars de type "feu rouge" mais plutot pour les radars "fixe"
## Visualisation des differents types de radars <a name="TypeRadars"></a>
![Les types de radars  (1)]![Les types de radars ](https://user-images.githubusercontent.com/121629941/217388626-c5d449c1-73ef-4e61-b488-fda81a097d8f.png)


  
### B. Jeu de données n°2 : les accidents de la route <a id="som1b"></a>

2) Les données sur les accidents de la route sont issues de ( à voir)
https://www.data.gouv.fr/fr/datasets/bases-de-donnees-annuelles-des-accidents-corporels-de-la-circulation-routiere-annees-de-2005-a-2021/
https://www.data.gouv.fr/fr/datasets/base-de-donnees-des-accidents-corporels-de-la-circulation/
## Pourquoi les radars 
1/La décision d’implanter un radar s’effectue sur des sites où se produisent un nombre d’accidents corporels supérieur à la moyenne, où la vitesse est souvent en cause dans la survenance de ces accidents et où les contrôles sont difficiles à réaliser avec des moyens humains.
2/Le déploiement de radars automatiques en France est intervenu dès 2003 dans l’optique de réduire le nombre de tués sur les routes.

Les dates-clés du contrôle automatisé
https://www.securite-routiere.gouv.fr/radars/chiffres-radars/historique-des-radars

## Radars et baisse de la mortalité routière
###Croisement de doonnées 
Les conducteurs ont considérablement réduit leur vitesse moyenne, passant de 91 km/h à 80 km/h. Cela a contribué à une baisse moyenne des accidents mortels à proximité des radars de 66 %. En 10 ans, entre 2003 et 2012, les radars ont permis de sauver 23 000 vies. 
PS: les donénes concernant l'année 2018 étaient pas disponile pour des raison inconnues 
<div class="flourish-embed flourish-hierarchy" data-src="visualisation/12681434"><script src="https://public.flourish.studio/resources/embed.js"></script></div>
#Utilisation des outils de datavisualiation 
##utilisation de l'outil paladio cependant les données traité par l'outil sont non exportablee donc en sois l'outil m'a permis de mieux comprendre et assimilité les données, avoir une première impression des données et vérifier la qualité de mes données = > capture video avec les filtres paladio 
je passe à l'utilisation de l'outil rawgraph avec l'avantage d'exporter les données


https://www.onisr.securite-routiere.gouv.fr/outils-statistiques/open-data



Taux de mortalité en 2020 en  fonction des département 
<div class="flourish-embed flourish-hierarchy" data-src="visualisation/12680915"><script src="https://public.flourish.studio/resources/embed.js"></script></div>
## Visualisation des lieux d'accident les plus courant avec Wikidata Query Service
Il n'est pas possible d'avoir un résultat de reqête assez pertinent car les informations relatives aux accidents de la route ne sont pas toujours disponibles dans Wikidata. Par ailleurs, il est peu probable que des images des sites d'accidents de la route en France soient disponibles, étant donné que ces événements sont souvent tragiques et sensibles.
 
 
```sparql
#defaultView:ImageGrid
select distinct ?item ?itemLabel ?img
where {
  ?item wdt:P31 wd:Q9687 .
  ?item wdt:P17 wd:Q142 .
  ?item wdt:P18 ?img . 
    SERVICE wikibase:label { bd:serviceParam wikibase:language "[AUTO_LANGUAGE],en, fr" } }
 ```
 <iframe style="width: 80vw; height: 50vh; border: none;" src="https://query.wikidata.org/embed.html#%23defaultView%3AImageGrid%0Aselect%20distinct%20%3Fitem%20%3FitemLabel%20%3Fimg%0Awhere%20%7B%0A%20%20%3Fitem%20wdt%3AP31%20wd%3AQ9687%20.%0A%20%20%3Fitem%20wdt%3AP17%20wd%3AQ142%20.%0A%20%20%3Fitem%20wdt%3AP18%20%3Fimg%20.%20%0A%20%20%20%20SERVICE%20wikibase%3Alabel%20%7B%20bd%3AserviceParam%20wikibase%3Alanguage%20%22%5BAUTO_LANGUAGE%5D%2Cen%2C%20fr%22%20%7D%20%7D%0A" referrerpolicy="origin" sandbox="allow-scripts allow-same-origin allow-popups"></iframe>
 PS: je souligne la complexité d'effectuer une reqête avec car Wikidata ne peut pas être considérée comme une source fiable pour obtenir des données en temps réel sur la sécurité routière et la circulation, car elle se concentre principalement sur la collecte et l'organisation d'informations structurées et historiques sur des sujets tels que des événements, des personnes, des lieux et des œuvres d'art. 
 
 <div class="flourish-embed" data-src="story/1825342"><script src="https://public.flourish.studio/resources/embed.js"></script></div>

