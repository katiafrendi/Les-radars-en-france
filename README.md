# ProjetDatavisualisation Les Radars en France 
<iframe width="853" height="480" src="https://www.youtube.com/embed/4E9TKXSK5CI" title="Fonctionnement du radar" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
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

























# Sujet : Les principaux établissements d'enseignement supérieur français 

![Image](pexels-pixabay-207691.jpg)

## Table des matières

* [Introduction](#Introduction)
* [Définition du sujet](#Définition du sujet)
    * [Section 1.1](#section_1_1)
    * [Section 1.2](sSection_1_2)
        * [Section 1.2.1](#section_1_2_1)
        * [Section 1.2.2](#section_1_2_2)
        * [Section 1.2.3](#section_1_2_3)
* [Chapter 2](#chapter2)
    * [Section 2.1](#section_2_1)
    * [Section 2.2](#section_2_2)

## Introduction 
Le jeu de données choisi porte sur le thème des établissements d'enseignement supérieur français, ce thème m'a attiré car en tant qu'étudiante à l'université de Paris Nanterre, je souhaite savoir combien d'université française existe, comparer le nombre des universités, des écoles, des grands établissements par région... 
Dans la suite de ce travail nous expliquerons chaque jeu de données réalisé ainsi que le but de ce dernier.

### Définition du Sujet 

Le terme d'études supérieures (parfois appelées études tertiaires), ou d'enseignement supérieur, désigne généralement l'instruction dispensée par les universités. En France un système plus dual de grandes écoles, d’instituts et d'autres institutions comme les grands établissements décernant des grades universitaires ou autres diplômes de l’enseignement supérieur. Ces études visent à acquérir un niveau « supérieur » de compétences.

## Les données récoltés 

### Première étape : la récolte des données 
Avant de réaliser les jeux de données, j'ai récolté les données sur le site (data.gouv.fr ) 

#### Le lien vers les données récoltées est le suivant : 

Le lien -->  [GitHub Pages](https://www.data.gouv.fr/fr/datasets/principaux-etablissements-d-enseignement-superieur-mesr/
 ) 
 
D'après les données récoltés? nous comptons 255 étbalissements d'enseignement supérieur français, ces derniers régroupe les écoles, les Universités, les Grands établissements et autres. Chacun fait partie d'une typologie précise, d'un secteur précis, à un nom, un url, un sigle, une localisation, date de création, un identifiant ainsi que d'autres infomrations importantes relatives à ces établissements.

<iframe src="https://data.opendatasoft.com/explore/embed/dataset/principaux-etablissements-denseignement-superieur@datailedefrance/table/?disjunctive.type_d_etablissement&disjunctive.typologie_d_universites_et_assimiles&static=false&datasetcard=false" width="800" height="500" frameborder="0"></iframe>

Les données récoltés sont de (format Csv), elles vont nous servir dans la suite du projet comme base de données à importer dans différents outils de création de jeux de données.
 
Pour faciliter la compréhension des jeux de données, j'ai fait en sorte de faire comprendre au public par ordre hiérarchique nos jeux de données, c'est à dire commençant par le plus simple au plus complexe en matière de charge d'informations.
 
### Premier jeu de données 
 
 Ce premier jeu de données, réalisé à partir de l'outil OpendataSoft; est une carte géographique qui nous permet de voir d'une manière globale; combien d'établissement supérieurs nous avons et où ils se situent, en cliquant sur un établissement par exemple nous voyons d'autres informations telles que le nom exact de l'établissement, son adresse, ains que son site Web.
Garce à ce jeu de données, nous découvrons qu'il existe des établissement français qui se trouvent dans d'autres pays, par exemple : L'Institut français d'archéologie orientale du Caire qui se trouve en Egypte.


<iframe frameborder="0" width="800" height="500" src="https://data.opendatasoft.com/map/embed/etablissements_sup_fr_sara/?&static=false&scrollWheelZoom=false"></iframe>

### 1) Requette sur les différents établissements d'enseignement supérieur français, leur date de création ainsi et les images corespondantes

la requette suivante a été effectuée sur Wikidata, elle nou permet d'afficher différement les informations souhaitées :

* Une carte géographique qui montre les différents établissements supérieurs de france 
* Les images des établissements avec en bas de chaque image, la date de création s'il y'en a, les coordonnées de l'établissement
* Un tableau dans lequel nous avons les Items de chaque établissement, le nom, le lien vers l'image, les coordonées, la date de création de l'établissement ( en ordre décroissant) c'est à dire nous comprenons facilement quel est l'établissement le plus récent et lequel est le plus ancien.
 


```sparql

#Etablissements supérieurs
#defaultView:ImageGrid
#defaultView:Map
SELECT ?item ?image ?datecreation ?coord WHERE
{
?item wdt:P31 wd:Q38723.
?item wdt:P17 wd:Q142
OPTIONAL {
?item wdt:P18 ?image. #affichier les images 
?item wdt:P571 ?datecreation.
?item wdt:P18 ?image .
?item wdt:P625 ?coord .
}
  SERVICE wikibase:label {bd:serviceParam wikibase:language "fr"}
}

ORDER BY DESC (?datecreation)

```
#### Remarque :
La visualisation des données en utilisant cette requette nous a donné l'occasion de voir les images de chaque établissement; donc nous a donné une vision plus agréable, mais celui-ci n'a pas affiché toutes les images. il existe des établissements pour lesquelles nous ne trouvons pas d'images dans Wikidata, ce qui est le cas pour les dates de création de certains établissements aussi, celà est probablement dû à l'absence de l'information dans la base de données.   

Ci-dessous l'affichage du résultat de la requette : 
Remarque : nous pouvons changer l'affichage ( map, tableau, images...) en cliquant sur le bouton à gauche de l'affichage.  

### Le résultat 

<iframe style="width: 70vw; height: 40vh; border: none;" src="https://query.wikidata.org/embed.html#%23Etablissements%20sup%C3%A9rieurs%0A%23defaultView%3AImageGrid%0ASELECT%20%3Fitem%20%3Fimage%20%3Fdatecreation%20%3Fcoord%20WHERE%0A%7B%0A%3Fitem%20wdt%3AP31%20wd%3AQ38723.%0A%3Fitem%20wdt%3AP17%20wd%3AQ142%0AOPTIONAL%20%7B%0A%3Fitem%20wdt%3AP18%20%3Fimage.%20%23affichier%20les%20images%20%0A%3Fitem%20wdt%3AP571%20%3Fdatecreation.%0A%3Fitem%20wdt%3AP18%20%3Fimage%20.%0A%3Fitem%20wdt%3AP625%20%3Fcoord%20.%0A%7D%0A%20%20SERVICE%20wikibase%3Alabel%20%7Bbd%3AserviceParam%20wikibase%3Alanguage%20%22fr%22%7D%0A%7D%0A%0AORDER%20BY%20DESC%20%28%3Fdatecreation%29" referrerpolicy="origin" sandbox="allow-scripts allow-same-origin allow-popups" ></iframe>

### Deuxième jeu de données 

#### Les types d'établissements supérieurs

Ce jeu de données est réalisé à partir de l'outil OpenDataSoft, il nous a permis d'afficher les types d'établissemts d'enseignement supérieur existant dans chaque région, nous faisons la différence entre une école, une université, un grand établissement ou autre en suivant la clef des couleurs indiquée sur la carte.

<iframe frameborder="0" width="800" height="600" src="https://data.opendatasoft.com/map/embed/type_etablissement_sara/?&static=false&scrollWheelZoom=false"></iframe>

### Troisième jeu de données 

#### Graphique sur le nombre et le type d'établissements par région 

##### Explication du graphique : 

Ce type de jeu de données qui est un diagrame à batons a été réalisé à partir de l'outil OpenDataSoft, il permet une représentation graphique d'une série de données (le nombre des établissements par régions). Les hauteurs des bâtons sont les valeurs de ces données. Pour chaque région nous avons au minimum un baton et au maximum 4 batons, car nous avons 4 types d'établissements différents, il y'a des régions où se trouvent les quatres types détablissements avec un nombre différent pour chaque type, nous avons d'autres régions ou nou n'avons pas tous les types ce qui est le but de ce diagrame.
##### Observation et Constat : 

Nous constatons après avoir bien observé notre diagramme que la région d'Ile de france est la région où il y'a le plus grand nombre d'établissements ((écoles (58), universités (15), grands établissements (12), Autre (1) comparé à d'autres régions de France où nous avons beaucoups moins détablissements comme en Auvergne-Rhône-Alpes qui contient un nombre de 11 écoles, 7 universités, 2 grands établissements, 1 autre , nous constatons aussi qu'il existe des régions où nous n'avons que des universités comme la région de la réunion où il y'a qu'une seule et unique université. Nous remarquons aussi qu'à l'étranger; il y'a que des étbalissements de type "autre" et pas d'universités ni d'écoles ou grands établissement français. 
##### Résultat du constat : 

Le plus grand nombre d'établissements en Ile de france est dù à sa population dense, ainsi qu'au fait que c'est là ou se trouve la capitale de France ( Paris ).


<iframe src="https://data.opendatasoft.com/chart/embed/nombre_etablissements-region/?&static=false&datasetcard=false" width="800" height="600" frameborder="0"></iframe>

### Quatrième jeu de données 

#### Les établissements d'enseignement supérieur par secteur ( privé/Public)

Ce jeu de données est réalisé à partir de l'outil Palladio, il nous permet de voir le nom des établissements ( nom_court ) par secteur. 
Nous observons deux types de secteurs existants, le secteur privé et le secteur public.
Ce jeu de données ne permet pas de voir le nombre d'établissemnents qui appartiennent aux secteur privé ou public, mais nous donne une vision globale sur ce point; visuellement nous constatons qu'il figure un plus grand nombre d'établissemnts publics que d'établissemnts privés. certes ce constat n'a pas d'exactitude cependant nous voyons un point important concernant un seul établissemnt français qui est ITESCIA qui est l'école du i-management, cet établissemnt fait partie du secteur public et privé au même temps.

 ![Palladio](Palladio Graph (4).svg)
### Cinquième jeu de données 

#### Graph sur le nombre des étudiants inscrits en 2011 et 2017

##### Explication du graphique : 

Ce jeu de données présenté est un diagrame à batons a été réalisé à partir de l'outil DataWrapper, il permet une représentation graphique d'une série de données (Les noms d'établissemnts par nombre détudiants inscrits en 2011 et 2017). Les hauteurs des bâtons sont des valeurs différentes des nombres d'étudiants selon ces deux années ( le bleu pour les étudiants inscrits en 2010, le rouge pour les étudiants inscrits en 2017. 

##### Observation et Constat : 

Nous constatons après avoir bien observé notre diagramme que l'université de la Sorbonne contient le plus grand nombre d'inscription comparés aux autres, elle contient 52,28k d'inscriptions en 2011, et un peu plus en 2017 , l'établissemnt qui a le moins d'inscription est l'ecole supérieure de fonderie et de forge. Nous remarquons sue en moyenne globale ce sont les universités qui ont le plus d'inscriptions que les écoles.


##### Résultat du constat : 
Hausse d'inscriptions dans les universités comparé aux écoles est dû au fait que les inscriptions soient gratuites ou moins chères dans les universités que dans les écoles, et probablement aussi liés aux conditions d'acceptabilité qui sont plus strictes quand il s'agit des écoles.
Le fait de comparer entre les inscriptions de l'année 2011 et 2017 a pour but de savoir si l'évolution des inscription (en moyenne) est resté le même au fil du temps. Donc nous avons confirmé cette hypothèse à partir de ce jeu de données ! 


<iframe title="[ Le nombre des étudiants inscrits en 2011/2017  ]" aria-label="Graphique en colonnes" id="datawrapper-chart-v2XL7" src="https://datawrapper.dwcdn.net/v2XL7/1/" scrolling="no" frameborder="0" style="width: 0; min-width: 100% !important; border: none;" height="523"></iframe><script type="text/javascript">!function(){"use strict";window.addEventListener("message",(function(e){if(void 0!==e.data["datawrapper-height"]){var t=document.querySelectorAll("iframe");for(var a in e.data["datawrapper-height"])for(var r=0;r<t.length;r++){if(t[r].contentWindow===e.source)t[r].style.height=e.data["datawrapper-height"][a]+"px"}}}))}();
</script>
