# Les radars routiers en france

Les radars routiers sont des dispositifs de contrôle de la vitesse des véhicules sur les routes, et ils jouent un rôle crucial dans la sécurité routière. En mesurant la vitesse des véhicules, les radars routiers aident à prévenir les accidents de la route en encourageant les conducteurs à respecter les limites de vitesse et à conduire prudemment.
Les radars routiers sont également utiles pour l'application des lois et des règlements de la circulation. Les autorités peuvent utiliser les données collectées par les radars routiers pour identifier les zones à risque et pour planifier des mesures de sécurité routière.
Voici une vidéo qui explique le fonctionnement des radars de manière didactique.

<iframe width="853" height="480" src="https://www.youtube.com/embed/4E9TKXSK5CI" title="Fonctionnement du radar" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>


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

les données concernant les 3000 radars automatiques en France. Informent de l'emplacement précis, de la route, de la direction, du type, de la vitesse contrôlée, de la date d'installation.
Ce jeu de données utilise comme source le site du Ministère de l'Intérieur, j'ai pu extraire à partir du site [data.gouv](https://www.data.gouv.fr/fr/datasets/radars-automatiques/). J'ai effectué une analyse qualité (sprint qualité) rigoureuse des données et appliqué des procédés de purification. Les données sont de qualité satisfaisante, bien qu'il soit possible de constater certaines omissions pour les dernières entrées de mon fichier, lesquelles sont toutefois peu significatives, étant donné qu'elles sont liées à la direction des radars. Pour corriger les irrégularités identifiées.

j'ai eu recours à OpenRefine, par exemple pour ajouter une anneé de création : 
```sparql
value.match(/.*(\d{4}).*/)[0]
```
ce qui a conduit à l'obtention des résultats finaux, ci-dessous un aperçu des données relatives aux radars.


| anneeCreation | departement | latitude  | longitude | equipement | type            | emplacement         |
|---------------|-------------|-----------|-----------|------------|-----------------|---------------------|
| 2018          | 57          | 49.11907  | 6.20408   | FARECO     | Radar feu rouge | METZ                |
| 2018          | 80          | 49.95842  | 2.85479   | MORPHO     | Radar fixe      | HEM MONACU          |
| 2018          | 91          | 48.67029  | 2.27976   | MORPHO     | Radar fixe      | LA VILLE DU BOIS    |
| 2018          | 91          | 48.63212  | 2.4065    | MORPHO     | Radar fixe      | COURCOURONNES       |
| 2018          | 78          | 48.83313  | 2.08501   | MORPHO     | Radar fixe      | BAILLY              |
| 2018          | 86          | 46.55483  | 0.28342   | MORPHO     | Radar fixe      | VOUNEUIL SOUS BIARD |
| 2018          | 67          | 48.57066  | 7.73904   | MORPHO     | Radar fixe      | STRASBOURG          |


> Tableau généré avec [Tables Generator](https://www.tablesgenerator.com)
NB: la vitesse limité par le radar n'est pas renseigné pour les radars de type "feu rouge" mais plutot pour les radars "fixe"


### B. Jeu de données n°2 :  les  les accidents corporels de la circulation routière (2010-2020) <a id="som1a"></a> 

Le second jeu de donnée va concerner les accidents corporels de la circulation routière enregistrés par les forces de l'ordre, ainsi que les victimes de ces accidents, en France métropolitaine et outre-mer, ces 10 dernières années jusqu'en 2020 (dernière année officielle). Les données sur les accidents de la route en France sont gérées par des organismes tels que l'Observatoire National Interministériel de la Sécurité Routière (ONISR) et téléchargé à partir du site [data.gouv](https://www.data.gouv.fr/fr/datasets/bases-de-donnees-annuelles-des-accidents-corporels-de-la-circulation-routiere-annees-de-2005-a-2021/)
J'ai fusionné plusieurs jeux de données annuels en un seul fichier, étant donné que les informations étaient initialement éparpillées sur plusieurs enregistrements. De plus, j'ai amélioré la présentation des colonnes pour obtenir des données de qualité.
 
## Visualaisation de la répartition des radars sur l'ensemble du teriitoir francais 
Pour ce premier jeu de donneés j'ai eu recours à l'utilisation de umap pour une visulasation dynamyque c'est à dire la possibilité de zoomer pour avoir l'emplacement exact des radars.
On constate : 

Il est possible de suggérer qu'une concentration importante de radars dans la région francilienne est liée à la densité de la population dans cette région. En effet, étant donné qu'il y a plus de personnes et de véhicules sur les routes, il est probable que la sécurité routière soit une préoccupation majeure dans cette région, justifiant ainsi une surveillance accrue. Cependant, il convient également de prendre en compte d'autres facteurs tels que les taux d'accidents et d'infractions au code de la route dans la région, ainsi que les politiques de sécurité routière mises en place par les autorités locales et nationales. Ces facteurs seront explorés plus en détail dans les prochaines visualisations.

<iframe width="100%" height="300px" frameborder="0" allowfullscreen src="//umap.openstreetmap.fr/fr/map/repartition-des-radars-en-france_867205?scaleControl=false&miniMap=false&scrollWheelZoom=false&zoomControl=true&allowEdit=false&moreControl=true&searchControl=null&tilelayersControl=null&embedControl=null&datalayersControl=true&onLoadPanel=undefined&captionBar=false&datalayers=2623604"></iframe><p><a href="//umap.openstreetmap.fr/fr/map/repartition-des-radars-en-france_867205">Voir en plein écran</a></p>

## Visualisation des differents types de radars <a name="TypeRadars"></a>

Dans cette deuxième visualisation réalisée à l'aide de l'outil Rawgraph, un diagramme Treemap a été utilisé pour mettre en évidence la disponibilité des différents types de radars dans le territoire. On observe que les radars fixes sont les plus répandus sur l'ensemble du territoire, mais principalement dans les départements 78 et 92. Les radars feu rouge sont le deuxième type de radar le plus disponible, suivis par les radars discriminants, tandis que les trois autres types de radars sont moins présents.

![viz](https://user-images.githubusercontent.com/121629941/218332270-64328c76-3000-4e8b-af0e-6f28a9885b17.png)


## Radars et baisse de la mortalité routière
J'ai utilisé l'outil Flourish pour créer ma troisième visualisation, qui présente le taux de mortalité sur les routes en France entre 2010 et 2020. Globalement, on constate une tendance à la baisse, malgré quelques augmentations observées en 2017 et 2015. Il est possible d'expliquer les raisons pour lesquelles il y a eu un nombre élevé de morts sur les routes en France en 2017, notamment des comportements à risque tels que la vitesse excessive, la conduite sous l'influence de l'alcool ou de drogues, ou le non-respect des règles de conduite. Il convient toutefois de noter que le taux de mortalité a nettement diminué en 2020.

Des études en sécurité routière ont montré que les conducteurs ont significativement réduit leur vitesse moyenne, passant de 91 km/h à 80 km/h, ce qui a contribué à une baisse moyenne de 66% des accidents mortels à proximité des radars. Au cours de la période de 10 ans entre 2003 et 2012, les radars ont permis de sauver 23 000 vies. 

<div class="flourish-embed flourish-hierarchy" data-src="visualisation/12681434"><script src="https://public.flourish.studio/resources/embed.js"></script></div>

Il convient de noter que les données relatives à l'année 2018 n'étaient pas disponibles pour des raisons inconnues.

## Taux de mortalité routière en 2020 en fonction des départements français

Le taux de mortalité routière en France en 2020 a été impacté par la pandémie de Covid-19, qui a entraîné une baisse significative des déplacements et donc du trafic routier. Selon les données de l'Observatoire national interministériel de la sécurité routière (ONISR), le nombre de personnes tuées sur les routes françaises en 2020 a atteint un plus bas historique depuis la création de cet observatoire en 1948, avec 2 550 décès enregistrés. Cela représente une baisse de 21,5 % par rapport à l'année précédente, où 3 244 personnes ont été tuées sur les routes.

<div class="flourish-embed flourish-hierarchy" data-src="visualisation/12680915"><script src="https://public.flourish.studio/resources/embed.js"></script></div>

Pour finir, Tous les indicateurs de la sécurité routière ont connu une amélioration en 2020, notamment le nombre d'accidents corporels (- 19 %) et le nombre de blessés hospitalisés (- 22 %). Cependant, malgré ces chiffres encourageants, il est important de continuer à promouvoir une conduite responsable et respectueuse des règles de sécurité routière afin de maintenir cette tendance à la baisse.
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

