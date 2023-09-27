<!DOCTYPE html>
<html lang="de">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Gymtastisch</title>

    <style>

    </style>
</head>
<body>

    <div>
        <a href="index.html">Deutsch</a> | <a href="index_en.html">English</a> | <a href="index_es.html">Español</a>
    </div>

    <h1>Willkommen auf Gymtastisch!</h1>
    <p>Hier finden Sie die passenden Fitnessartikel für sich.</p>
    
    <form>
        <input type="text" id="search-input" placeholder="Produktsuche...">
        <button type="button" onclick="suchen()">Suchen</button>
    </form>

    <div id="search-results"></div>

    <h2>Impressum</h2>
    <p>Firmenname: Gymtastisch GmbH</p>
    <p>Vertretungsberechtigte Person: Emin Öztürk</p>
    <p>Adresse: Moorwisch 5, 22547 Hamburg</p>
    <p>Telefon: 015203108164</p>
    <p>E-Mail: 52emin.oeztuerk@gmail.com</p>


    <script>
        var datenbank = [
            { name: "Produkt 1", beschreibung: "Beschreibung von Produkt 1" },
            { name: "Produkt 2", beschreibung: "Beschreibung von Produkt 2" },
            { name: "Produkt 3", beschreibung: "Beschreibung von Produkt 3" },
            // Weitere Produkte hinzufügen
        ];

        function suchen() {
            var suchbegriff = document.getElementById("search-input").value.toLowerCase();
            var ergebnisse = [];

            for (var i = 0; i < datenbank.length; i++) {
                var produkt = datenbank[i];
                if (produkt.name.toLowerCase().includes(suchbegriff) || produkt.beschreibung.toLowerCase().includes(suchbegriff)) {
                    ergebnisse.push(produkt);
                }
            }

            anzeigenSuchergebnisse(ergebnisse);
        }

        function anzeigenSuchergebnisse(ergebnisse) {
            var ergebnisContainer = document.getElementById("search-results");
            ergebnisContainer.innerHTML = ""; // Löschen Sie den Inhalt des Container-Elements

            if (ergebnisse.length === 0) {
                ergebnisContainer.innerHTML = "Keine Ergebnisse gefunden.";
            } else {
                for (var i = 0; i < ergebnisse.length; i++) {
                    var ergebnis = ergebnisse[i];
                    var ergebnisElement = document.createElement("div");
                    ergebnisElement.textContent = ergebnis.name + ": " + ergebnis.beschreibung;
                    ergebnisContainer.appendChild(ergebnisElement);
                }
            }
        }
    </script>
</body>
</html>
