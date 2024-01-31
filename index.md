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
            width: 80%;
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
            <p> Mon projet vise à présenter une carte mondiale indiquant les pays de naissance des papes, offrant un aperçu global de leurs origines. En plus d'une page montrant une grille d'images des papes, j'ai également créé des visualisations détaillant le nombre de papes par pays et par continent. Cette approche multiple permet une compréhension approfondie de la répartition géographique des papes au fil de l'histoire, mettant en lumière l'influence dominante de certains pays et continents dans la formation de la papauté.</p>
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
            <h2>Idées Non Concrétisées</h2>
            <p>J'ai voulu créer une visualisation d'une frise chrnologique de tout les papes avec leurs dates de début et de fin de ponctificat en utilsiant le jeux de données de wikidata, j'ai demandé à wikidata de me donner l'année,le jour et le mois de début de pontificat en nombre et chacune dans une colonne et de même pour la fin de pontificat, voici le résultat que j'ai obtenu : <a href="https://github.com/fouadissa/M2_DEFI_2024_DataVisualisation/blob/main/capture_ecran_wikidata_pontificats.png">capture_ecran_wikidata_pontificats.png</a> et voici le jeux de données : <a href="https://github.com/fouadissa/M2_DEFI_2024_DataVisualisation/blob/main/Papes_pontifcats.xls">Papes_pontifcats.xls</a>. Ensuite, j'ai unifié les dates de début et les date de fin de pontificat sur <a href="https://github.com/fouadissa/M2_DEFI_2024_DataVisualisation/blob/main/fusion_colonne.png">Capture_Openrefine</a>, pour avoir des données de type YYYY-MM-DD qui est compatbile avec Gannt Chart de <a href="https://app.rawgraphs.io/">rawgraphs</a>.   </p>
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
            
	    
        </div>
</body>
</html>
