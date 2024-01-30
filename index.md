<!DOCTYPE html>
<html>
<head>
    <title>Projet de Visualisation de Données</title>
    
    <style>
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
    </style>
</head>

<body>
    <header>
        <h1>Projet de Visualisation de Données</h1>
    </header>

    <div class="container">
        <div class="section">
            <h2>Introduction</h2>
            <p> Mon projet consiste à expliquer les </p>
        </div>

        <div class="section">
            <div id="viz-container-1">
                  <iframe style="width: 80vw; height: 50vh; border: none;" src="https://query.wikidata.org/embed.html#%23defaultView%3AMap%0ASELECT%20%3Fpape%20%3FpapeLabel%20%3FdateDebut%20%3FdateFin%20%3Fcoordonnees%20%3Fimage%20WHERE%20%7B%0A%20%20%3Fpape%20wdt%3AP39%20wd%3AQ19546%3B%20%23%20Position%20occup%C3%A9e%3A%20Pape%0A%20%20%20%20%20%20%20%20wdt%3AP19%20%3FlieuNaissance%3B%0A%20%20%20%20%20%20%20%20wdt%3AP18%20%3Fimage%3B%0A%20%20%20%20%20%20%20%20p%3AP39%20%3Fstatement.%0A%20%20%3FlieuNaissance%20wdt%3AP625%20%3Fcoordonnees.%0A%20%20%3Fstatement%20ps%3AP39%20wd%3AQ19546%3B%20%23%20D%C3%A9claration%20de%20position%20occup%C3%A9e%3A%20Pape%0A%20%20%20%20%20%20%20%20%20%20%20%20%20pq%3AP580%20%3FdateDebut.%20%23%20Date%20de%20d%C3%A9but%3A%20P580%0A%20%20OPTIONAL%20%7B%20%3Fstatement%20pq%3AP582%20%3FdateFin.%20%7D%20%23%20Date%20de%20fin%3A%20P582%20(optionnel)%0A%20%20SERVICE%20wikibase%3Alabel%20%7B%20bd%3AserviceParam%20wikibase%3Alanguage%20%22%5BAUTO_LANGUAGE%5D%2Cfr%22.%20%7D%0A%7D%0AORDER%20BY%20%3FdateDebut%0A%0A" referrerpolicy="origin" sandbox="allow-scripts allow-same-origin allow-popups"></iframe>
            </div>
        </div>

        <div class="section">
            <h2>Visualisation #2</h2>
            <div id="viz-container-2">
                
            </div>
        </div>

        <div class="section">
            <h2>Conclusion</h2>
            <p>En conclusion</p>
        </div>
    </div>

</body>
</html>
