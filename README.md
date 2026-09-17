# SlovíčKO 📖

Denná dávka anglických slovíčok. Každý deň 10 nových slov (ktoré si ešte
nevidel), popáruješ slovenčinu s angličtinou ťahaním, a keď to isté kolo
zvládneš 3× za sebou, deň sa započíta do kalendára/série.

Databáza obsahuje **2222 slovíčok** (bežná slovná zásoba, zoradená voľne
podľa tém, bez duplicitných slovenských prekladov). Dá sa kedykoľvek
rozšíriť – stačí pridať ďalšie dvojice do `words.js`.

Appka funguje obojsmerne (ťahaj slovo z ktorejkoľvek strany na druhú),
ozve sa pri správnom aj nesprávnom spárovaní, a po splnení dňa si vieš
kedykoľvek pridať ďalšiu dobrovoľnú dávku navyše.

## Ako appku aktualizovať (odteraz jednoduchšie)

Appka je teraz postavená tak, že **takmer všetky budúce úpravy budú znamenať
len nahradenie jedného súboru: `index.html`** (obsahuje aj vzhľad aj
logiku appky dokopy). Súbory `manifest.json`, `sw.js`, `words.js` a priečinok
`icons` sa menia len výnimočne (napr. pri rozšírení slovnej zásoby).

Postup pri aktualizácii cez GitHub Desktop:
1. V priečinku repozitára na disku **prepíš iba `index.html`** tým novým,
   čo ti pošlem (nie kopírovať vedľa, ale skutočne nahradiť ten istý súbor
   rovnakého mena).
2. V GitHub Desktop uvidíš zmenu len pri `index.html`.
3. Summary → Commit → Push origin.
4. Appku na telefóne zatvor a znova otvor.

## Ako to dostať na telefón (GitHub Pages)

1. Vytvor si nový repozitár na GitHube (napr. `slovicko`) a nahraj doňho
   **všetky súbory z tohto priečinka** (cez "Add file → Upload files",
   alebo `git push`, podľa toho, čo ti vyhovuje).
2. V repozitári choď do **Settings → Pages**.
3. Pri "Source" vyber vetvu `main` a priečinok `/ (root)`, ulož.
4. Za pár minút ti GitHub vygeneruje adresu v tvare
   `https://TVOJE_MENO.github.io/slovicko/`.
5. Otvor tú adresu v telefóne (Safari na iPhone / Chrome na Androide).
6. iPhone: klepni na tlačidlo zdieľania → **"Pridať na plochu"**.
   Android (Chrome): otvorí sa ponuka → **"Pridať na plochu"** /
   "Nainštalovať appku".
7. Na ploche pribudne ikonka SlovíčKO a appka sa spúšťa ako normálna appka,
   bez adresného riadku prehliadača. Funguje aj čiastočne offline (service
   worker si stránku uloží do cache).

## Poznámka k ukladaniu postupu

Appka je čisto statická stránka (žiadny server), takže si postup
(videné slová, splnené dni, séria) pamätá **priamo v telefóne** cez
`localStorage`. Ak appku odinštaluješ alebo vymažeš dáta prehliadača,
postup sa stratí. Medzi rôznymi zariadeniami sa postup nezdieľa.

## Rozšírenie slovnej zásoby

Otvor `words.js` a pridaj ďalšie dvojice v tvare:
```js
["english word","slovenský preklad"],
```
Appka sama zabezpečí, že sa nové slová dostanú do rotácie a nebudú sa
opakovať so slovami, ktoré si už videl.
