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
