# Oefenschrift (huiswerk-app)

Oefenapp voor huiswerk Engels en spelling op de basisschool. Privéproject.

## Opbouw

- Alles in **één bestand: `index.html`** (HTML, CSS en vanilla JS, geen build, geen libraries). Alleen Google Fonts wordt extern geladen. Houd dat zo.
- `lijsten.json` bevat voorbeeldlijsten. De losse versie laadt die als er in de browser nog geen lijsten staan.
- Dezelfde code draait ook als privé-Artifact op claude.ai. Daar gebruikt hij de `db`-capability (collecties `lijsten`, `voortgang/<kind-id>`, document `instellingen/algemeen`) en `sample` (foto van huiswerk lezen, leestekst maken). Zonder `window.claude` valt hij terug op `localStorage` en zijn de Claude-knoppen verborgen. Voor het Artifact publiceer je alles tussen `<head>` en `</body>` zonder de omhulling.
- `README.md` is de gebruikersuitleg. Werk die bij als de bediening verandert.

## Privacy (belangrijk)

- **Deze repo is openbaar.** Zet nooit namen, foto's, cijfers of andere gegevens van kinderen of het gezin in code, testdata, commits of screenshots. Kinderen staan alleen in `instellingen.kinderen`, ingevuld in de app.
- Gebruik in tests verzonnen namen.

## Didactiek (niet zomaar weghalen)

- Leitner-bakjes (`INTERVAL`), van herkennen naar zelf maken (`typeEngels`).
- Faqta: lesdoel, ik doe het voor, samen, controle met 80%-grens en verlengde instructie (`startSessie`, `verlengdeInstructie`), close reading in drie lezingen (`schermLezen`).
- STAAL: categorie, regel, schrijven, na een fout overtypen (`CATS`).
- Spelelementen (munten, winkel, weekmedailles, potloodfiguur) zijn een eigen ontwerp. Neem geen teksten, logo's of figuren van andere apps over.

## Stijl

- Alle tekst in de interface en alle commits in het Nederlands: korte zinnen, gewone woorden, voor kinderen van 8 tot 12.
- Kleuren alleen via de CSS-variabelen op `:root`; licht (schrift) en donker (schoolbord) zijn allebei gedefinieerd.
- Moet werken op de telefoon (390 px breed) zonder horizontaal scrollen.

## Testen

Headless met Playwright: start `python3 -m http.server` in de map, voeg via "Voor ouders" twee verzonnen kinderen toe, doorloop een ronde Engels (met controle), de leestekst, een ronde spelling en de winkel. Controleer op `pageerror`. Maak screenshots op 1100×860 en 390×780 (donker).
