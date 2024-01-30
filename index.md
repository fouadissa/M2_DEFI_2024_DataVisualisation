<html>
<head>
    <title>Projet de Visualisation de Données : </br>Les Papes </title>
    
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
        <h1>Projet de Visualisation de Données</h1>
        <img src="https://media.npr.org/assets/img/2013/07/05/johnpaulii052way_custom-0e0891dcc3a65c7d8ee7bcf26caaf2033e908ca5-s1100-c50.jpg" alt="John Paul II">
    </header>

    <div class="container">
        <div class="section">
            <h2>Introduction</h2>
            <p> Mon projet consiste à expliquer les </p>
        </div>

        <div class="section">
            <h2>Pays de naissance des Papes</h2>
		<p>Ceci est learfjdgnefighnerziugnruizg</p>
            <div id="viz-container-1">
                  <iframe style="width: 80vw; height: 50vh; border: none;" src="https://query.wikidata.org/embed.html#%23defaultView%3AMap%0ASELECT%20%3Fpape%20%3FpapeLabel%20%3FdateDebut%20%3FdateFin%20%3Fcoordonnees%20%3Fimage%20WHERE%20%7B%0A%20%20%3Fpape%20wdt%3AP39%20wd%3AQ19546%3B%20%23%20Position%20occup%C3%A9e%3A%20Pape%0A%20%20%20%20%20%20%20%20wdt%3AP19%20%3FlieuNaissance%3B%0A%20%20%20%20%20%20%20%20wdt%3AP18%20%3Fimage%3B%0A%20%20%20%20%20%20%20%20p%3AP39%20%3Fstatement.%0A%20%20%3FlieuNaissance%20wdt%3AP625%20%3Fcoordonnees.%0A%20%20%3Fstatement%20ps%3AP39%20wd%3AQ19546%3B%20%23%20D%C3%A9claration%20de%20position%20occup%C3%A9e%3A%20Pape%0A%20%20%20%20%20%20%20%20%20%20%20%20%20pq%3AP580%20%3FdateDebut.%20%23%20Date%20de%20d%C3%A9but%3A%20P580%0A%20%20OPTIONAL%20%7B%20%3Fstatement%20pq%3AP582%20%3FdateFin.%20%7D%20%23%20Date%20de%20fin%3A%20P582%20(optionnel)%0A%20%20SERVICE%20wikibase%3Alabel%20%7B%20bd%3AserviceParam%20wikibase%3Alanguage%20%22%5BAUTO_LANGUAGE%5D%2Cfr%22.%20%7D%0A%7D%0AORDER%20BY%20%3FdateDebut%0A%0A" referrerpolicy="origin" sandbox="allow-scripts allow-same-origin allow-popups"></iframe>
            </div>
	  
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

        </div>

        <div class="section">
            <h2>Visualisation #2</h2>
            <div id="viz-container-2">
                <iframe style="width: 80vw; height: 50vh; border: none;" src="https://query.wikidata.org/embed.html#%23defaultView%3AImageGrid%0ASELECT%20%3Fpope%20%3FpopeLabel%20%3Fimage%0AWHERE%20%7B%0A%20%20%3Fpope%20wdt%3AP39%20wd%3AQ19546%3B%20%23%20Position%20held%3A%20Pope%0A%20%20%20%20%20%20%20%20wdt%3AP18%20%3Fimage.%20%20%20%20%20%20%23%20Property%3A%20image%0A%20%20SERVICE%20wikibase%3Alabel%20%7B%20bd%3AserviceParam%20wikibase%3Alanguage%20%22%5BAUTO_LANGUAGE%5D%2Cfr%22.%20%7D%0A%7D" referrerpolicy="origin" sandbox="allow-scripts allow-same-origin allow-popups"></iframe>
            </div>
        </div>

        <div class="section">
            <h2>Conclusion</h2>
            <p>En conclusion</p>
        </div>
    </div>

</body>
</html>
