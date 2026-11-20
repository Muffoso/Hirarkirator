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
- `Taggar` (även `Tags`): kommaseparerade taggar. Taggkolumnen kan ligga var som helst bland fälten och flyttas som ett fält i appen. Klicka i en taggcell för att redigera taggarna.
- Flytta en rad (med underrader) genom att dra i ⋮⋮. Håll **Ctrl** när du släpper för att kopiera i stället. Är raden ikryssad följer alla ikryssade rader med. Kopiorna får inga bildmarkeringar.
- Alla övriga kolumner är fält. Du kan lägga till, ta bort, byta namn på och ändra ordning på dem i appen.
- Filen skrivs som UTF-8 med BOM, så att Excel visar å, ä och ö rätt. Den kan också läsa ANSI-filer som sparats från Excel.

Se `exempel.csv`.

## Filtrering och zoom

- **Taggfiltret** i den översta raden (🏷) filtrerar både raderna och bilderna. En bild visas om den själv har taggen eller om den har markeringar för någon av de framfiltrerade raderna. Klicka på en tagg, i filtret eller på en bild, för att slå på eller av den. Med flera valda taggar väljer du om raderna och bilderna ska ha **någon** eller **alla** av dem.
- **Taggfärger:** högerklicka på en tagg (i listan, i filtret eller på en bild) och välj en färg, grå eller **Automatisk färg**. Färgerna sparas i webbläsaren.
- **Ctrl + scrollhjul över listan** zoomar listan (50–250 %).

## Bilder och markeringar

Till höger om listan kan du lägga till bilder och märka ut rader på dem med numrerade cirklar. Dra en rad till en bild, eller använd **📍** (placera markering). Bilderna anpassas som standard så att de fyller bildytans bredd.

- **Zooma bilder:** klicka på en bild och använd Ctrl + scrollhjul för att zooma bara den bilden. Klicka på bakgrunden i bildytan för att zooma alla bilder. Procentknappen visar vad som är valt (🖼 en bild, 🗔 alla) och sätter zoomen till 100 % när du klickar på den. **⤢** (Anpassa) gör att bilden, eller alla bilder om ingen är vald, fyller bredden igen. Esc eller ett klick utanför bildytan avbryter valet.
- Markeringarna sparas i CSV-kolumnen `Bildmarkeringar`, i formatet `bild.png@x,y | bild2.jpg@x,y`. x och y anges i procent av bildens bredd och höjd.
- **Bildmapp (rekommenderas):** klicka **📁** (välj bildmapp) och peka ut mappen där bilderna ligger, gärna samma mapp som CSV-filen. Bilderna hittas då via namnen i CSV-filen, så listan kan flyttas eller delas tillsammans med mappen. Bilder du lägger till kopieras in i mappen, men befintliga filer skrivs aldrig över. Mappvalet kommer ihåg per lista.
- Bilderna läses in från mappen varje gång sidan laddas, och när du går tillbaka till fönstret. Skriver du över en bildfil i mappen syns den nya versionen direkt. Efter en omladdning frågar Chrome ibland om åtkomst till mappen igen. Välj **Tillåt vid varje besök**, så slipper du frågan i fortsättningen. Fram till dess visas webbläsarens senast sparade kopior.
- **Taggar på bilder:** skriv i fältet **+ tagg** under bildnamnet och tryck Enter. Bildtaggarna ingår i det gemensamma taggfiltret överst. Bildtaggarna sparas i webbläsaren, kopplade till bildnamnet.
- **◉ / ☑ (vad som lyfts fram):** växlar mellan att lyfta fram markeringarna för bara den markerade raden (◉) eller för alla ikryssade rader (☑). **🎯** följer samma val.
- **Lås en bild (🔓/🔒):** en låst bild visas alltid, även när **🎯** (bara bilder med markerad rad) eller taggfiltret annars skulle dölja den.
- Utan bildmapp sparas bilderna i webbläsaren, kopplade till CSV-filens namn. Det gäller också som reserv om mappen inte är kopplad.
