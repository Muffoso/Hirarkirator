# Hierarkirator

En fristående HTML-fil (`hierarkirator.html`) för att skapa, redigera och exportera hierarkiska listor som lagras i semikolonseparerade CSV-filer.

Öppna filen i **Chrome eller Edge**. Där kan sidan skriva direkt till CSV-filen och autospara var 10:e sekund. I andra webbläsare kan du läsa filer, men "Spara" laddar då ner en kopia.

## CSV-format

```
Nivå;Namn;Beskrivning;Ansvarig;Taggar
1;Projekt;;Anna;projekt
2;Delmoment;"Text med ; inom citattecken";Erik;analys, möte
```

- `Nivå` (även `Level`): hierarkinivå 1, 2, 3 … Radordningen i filen är ordningen i listan.
- `Taggar` (även `Tags`): kommaseparerade taggar.
- Alla övriga kolumner är fält. Du kan lägga till, ta bort, byta namn på och ändra ordning på dem i appen.
- Filen skrivs som UTF-8 med BOM, så att Excel visar å, ä och ö rätt. Den kan också läsa ANSI-filer som sparats från Excel.

Se `exempel.csv`.

## Bilder och markeringar

Under listan kan du lägga till bilder och märka ut rader på dem med numrerade cirklar. Dra en rad till en bild, eller använd **📍 Placera markering**.

- Markeringarna sparas i CSV-kolumnen `Bildmarkeringar`, i formatet `bild.png@x,y | bild2.jpg@x,y`. x och y anges i procent av bildens bredd och höjd.
- **Bildmapp (rekommenderas):** klicka **📁 Välj bildmapp…** och peka ut mappen där bilderna ligger, gärna samma mapp som CSV-filen. Bilderna hittas då via namnen i CSV-filen, så listan kan flyttas eller delas tillsammans med mappen. Bilder du lägger till kopieras in i mappen, men befintliga filer skrivs aldrig över. Mappvalet kommer ihåg per lista.
- Utan bildmapp sparas bilderna i webbläsaren, kopplade till CSV-filens namn. Det gäller också som reserv om mappen inte är kopplad.
