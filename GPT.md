# Origine géographique des papes

![Jean Paul II](https://media.npr.org/assets/img/2013/07/05/johnpaulii052way_custom-0e0891dcc3a65c7d8ee7bcf26caaf2033e908ca5-s1100-c50.jpg)  
Source de l'image: [National Public Radio](https://media.npr.org/assets/img/2013/07/05/johnpaulii052way_custom-0e0891dcc3a65c7d8ee7bcf26caaf2033e908ca5-s1100-c50.jpg)  
Jean Paul II

## Introduction

Mon projet vise à présenter une carte mondiale indiquant les pays de naissance des papes, offrant un aperçu global de leurs origines. En plus d'une page montrant une grille d'images des papes, j'ai également créé des visualisations détaillant le nombre de papes par pays et par continent. J'ai aussi réalisé une frise chronologique des papes depuis le XVIIIe siècle, qui met en évidence l'évolution temporelle de la papauté. Cette approche multiple permet une compréhension approfondie de la répartition géographique et historique des papes au fil de l'histoire, mettant en lumière l'influence dominante de certains pays et continents dans la formation de la papauté.

## Carte du monde présentant les pays de naissance des Papes

Ceci est une carte du monde avec des points rouges représentant les pays de naissance des papes.

Nous pouvons constater que l'écrasante majorité des papes proviennent d'Europe, en particulier d'Italie.
#defaultView:Map
SELECT ?pape ?papeLabel ?dateDebut ?dateFin ?coordonnees ?image WHERE {
?pape wdt:P39 wd:Q19546; # Position occupée: Pape
wdt:P19 ?lieuNaissance;
wdt:P18 ?image;
p:P39 ?statement.
?lieuNaissance wdt:P625 ?coordonnees.
?statement ps:P39 wd:Q19546; # Déclaration de position occupée: Pape
pq:P580 ?dateDebut. # Date de début: P580
OPTIONAL { ?statement pq:P582 ?dateFin. } # Date de fin: P582 (optionnel)
SERVICE wikibase:label { bd:serviceParam wikibase:language "[AUTO_LANGUAGE],fr". }
}
ORDER BY ?dateDebut

Ce code est une requête SPARQL pour Wikidata, conçue pour récupérer des informations sur les papes. Elle sélectionne le nom du pape (papeLabel), les dates de début et de fin de son pontificat, les coordonnées géographiques de son lieu de naissance, et une image associée. La requête ordonne les résultats par date de début de pontificat et utilise le service de labels pour obtenir les noms en français. Elle est conçue pour afficher les résultats sous forme de carte grâce à l'instruction #defaultView:Map.

## Images des Papes

Ceci est une sélection d'images des papes, organisée pour fournir une vue d'ensemble visuelle.

#defaultView:ImageGrid
SELECT ?pope ?popeLabel ?image WHERE {
?pope wdt:P39 wd:Q19546; # Position occupée: Pape
wdt:P18 ?image. # Propriété: image
SERVICE wikibase:label {
bd:serviceParam wikibase:language "[AUTO_LANGUAGE],fr".
}
}


Cette requête SPARQL pour Wikidata vise à afficher une grille d'images des papes. Elle sélectionne le nom et l'image de chaque pape, en identifiant la position occupée comme étant celle de pape (wd:Q19546) et utilise le service de labels pour afficher les noms en français.

## Nombre de Papes par pays

Pour réaliser la visualisation des données "Graphique en anneau" sur Flourish, j'ai manuellement copié les informations nécessaires depuis le site [World Population Review - Popes by Country](https://worldpopulationreview.com/country-rankings/popes-by-country), car le téléchargement des données requérait la fourniture d'une adresse e-mail, ce que je souhaitais éviter. Après avoir traduit les noms des pays en français, ces données, qui comprenaient le pays et le nombre de papes correspondant, ont été ajoutées à un graphique en anneau sur Flourish pour une représentation visuelle claire du nombre de papes par pays. Les données sont accessible sur mon répertoire GitHub sous le nom de fichier [nbre_papes_pays.ods](https://github.com/fouadissa/M2_DEFI_2024_DataVisualisation/blob/main/nbre_papes_pays.ods). Vous pouvez accéder à ces données pour une étude plus approfondie ou pour les utiliser dans d'autres projets.

Nous pouvons constater qu'avec 217 papes, l'Italie représente l'écrasante majorité des papes, qui totalisent 266 au total. Les papes italiens représentent ainsi 81,58% des papes en 2024.

## Nombre de Papes par continent

Cette nouvelle visualisation de données, également réalisée sur le site Flourish, prend la forme d'un "Graphique en anneau" et présente le nombre de papes par continent. Les données utilisées dans cette visualisation sont extraites de la précédente, qui se basait sur le jeu de données provenant du site [World Population Review - Popes by Country](https://worldpopulationreview.com/country-rankings/popes-by-country). Elle s'appuie sur des données que j'ai compilées dans un fichier intitulé [nbre_papes_continent.ods](https://github.com/fouadissa/M2_DEFI_2024_DataVisualisation/blob/main/nbre_papes_continent.ods), que vous pouvez trouver dans mon répertoire GitHub. Ces données ont été élaborées manuellement à partir du fichier [nbre_papes_pays.ods](https://github.com/fouadissa/M2_DEFI_2024_DataVisualisation/blob/main/nbre_papes_pays.ods), en additionnant les nombres de papes issus des pays européens, asiatiques (spécifiquement de l'Asie de l'Ouest), américains (en se concentrant sur l'Amérique du Sud) et africains (en se focalisant sur l'Afrique du Nord), afin d'apporter une précision géographique accrue à la visualisation.

À l'échelle mondiale, l'Europe a fourni 252 papes jusqu'en 2024, représentant 94,74% du total des papes. Cette donnée souligne la diversité géographique des origines des papes européens, issus de pays tels que l'Italie, la France, l'Allemagne, la Grèce, l'Espagne, le Portugal, la Croatie, le Royaume-Uni, la Pologne et les Pays-Bas.

## Frise chronologique des papes depuis le XVIIIe siècle

J'ai voulu créer une visualisation d'une frise chronologique de tous les papes depuis le XVIIIe siècle, avec leurs dates de début et de fin de pontificat, en utilisant le jeu de données de Wikidata. J'ai demandé à Wikidata de me donner l'année, le jour et le mois de début de pontificat sous forme numérique et dans des colonnes séparées, et de même pour la fin de pontificat. Voici le résultat que j'ai obtenu : [capture_ecran_wikidata_pontificats.png](https://github.com/fouadissa/M2_DEFI_2024_DataVisualisation/blob/main/capture_ecran_wikidata_pontificats.png), et voici le jeu de données : [Papes_pontifcats.xls](https://github.com/fouadissa/M2_DEFI_2024_DataVisualisation/blob/main/Papes_pontifcats.xls). Ensuite, j'ai unifié les dates de début et de fin de pontificat sur [Capture_Openrefine](https://github.com/fouadissa/M2_DEFI_2024_DataVisualisation/blob/main/fusion_colonne.png) pour obtenir des données au format YYYY-MM-DD, compatible avec le Gantt Chart de [rawgraphs](https://app.rawgraphs.io/). J'ai également ajouté manuellement une colonne indiquant les pays de naissance des papes en effectuant des recherches, car je n'ai pas réussi à effectuer des requêtes SQL sur OpenRefine. En effet, lors de la réconciliation de la colonne des papes, les noms de ces derniers n'étaient pas retrouvés.

D'après la frise chronologique, nous constatons que tous les papes depuis le XVIIIe siècle sont d'origine italienne, à l'exception des trois derniers qui sont respectivement polonais, allemand et argentin.

## Conclusion

En conclusion, cette étude de l'origine géographique des papes révèle une prédominance européenne marquée, avec une concentration particulièrement forte en Italie. Cette distribution souligne l'influence historique et culturelle de l'Europe sur la papauté. Les visualisations créées offrent une perspective claire et accessible de cette tendance, enrichissant notre compréhension de l'histoire de la papauté et de son impact à travers les âges.

## Quiz

Ceci est une visualisation interactive sous forme de quiz créée avec Flourish, abordant le thème de l'origine géographique des papes. Testez vos connaissances en répondant à une série de questions sur l'origine des papes à travers le monde.


