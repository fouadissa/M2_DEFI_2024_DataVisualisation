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
        <img src="https://media.npr.org/assets/img/2013/07/05/johnpaulii052way_custom-0e0891dcc3a65c7d8ee7bcf26caaf2033e908ca5-s1100-c50.jpg" alt="John Paul II">
    </header>

    <div class="container">
        <div class="section">
            <h2>Introduction</h2>
            <p> Mon projet consiste à présenter une carte du monde indiquant les pays de naissance des papes pour donner un aperçu d'où proviennent la plupart des papes, en termes de continents et de pays. Je vais également créer une page affichant une grille d'images des papes, ainsi qu'une visualisation du nombre de papes par pays.</p>
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
	    <p>Ceci est une visualisation de données réalisée sur le site Flourish intitulée "Graphique en anneau". Cette visualisation représente le nombre de Papes par pays. Le jeu de données utilisé pour cette visualisation provient du site https://worldpopulationreview.com/country-rankings/popes-by-country. </p>
<div id="viz-container-3">
                <div class="flourish-embed flourish-chart" data-src="visualisation/16636121"><script src="https://public.flourish.studio/resources/embed.js"></script></div>
            </div>
	    <p>Nous pouvons constater qu'avec 217 papes, l'Italie représente l'écrasante majorité des papes, qui totalisent 266 au total. Les papes italiens représentent ainsi 81,58% des papes en 2024.</p>
        </div>
        <div class="section">
            <h2>Conclusion</h2>
            <p>En conclusion</p>
        </div>
    </div>
<div class="section">
            <h2>Quiz</h2>
	    <p>Ceci est une visualisation interactive sous forme de quiz créée avec Flourish, abordant le thème de l'origine géographique des papes. Testez vos connaissances en répondant à une série de questions sur l'origine des papes à travers le monde. </p>
<div id="viz-container-3">
                <div class="flourish-embed flourish-quiz" data-src="visualisation/16636627"><script src="https://public.flourish.studio/resources/embed.js"></script></div></div> 
            </div>
	    
        </div>
</body>
</html>
