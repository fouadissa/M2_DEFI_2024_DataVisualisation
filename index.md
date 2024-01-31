<html>
<head>
    <title>Origine géographique des papes</title>
    
    <style>
	img {
            max-width: 100%;
            height: auto;
        }
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f4f4f4;
            color: #333;
        }

        .container {
            width: 100%;
            margin: 20px auto;
            overflow: hidden;
        }

        header {
            background: #333;
            color: #fff;
            padding: 20px 0;
            text-align: center;
        }

        header h1 {
            margin: 0;
        }

        .section {
            background: #fff;
            margin: 20px 0;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
        }

        .section h2 {
            color: #333;
        }

        .centered-container {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 50vh;
            border: 2px solid #000;
            padding: 20px;
            background-color: #f0f0f0;
        }

        .code-block {
            background-color: #f5f5f5;
            border: 1px solid #ddd;
            padding: 10px;
            font-family: monospace;
            color: #333;
            white-space: pre;
        }
        .keyword { color: #008b8b; } /* Keywords */
        .variable { color: #905; }   /* Variable names */
        .comment { color: #998; font-style: italic; } /* Comments */
        .literal { color: #d14; }    /* String literals */
    </style>
</head>

<body>
    <header>
        <h1>Origine géographique des papes</h1>
        <img src="https://media.npr.org/assets/img/2013/07/05/johnpaulii052way_custom-0e0891dcc3a65c7d8ee7bcf26caaf2033e908ca5-s1100-c50.jpg" alt="Jean Paul II">
        <p>Source de l'image: <a href="https://media.npr.org/assets/img/2013/07/05/johnpaulii052way_custom-0e0891dcc3a65c7d8ee7bcf26caaf2033e908ca5-s1100-c50.jpg">National Public Radio</a></p>
        <p>Jean Paul II</p>
    </header>

    <div class="container">
        <div class="section">
            <h2>Introduction</h2>
            <p>Mon projet vise à présenter une carte mondiale indiquant les pays de naissance des papes, offrant un aperçu global de leurs origines. En plus d'une page montrant une grille d'images des papes, j'ai également créé des visualisations détaillant le nombre de papes par pays et par continent. J'ai aussi réalisé une frise chronologique des papes depuis le XVIIIe siècle, qui met en évidence l'évolution temporelle de la papauté. Cette approche multiple permet une compréhension approfondie de la répartition géographique et historique des papes au fil de l'histoire, mettant en lumière l'influence dominante de certains pays et continents dans la formation de la papauté.</p>
        </div>

        <div class="section">
            <h2>Carte du monde présentant les pays de naissance des Papes</h2>
		<p>Ceci est une carte du monde avec des points rouges représentant les pays de naissance des papes.</p>
            <div id="viz-container-1">
                  <iframe style="width: 80vw; height: 50vh; border: none;" src="https://query.wikidata.org/embed.html#%23defaultView%3AMap%0ASELECT%20%3Fpape%20%3FpapeLabel%20%3FdateDebut%20%3FdateFin%20%3Fcoordonnees%20%3Fimage%20WHERE%20%7B%0A%20%20%3Fpape%20wdt%3AP39%20wd%3AQ19546%3B%20%23%20Position%20occup%C3%A9e%3A%20Pape%0A%20%20%20%20%20%20%20%20wdt%3AP19%20%3FlieuNaissance%3B%0A%20%20%20%20%20%20%20%20wdt%3AP18%20%3Fimage%3B%0A%20%20%20%20%20%20%20%20p%3AP39%20%3Fstatement.%0A%20%20%3FlieuNaissance%20wdt%3AP625%20%3Fcoordonnees.%0A%20%20%3Fstatement%20ps%3AP39%20wd%3AQ19546%3B%20%23%20D%C3%A9claration%20de%20position%20occup%C3%A9e%3A%20Pape%0A%20%20%20%20%20%20%20%20%20%20%20%20%20pq%3AP580%20%3FdateDebut.%20%23%20Date%20de%20d%C3%A9but%3A%20P580%0A%20%20OPTIONAL%20%7B%20%3Fstatement%20pq%3AP582%20%3FdateFin.%20%7D%20%23%20Date%20de%20fin%3A%20P582%20(optionnel)%0A%20%20SERVICE%20wikibase%3Alabel%20%7B%20bd%3AserviceParam%20wikibase%3Alanguage%20%22%5BAUTO_LANGUAGE%5D%2Cfr%22.%20%7D%0A%7D%0AORDER%20BY%20%3FdateDebut%0A%0A" referrerpolicy="origin" sandbox="allow-scripts allow-same-origin allow-popups"></iframe>
            </div>
	  <p>Nous pouvons constater que l'écrasante majorité des papes proviennent d'Europe, en particulier d'Italie.</p>
    <div class="code-block">
        <span class="keyword">#defaultView:Map</span>
        <span class="keyword">SELECT</span> ?pape ?papeLabel ?dateDebut ?dateFin ?coordonnees ?image <span class="keyword">WHERE</span> {
        <span class="keyword">?</span>pape <span class="keyword">wdt:P39</span> <span class="keyword">wd:Q19546</span>; <span class="comment"># Position occupée: Pape</span>
        <span class="keyword">wdt:P19</span> ?lieuNaissance;
        <span class="keyword">wdt:P18</span> ?image;
        <span class="keyword">p:P39</span> ?statement.
        ?lieuNaissance <span class="keyword">wdt:P625</span> ?coordonnees.
        ?statement <span class="keyword">ps:P39</span> <span class="keyword">wd:Q19546</span>; <span class="comment"># Déclaration de position occupée: Pape</span>
        <span class="keyword">pq:P580</span> ?dateDebut. <span class="comment"># Date de début: P580</span>
        <span class="keyword">OPTIONAL</span> { ?statement <span class="keyword">pq:P582</span> ?dateFin. } <span class="comment"># Date de fin: P582 (optionnel)</span>
        <span class="keyword">SERVICE</span> <span class="keyword">wikibase:label</span> { <span class="keyword">bd:serviceParam</span> <span class="keyword">wikibase:language</span> <span class="literal">"[AUTO_LANGUAGE],fr"</span>. }
        }
        <span class="keyword">ORDER BY</span> ?dateDebut
    </div>
    <p>Ce code est une requête SPARQL pour Wikidata, conçue pour récupérer des informations sur les papes. Elle sélectionne le nom du pape (papeLabel), les dates de début et de fin de son pontificat, les coordonnées géographiques de son lieu de naissance, et une image associée. La requête ordonne les résultats par date de début de pontificat et utilise le service de labels pour obtenir les noms en français. Elle est conçue pour afficher les résultats sous forme de carte grâce à l'instruction #defaultView:Map.</p>

        </div>

        <div class="section">
            <h2>Images des Papes</h2>
            <div id="viz-container-2">
                <iframe style="width: 80vw; height: 50vh; border: none;" src="https://query.wikidata.org/embed.html#%23defaultView%3AImageGrid%0ASELECT%20%3Fpope%20%3FpopeLabel%20%3Fimage%0AWHERE%20%7B%0A%20%20%3Fpope%20wdt%3AP39%20wd%3AQ19546%3B%20%23%20Position%20held%3A%20Pope%0A%20%20%20%20%20%20%20%20wdt%3AP18%20%3Fimage.%20%20%20%20%20%20%23%20Property%3A%20image%0A%20%20SERVICE%20wikibase%3Alabel%20%7B%20bd%3AserviceParam%20wikibase%3Alanguage%20%22%5BAUTO_LANGUAGE%5D%2Cfr%22.%20%7D%0A%7D" referrerpolicy="origin" sandbox="allow-scripts allow-same-origin allow-popups"></iframe>
            </div>
	    <div class="code-block">
<span class="keyword">#defaultView:ImageGrid</span>
<span class="keyword">SELECT</span> ?pope ?popeLabel ?image
<span class="keyword">WHERE</span> {
    <span class="keyword">?</span>pope <span class="keyword">wdt:P39</span> <span class="keyword">wd:Q19546</span>; <span class="comment"># Position occupée: Pape</span>
    <span class="keyword">wdt:P18</span> ?image. <span class="comment"># Propriété: image</span>
    <span class="keyword">SERVICE</span> <span class="keyword">wikibase:label</span> {
        <span class="keyword">bd:serviceParam</span> <span class="keyword">wikibase:language</span> <span class="literal">"[AUTO_LANGUAGE],fr"</span>.
    }
}
     </div>
     <p>Cette requête SPARQL pour Wikidata vise à afficher une grille d'images des papes. Elle sélectionne le nom et l'image de chaque pape, en identifiant la position occupée comme étant celle de pape (wd:Q19546) et utilise le service de labels pour afficher les noms en français.</p>
        </div>
	<div class="section">
            <h2>Nombre de Papes par pays</h2>
	    <p>Pour réaliser la visualisation des données "Graphique en anneau" sur Flourish, j'ai manuellement copié les informations nécessaires depuis le site <a href="https://worldpopulationreview.com/country-rankings/popes-by-country">World Population Review - Popes by Country</a> , car le téléchargement des données requérait la fourniture d'une adresse e-mail, ce que je souhaitais éviter. Après avoir traduit les noms des pays en français, ces données, qui comprenaient le pays et le nombre de papes correspondant, ont été ajoutées à un graphique en anneau sur Flourish pour une représentation visuelle claire du nombre de papes par pays. Les données sont accessible sur mon répertoire GitHub sous le nom de fichier <a href="https://github.com/fouadissa/M2_DEFI_2024_DataVisualisation/blob/main/nbre_papes_pays.ods">nbre_papes_pays.ods</a>. Vous pouvez accéder à ces données pour une étude plus approfondie ou pour les utiliser dans d'autres projets. </p>
<div id="viz-container-3">
                <div class="flourish-embed flourish-chart" data-src="visualisation/16636121"><script src="https://public.flourish.studio/resources/embed.js"></script></div>
            </div>
	    <p>Nous pouvons constater qu'avec 217 papes, l'Italie représente l'écrasante majorité des papes, qui totalisent 266 au total. Les papes italiens représentent ainsi 81,58% des papes en 2024.</p>
        </div>

 <div class="section">
            <h2>Nombre de Papes par continent</h2>
	    <p>Cette nouvelle visualisation de données, également réalisée sur le site Flourish, prend la forme d'un "Graphique en anneau" et présente le nombre de papes par continent. Les données utilisées dans cette visualisation sont extraites de la précédente, qui se basait sur le jeu de données provenant du site <a href="https://worldpopulationreview.com/country-rankings/popes-by-country">World Population Review - Popes by Country</a>. Elle s'appuie sur des données que j'ai compilées dans un fichier intitulé <a href="https://github.com/fouadissa/M2_DEFI_2024_DataVisualisation/blob/main/nbre_papes_continent.ods"> nbre_papes_continent.ods</a>, que vous pouvez trouver dans mon répertoire GitHub. Ces données ont été élaborées manuellement à partir du fichier <a href="https://github.com/fouadissa/M2_DEFI_2024_DataVisualisation/blob/main/nbre_papes_pays.ods"> nbre_papes_pays.ods</a>, en additionnant les nombres de papes issus des pays européens, asiatiques (spécifiquement de l'Asie de l'Ouest), américains (en se concentrant sur l'Amérique du Sud) et africains (en se focalisant sur l'Afrique du Nord), afin d'apporter une précision géographique accrue à la visualisation.
            . </p>
<div id="viz-container-4">
               <div class="flourish-embed flourish-chart" data-src="visualisation/16636788"><script src="https://public.flourish.studio/resources/embed.js"></script></div>
            </div>
	    <p>
À l'échelle mondiale, l'Europe a fourni 252 papes jusqu'en 2024, représentant 94,74% du total des papes. Cette donnée souligne la diversité géographique des origines des papes européens, issus de pays tels que l'Italie, la France, l'Allemagne, la Grèce, l'Espagne, le Portugal, la Croatie, le Royaume-Uni, la Pologne et les Pays-Bas.</p>
        </div>


 <div class="section">
            <h2>Frise chronologique des papes depuis le XVIIIe siècle</h2>
            <p>J'ai voulu créer une visualisation d'une frise chronologique de tous les papes depuis le XVIIIe siècle, avec leurs dates de début et de fin de pontificat, en utilisant le jeu de données de Wikidata. J'ai demandé à Wikidata de me donner l'année, le jour et le mois de début de pontificat sous forme numérique et dans des colonnes séparées, et de même pour la fin de pontificat. Voici le résultat que j'ai obtenu : <a href="https://github.com/fouadissa/M2_DEFI_2024_DataVisualisation/blob/main/capture_ecran_wikidata_pontificats.png">capture_ecran_wikidata_pontificats.png</a>, et voici le jeu de données : <a href="https://github.com/fouadissa/M2_DEFI_2024_DataVisualisation/blob/main/Papes_pontifcats.xls">Papes_pontifcats.xls</a>. Ensuite, j'ai unifié les dates de début et de fin de pontificat sur <a href="https://github.com/fouadissa/M2_DEFI_2024_DataVisualisation/blob/main/fusion_colonne.png">Capture_Openrefine</a> pour obtenir des données au format YYYY-MM-DD, compatible avec le Gantt Chart de <a href="https://app.rawgraphs.io/">rawgraphs</a>. J'ai également ajouté manuellement une colonne indiquant les pays de naissance des papes en effectuant des recherches, car je n'ai pas réussi à effectuer des requêtes SQL sur OpenRefine. En effet, lors de la réconciliation de la colonne des papes, les noms de ces derniers n'étaient pas retrouvés.</p>
	 <div id="viz-container-5">
<svg xmlns="http://www.w3.org/2000/svg" width="1005" height="600"><rect width="1005" height="600" x="0" y="0" fill="#FFFFFF" id="background"/><g transform="translate(100,50)" id="visualization"><g id="axis"><g transform="translate(0,500)" fill="none" font-size="10" font-family="sans-serif" text-anchor="middle"><path class="domain" stroke="currentColor" d="M0,6V0H655V6"/><g class="tick" opacity="1" transform="translate(0,0)"><line stroke="currentColor" y2="6"/><text fill="currentColor" y="9" dy="0.71em">1720</text></g><g class="tick" opacity="1" transform="translate(44,0)"><line stroke="currentColor" y2="6"/><text fill="currentColor" y="9" dy="0.71em">1740</text></g><g class="tick" opacity="1" transform="translate(87,0)"><line stroke="currentColor" y2="6"/><text fill="currentColor" y="9" dy="0.71em">1760</text></g><g class="tick" opacity="1" transform="translate(131,0)"><line stroke="currentColor" y2="6"/><text fill="currentColor" y="9" dy="0.71em">1780</text></g><g class="tick" opacity="1" transform="translate(175,0)"><line stroke="currentColor" y2="6"/><text fill="currentColor" y="9" dy="0.71em">1800</text></g><g class="tick" opacity="1" transform="translate(218,0)"><line stroke="currentColor" y2="6"/><text fill="currentColor" y="9" dy="0.71em">1820</text></g><g class="tick" opacity="1" transform="translate(262,0)"><line stroke="currentColor" y2="6"/><text fill="currentColor" y="9" dy="0.71em">1840</text></g><g class="tick" opacity="1" transform="translate(306,0)"><line stroke="currentColor" y2="6"/><text fill="currentColor" y="9" dy="0.71em">1860</text></g><g class="tick" opacity="1" transform="translate(349,0)"><line stroke="currentColor" y2="6"/><text fill="currentColor" y="9" dy="0.71em">1880</text></g><g class="tick" opacity="1" transform="translate(393,0)"><line stroke="currentColor" y2="6"/><text fill="currentColor" y="9" dy="0.71em">1900</text></g><g class="tick" opacity="1" transform="translate(437,0)"><line stroke="currentColor" y2="6"/><text fill="currentColor" y="9" dy="0.71em">1920</text></g><g class="tick" opacity="1" transform="translate(480,0)"><line stroke="currentColor" y2="6"/><text fill="currentColor" y="9" dy="0.71em">1940</text></g><g class="tick" opacity="1" transform="translate(524,0)"><line stroke="currentColor" y2="6"/><text fill="currentColor" y="9" dy="0.71em">1960</text></g><g class="tick" opacity="1" transform="translate(568,0)"><line stroke="currentColor" y2="6"/><text fill="currentColor" y="9" dy="0.71em">1980</text></g><g class="tick" opacity="1" transform="translate(611,0)"><line stroke="currentColor" y2="6"/><text fill="currentColor" y="9" dy="0.71em">2000</text></g><g class="tick" opacity="1" transform="translate(655,0)"><line stroke="currentColor" y2="6"/><text fill="currentColor" y="9" dy="0.71em">2020</text></g></g></g><g id="viz"><g id="Innocent XIII" transform="translate(0,0)"><text x="-4" y="10.869565217391305" text-anchor="end" dominant-baseline="middle" style="font-family: Arial, sans-serif; font-size: 10px; fill: black; font-weight: normal;">Innocent XIII</text><rect x="3" y="0" width="6" height="21.73913043478261" fill="#2ca02c"/><line x1="0" y1="0" x2="655" y2="0" style="stroke: rgb(204, 204, 204);"/></g><g id="Benoît XIII" transform="translate(0,21.73913043478261)"><text x="-4" y="10.869565217391305" text-anchor="end" dominant-baseline="middle" style="font-family: Arial, sans-serif; font-size: 10px; fill: black; font-weight: normal;">Benoît XIII</text><rect x="10" y="0" width="12" height="21.73913043478261" fill="#2ca02c"/><line x1="0" y1="0" x2="655" y2="0" style="stroke: rgb(204, 204, 204);"/></g><g id="Clément XII" transform="translate(0,43.47826086956522)"><text x="-4" y="10.869565217391305" text-anchor="end" dominant-baseline="middle" style="font-family: Arial, sans-serif; font-size: 10px; fill: black; font-weight: normal;">Clément XII</text><rect x="23" y="0" width="21" height="21.73913043478261" fill="#2ca02c"/><line x1="0" y1="0" x2="655" y2="0" style="stroke: rgb(204, 204, 204);"/></g><g id="Benoît XIV" transform="translate(0,65.21739130434783)"><text x="-4" y="10.869565217391305" text-anchor="end" dominant-baseline="middle" style="font-family: Arial, sans-serif; font-size: 10px; fill: black; font-weight: normal;">Benoît XIV</text><rect x="45" y="0" width="39" height="21.73913043478261" fill="#2ca02c"/><line x1="0" y1="0" x2="655" y2="0" style="stroke: rgb(204, 204, 204);"/></g><g id="Clément XIII" transform="translate(0,86.95652173913044)"><text x="-4" y="10.869565217391305" text-anchor="end" dominant-baseline="middle" style="font-family: Arial, sans-serif; font-size: 10px; fill: black; font-weight: normal;">Clément XIII</text><rect x="84" y="0" width="23" height="21.73913043478261" fill="#2ca02c"/><line x1="0" y1="0" x2="655" y2="0" style="stroke: rgb(204, 204, 204);"/></g><g id="Clément XIV" transform="translate(0,108.69565217391305)"><text x="-4" y="10.869565217391305" text-anchor="end" dominant-baseline="middle" style="font-family: Arial, sans-serif; font-size: 10px; fill: black; font-weight: normal;">Clément XIV</text><rect x="108" y="0" width="11" height="21.73913043478261" fill="#2ca02c"/><line x1="0" y1="0" x2="655" y2="0" style="stroke: rgb(204, 204, 204);"/></g><g id="Pie VI" transform="translate(0,130.43478260869566)"><text x="-4" y="10.869565217391305" text-anchor="end" dominant-baseline="middle" style="font-family: Arial, sans-serif; font-size: 10px; fill: black; font-weight: normal;">Pie VI</text><rect x="120" y="0" width="54" height="21.73913043478261" fill="#2ca02c"/><line x1="0" y1="0" x2="655" y2="0" style="stroke: rgb(204, 204, 204);"/></g><g id="Pie VII" transform="translate(0,152.17391304347825)"><text x="-4" y="10.869565217391305" text-anchor="end" dominant-baseline="middle" style="font-family: Arial, sans-serif; font-size: 10px; fill: black; font-weight: normal;">Pie VII</text><rect x="175" y="0" width="51" height="21.73913043478261" fill="#2ca02c"/><line x1="0" y1="0" x2="655" y2="0" style="stroke: rgb(204, 204, 204);"/></g><g id="Léon XII" transform="translate(0,173.91304347826087)"><text x="-4" y="10.869565217391305" text-anchor="end" dominant-baseline="middle" style="font-family: Arial, sans-serif; font-size: 10px; fill: black; font-weight: normal;">Léon XII</text><rect x="226" y="0" width="12" height="21.73913043478261" fill="#2ca02c"/><line x1="0" y1="0" x2="655" y2="0" style="stroke: rgb(204, 204, 204);"/></g><g id="Pie VIII" transform="translate(0,195.6521739130435)"><text x="-4" y="10.869565217391305" text-anchor="end" dominant-baseline="middle" style="font-family: Arial, sans-serif; font-size: 10px; fill: black; font-weight: normal;">Pie VIII</text><rect x="239" y="0" width="3" height="21.73913043478261" fill="#2ca02c"/><line x1="0" y1="0" x2="655" y2="0" style="stroke: rgb(204, 204, 204);"/></g><g id="Grégoire XVI" transform="translate(0,217.3913043478261)"><text x="-4" y="10.869565217391305" text-anchor="end" dominant-baseline="middle" style="font-family: Arial, sans-serif; font-size: 10px; fill: black; font-weight: normal;">Grégoire XVI</text><rect x="243" y="0" width="33" height="21.73913043478261" fill="#2ca02c"/><line x1="0" y1="0" x2="655" y2="0" style="stroke: rgb(204, 204, 204);"/></g><g id="Pie IX" transform="translate(0,239.1304347826087)"><text x="-4" y="10.869565217391305" text-anchor="end" dominant-baseline="middle" style="font-family: Arial, sans-serif; font-size: 10px; fill: black; font-weight: normal;">Pie IX</text><rect x="276" y="0" width="69" height="21.73913043478261" fill="#2ca02c"/><line x1="0" y1="0" x2="655" y2="0" style="stroke: rgb(204, 204, 204);"/></g><g id="Léon XIII" transform="translate(0,260.8695652173913)"><text x="-4" y="10.869565217391305" text-anchor="end" dominant-baseline="middle" style="font-family: Arial, sans-serif; font-size: 10px; fill: black; font-weight: normal;">Léon XIII</text><rect x="345" y="0" width="56" height="21.73913043478261" fill="#2ca02c"/><line x1="0" y1="0" x2="655" y2="0" style="stroke: rgb(204, 204, 204);"/></g><g id="Pie X" transform="translate(0,282.60869565217394)"><text x="-4" y="10.869565217391305" text-anchor="end" dominant-baseline="middle" style="font-family: Arial, sans-serif; font-size: 10px; fill: black; font-weight: normal;">Pie X</text><rect x="401" y="0" width="24" height="21.73913043478261" fill="#2ca02c"/><line x1="0" y1="0" x2="655" y2="0" style="stroke: rgb(204, 204, 204);"/></g><g id="Benoît XV" transform="translate(0,304.3478260869565)"><text x="-4" y="10.869565217391305" text-anchor="end" dominant-baseline="middle" style="font-family: Arial, sans-serif; font-size: 10px; fill: black; font-weight: normal;">Benoît XV</text><rect x="425" y="0" width="16" height="21.73913043478261" fill="#2ca02c"/><line x1="0" y1="0" x2="655" y2="0" style="stroke: rgb(204, 204, 204);"/></g><g id="Pie XI" transform="translate(0,326.0869565217391)"><text x="-4" y="10.869565217391305" text-anchor="end" dominant-baseline="middle" style="font-family: Arial, sans-serif; font-size: 10px; fill: black; font-weight: normal;">Pie XI</text><rect x="441" y="0" width="37" height="21.73913043478261" fill="#2ca02c"/><line x1="0" y1="0" x2="655" y2="0" style="stroke: rgb(204, 204, 204);"/></g><g id="Pie XII" transform="translate(0,347.82608695652175)"><text x="-4" y="10.869565217391305" text-anchor="end" dominant-baseline="middle" style="font-family: Arial, sans-serif; font-size: 10px; fill: black; font-weight: normal;">Pie XII</text><rect x="479" y="0" width="42" height="21.73913043478261" fill="#2ca02c"/><line x1="0" y1="0" x2="655" y2="0" style="stroke: rgb(204, 204, 204);"/></g><g id="Jean XXIII" transform="translate(0,369.5652173913044)"><text x="-4" y="10.869565217391305" text-anchor="end" dominant-baseline="middle" style="font-family: Arial, sans-serif; font-size: 10px; fill: black; font-weight: normal;">Jean XXIII</text><rect x="521" y="0" width="10" height="21.73913043478261" fill="#2ca02c"/><line x1="0" y1="0" x2="655" y2="0" style="stroke: rgb(204, 204, 204);"/></g><g id="Paul VI" transform="translate(0,391.304347826087)"><text x="-4" y="10.869565217391305" text-anchor="end" dominant-baseline="middle" style="font-family: Arial, sans-serif; font-size: 10px; fill: black; font-weight: normal;">Paul VI</text><rect x="532" y="0" width="33" height="21.73913043478261" fill="#2ca02c"/><line x1="0" y1="0" x2="655" y2="0" style="stroke: rgb(204, 204, 204);"/></g><g id="Jean-Paul Ier" transform="translate(0,413.04347826086956)"><text x="-4" y="10.869565217391305" text-anchor="end" dominant-baseline="middle" style="font-family: Arial, sans-serif; font-size: 10px; fill: black; font-weight: normal;">Jean-Paul Ier</text><rect x="565" y="0" width="1" height="21.73913043478261" fill="#2ca02c"/><line x1="0" y1="0" x2="655" y2="0" style="stroke: rgb(204, 204, 204);"/></g><g id="Jean-Paul II" transform="translate(0,434.7826086956522)"><text x="-4" y="10.869565217391305" text-anchor="end" dominant-baseline="middle" style="font-family: Arial, sans-serif; font-size: 10px; fill: black; font-weight: normal;">Jean-Paul II</text><rect x="565" y="0" width="58" height="21.73913043478261" fill="#d62728"/><line x1="0" y1="0" x2="655" y2="0" style="stroke: rgb(204, 204, 204);"/></g><g id="Benoît XVI" transform="translate(0,456.5217391304348)"><text x="-4" y="10.869565217391305" text-anchor="end" dominant-baseline="middle" style="font-family: Arial, sans-serif; font-size: 10px; fill: black; font-weight: normal;">Benoît XVI</text><rect x="623" y="0" width="17" height="21.73913043478261" fill="#1f77b4"/><line x1="0" y1="0" x2="655" y2="0" style="stroke: rgb(204, 204, 204);"/></g><g id="François" transform="translate(0,478.2608695652174)"><text x="-4" y="10.869565217391305" text-anchor="end" dominant-baseline="middle" style="font-family: Arial, sans-serif; font-size: 10px; fill: black; font-weight: normal;">François</text><rect x="640" y="0" width="1" height="21.73913043478261" fill="#ff7f0e"/><line x1="0" y1="0" x2="655" y2="0" style="stroke: rgb(204, 204, 204);"/></g></g></g><g id="legend" transform="translate(805,50)"><g transform="translate(5,0)"><g class="legendColor" transform="translate(0,0)"><g class="legendCells" transform="translate(0,16)"><g class="cell" transform="translate(0, 0)"><rect class="swatch" height="15" width="15" style="fill: rgb(31, 119, 180);"/><text class="label" transform="translate( 20, 12.5)" font-family="&quot;Arial&quot;, sans-serif" font-size="10px"><tspan x="0" dy="0em">Allemagne</tspan></text></g><g class="cell" transform="translate(0, 21)"><rect class="swatch" height="15" width="15" style="fill: rgb(255, 127, 14);"/><text class="label" transform="translate( 20, 12.5)" font-family="&quot;Arial&quot;, sans-serif" font-size="10px"><tspan x="0" dy="0em">Argentine</tspan></text></g><g class="cell" transform="translate(0, 42)"><rect class="swatch" height="15" width="15" style="fill: rgb(44, 160, 44);"/><text class="label" transform="translate( 20, 12.5)" font-family="&quot;Arial&quot;, sans-serif" font-size="10px"><tspan x="0" dy="0em">Italie</tspan></text></g><g class="cell" transform="translate(0, 63)"><rect class="swatch" height="15" width="15" style="fill: rgb(214, 39, 40);"/><text class="label" transform="translate( 20, 12.5)" font-family="&quot;Arial&quot;, sans-serif" font-size="10px"><tspan x="0" dy="0em">Pologne</tspan></text></g></g><text class="legendTitle" font-family="&quot;Arial&quot;, sans-serif" font-size="12px" font-weight="bold"><tspan x="0" dy="0em">Pays de Naissance</tspan></text></g></g></g></svg>
		 <p>D'après la frise chronologique, nous constatons que tous les papes depuis le XVIIIe siècle sont d'origine italienne, à l'exception des trois derniers qui sont respectivement polonais, allemand et argentin.</p>
        </div>
    </div>
        <div class="section">
            <h2>Conclusion</h2>
            <p>En conclusion, cette étude de l'origine géographique des papes révèle une prédominance européenne marquée, avec une concentration particulièrement forte en Italie. Cette distribution souligne l'influence historique et culturelle de l'Europe sur la papauté. Les visualisations créées offrent une perspective claire et accessible de cette tendance, enrichissant notre compréhension de l'histoire de la papauté et de son impact à travers les âges.</p>
        </div>
    
<div class="section">
            <h2>Quiz</h2>
	    <p>Ceci est une visualisation interactive sous forme de quiz créée avec Flourish, abordant le thème de l'origine géographique des papes. Testez vos connaissances en répondant à une série de questions sur l'origine des papes à travers le monde. </p>
<div id="viz-container-5">
                <div class="flourish-embed flourish-quiz" data-src="visualisation/16636627"><script src="https://public.flourish.studio/resources/embed.js"></script></div></div> 
            
	    
        
</body>
</html>
