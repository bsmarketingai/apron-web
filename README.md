# APRON – nový e-shop (dříve pilanamarket.cz)

Návrh a zároveň funkční prototyp homepage nového e-shopu **APRON** (nástroje na dřevo, prodejna Hulín).
Čisté HTML + CSS + JS, bez závislostí a bez build kroku. Postaveno z knihovny komponent **BSSHOP**.

- Živý náhled (claude.ai): https://claude.ai/artifact/V7ms4CT6BPFTLEZusG9LsT
- Vizuální identita (Figma): `33Jb3p8XkE4tT2CzTOPX9n`, node `37:7169` – „APRON — Návrh vizuální identity“
- Zdroj obsahu: https://www.pilanamarket.cz (kategorie, menu, produkty, kontakty, doprava, platby)

## Spuštění

Stačí otevřít `index.html` v prohlížeči, nebo spustit lokální server:

```bash
python3 -m http.server 8000   # → http://localhost:8000
```

Funguje i jako GitHub Pages (Settings → Pages → branch `main`, složka `/`).

## Struktura

```
index.html                  celá homepage (styly a skripty jsou inline)
assets/img/                 fotky (hero, kategorie, dílna), animace saw-edge.svg
assets/img/znacky/          loga výrobců
assets/img/produkty/        fotky produktů (viz SEZNAM-FOTEK.txt), _ukazka-kotouc.jpg = dočasná
assets/img/ikony/           ikony podkategorií mega menu (viz SEZNAM-IKON.txt)
data/menu.json              kompletní strom kategorií z pilanamarket.cz
docs/KOMPONENTY.md          mapování na knihovnu BSSHOP, tokeny, chování
```

## Stav a co chybí

| Oblast | Stav |
|---|---|
| Fotky produktů | dočasně jedna ukázková fotka; názvy souborů v `assets/img/produkty/SEZNAM-FOTEK.txt` – nahraná fotka se zobrazí automaticky |
| Krátké popisy produktů | zástupný text `[…]` – doplnit z detailu produktu |
| Ikony podkategorií (mega menu) | zástupné; názvy v `assets/img/ikony/SEZNAM-IKON.txt` (bílé SVG, zobrazí se automaticky) |
| Fotky mega menu u 7 kategorií | ilustrační – doplnit |
| Blog | názvy/data ze souhrnu, odkazy vedou na rubriku Rady a tipy – doplnit přesné URL a titulní fotky |
| Fotky prodejny/servisu/skladu | ilustrační – na webu jsou `prodejna_01–06.jpg` |
| Pilana Metal | odkaz na stránku značky nenalezen → vede na „Naše značky“ |
| Košík, hledání, měna, newsletter | jen prototypové chování v prohlížeči (bez backendu) |
| Ceny bez DPH | dopočítané z ceny s DPH (÷ 1,21) |

## Napojení na e-shop (pro programátora)

- Data na homepage jsou v `index.html` v JS konstantách: `CATS`, `MENU`, `P` (produkty), `POSTS`, `BRANDS`, `FOOT`, `REVIEWS`.
  Při napojení na BSSHOP/Pohodu je nahradit daty ze šablony e-shopu.
- Vyhledávací našeptávač hledá jen v datech stránky – pro celý katalog napojit na fulltext e-shopu.
- Barvy, písmo a zaoblení jsou v CSS proměnných (`:root`, názvy dle knihovny BSSHOP).

## Odesílání změn

Úpravy dělá Claude přímo ve složce `web` (= tento repozitář). V GitHub Desktop pak stačí
**Commit to main → Push origin**.
