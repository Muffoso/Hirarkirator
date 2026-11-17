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

Till höger om listan kan du lägga till bilder och märka ut rader på dem med numrerade cirklar. Dra en rad till en bild, eller använd **📍** (placera markering). Bilderna anpassas som standard så att de fyller bildytans bredd. Zooma in eller ut med Ctrl + scrollhjul, och klicka **⤢** (Anpassa) för att anpassa dem efter bredden igen.

- Markeringarna sparas i CSV-kolumnen `Bildmarkeringar`, i formatet `bild.png@x,y | bild2.jpg@x,y`. x och y anges i procent av bildens bredd och höjd.
- **Bildmapp (rekommenderas):** klicka **📁** (välj bildmapp) och peka ut mappen där bilderna ligger, gärna samma mapp som CSV-filen. Bilderna hittas då via namnen i CSV-filen, så listan kan flyttas eller delas tillsammans med mappen. Bilder du lägger till kopieras in i mappen, men befintliga filer skrivs aldrig över. Mappvalet kommer ihåg per lista.
- Bilderna läses in från mappen varje gång sidan laddas, och när du går tillbaka till fönstret. Skriver du över en bildfil i mappen syns den nya versionen direkt. Efter en omladdning frågar Chrome ibland om åtkomst till mappen igen. Välj **Tillåt vid varje besök**, så slipper du frågan i fortsättningen. Fram till dess visas webbläsarens senast sparade kopior.
- **Taggar på bilder:** skriv i fältet **+ tagg** under bildnamnet och tryck Enter. Taggarna visas i bildytans verktygsrad; klicka på en tagg där för att bara visa bilder som har någon av de valda taggarna. Bildtaggarna sparas i webbläsaren, kopplade till bildnamnet.
- **Lås en bild (🔓/🔒):** en låst bild visas alltid, även när **🎯** (bara bilder med markerad rad) är på och den markerade raden inte finns på bilden.
- Utan bildmapp sparas bilderna i webbläsaren, kopplade till CSV-filens namn. Det gäller också som reserv om mappen inte är kopplad.
