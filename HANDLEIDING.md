# Handleiding — de CustomerFirst-website zelf onderhouden

Deze gids is geschreven voor Ton. Je hebt géén programmeerkennis of speciale
software nodig: alles kan rechtstreeks in de browser, op github.com.

---

## 1. Hoe de site in elkaar zit

De hele website is **één bestand**: `index.html`. Daarin staat alles — de teksten,
de vormgeving, de afbeeldingen (ingebakken) en de status-tracker. Er is verder
niets om te installeren of bij te houden.

Elke wijziging die je in `index.html` opslaat ("commit"), staat **1 à 2 minuten
later automatisch live** op https://cfirstproject.github.io. Meer is publiceren
niet.

## 2. De status van het huidige werk bijwerken (meest voorkomende klus)

1. Ga naar de repository op github.com en klik op `index.html`.
2. Klik rechtsboven op het **potlood-icoon** (Edit this file).
3. Zoek met `Ctrl/Cmd + F` naar `CURRENT_WORK`. Je vindt dit blok (onderaan het
   bestand):

   ```js
   const CURRENT_WORK = {
     number: "Work I",
     title: "Carbon Presence",
     stage: 2,
     stateLabel: "In creation",
     note: "The individual has been chosen. Who they are remains between the work and them — unless, one day, they choose to speak."
   };
   ```

4. Pas de waarden aan:
   - `number` — het volgnummer van het werk ("Work I", "Work II", …).
   - `title` — de titel van het werk.
   - `stage` — waar het werk nu staat, als getal **1 t/m 7**:
     | # | Fase |
     |---|------|
     | 1 | Selection |
     | 2 | Creation |
     | 3 | The letter |
     | 4 | Intermediary |
     | 5 | Message |
     | 6 | Contact |
     | 7 | The moment |
   - `stateLabel` — het korte label bij de oranje stip, bijv. `"In creation"`,
     `"In suspension"`, `"The letter is on its way"`, `"Completed"`.
   - `note` — de cursieve regel onder de tracker. Let op: laat de aanhalingstekens
     eromheen staan.
5. Klik rechtsboven op **Commit changes…**, geef eventueel een korte omschrijving
   ("status Work I naar fase 3") en bevestig. Klaar — even wachten en verversen.

**Begint er een nieuw werk?** Zet `number` op "Work II", vul de nieuwe `title` in
en zet `stage` terug op `1`.

## 3. Teksten aanpassen

Alle zichtbare teksten staan gewoon als leesbare tekst in `index.html`. Gebruik
`Ctrl/Cmd + F` om de zin te vinden die je wilt wijzigen, pas hem aan (let erop dat
je geen `<` of `>` tekens van de omliggende code weghaalt) en commit zoals
hierboven.

Handige ankerpunten om naar te zoeken:

- `hero-tag` — de tagline op het openingsscherm
- `id="now"` — de sectie met de status-tracker
- `id="concept"` — WHY / WHAT / HOW
- `id="letter"` — de brief (de naam blijft bewust geredigeerd)
- `The principles` — de vijf principes, waaronder *No publicity*
- `id="maker"` — jouw verhaal
- `From the studio` — het OWE₂-fragment

**Groter bewerken?** Druk in de repository op de toets `.` (punt) — dan opent
github.dev, een volwaardige editor in je browser, met dezelfde commit-knop.

## 4. Iets fout gegaan? Alles is terug te draaien

GitHub bewaart elke versie. Klik in de repository op **History** (bij
`index.html`) om oude versies te bekijken en terug te zetten. Je kunt dus niets
permanent kapotmaken.

## 5. Later: eigen domein cfirst.nl koppelen

1. Registreer `cfirst.nl` bij een registrar (bijv. TransIP of Mijndomein, ± €10/jaar).
2. In GitHub: **Settings → Pages → Custom domain** → vul `cfirst.nl` in.
3. Bij de registrar, in het DNS-beheer:
   - 4 × **A-record** voor `cfirst.nl` (naam `@`) naar: `185.199.108.153`,
     `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - 1 × **CNAME-record** voor `www` naar `cfirstproject.github.io`
4. Vink in GitHub **Enforce HTTPS** aan zodra dat kan (kan een uur duren).

## 6. Overdracht van het account

Het GitHub-account is opgezet om overgedragen te worden. Om het volledig van Ton
te maken: log in → **Settings → Emails** → voeg Tons e-mailadres toe en maak het
primair → wijzig het wachtwoord → zet twee-factor-authenticatie op Tons telefoon.
Vanaf dat moment is Ton eigenaar van site én geschiedenis.

---

*Vragen of iets groters bouwen (een archiefpagina per werk, foto's van het
maakproces, meertaligheid)? De site is er klaar voor — elke ontwikkelaar, of
Claude, kan met dit ene bestand direct verder.*
