# Mapování na knihovnu komponent BSSHOP

Knihovna: https://claude.ai/artifact/Nb5GuTSZtkUHaZxvA2tzAz · breakpointy XXS 320 / XS 420 / S 550 / M 820 / L 1000 / XL 1362 / XXL 1745 (nad 1745 obsah na střed).

## Tokeny klienta (výběr)

| Token | Hodnota | Pozn. |
|---|---|---|
| `--c-primary` | `#D23E3E` | APRON červená (Figma) |
| `--c-dark`, `--c-footer`, `--c-nav-bg` | `#202020` | APRON černá |
| `--c-surface` | `#F2F2F2` | APRON bílá |
| `--c-topbar` | `#D23E3E` | horní lišta se zuby |
| `--c-price-sale` | `#B8302F` | ztmavená červená kvůli kontrastu malého textu |
| `--c-ok` | `#1E7A3C` | „Skladem“ – ztmaveno na 4,5 : 1 |
| `--font-body` | LINE Seed JP 400/700/800 | Google Fonts |
| `--tooth` | SVG zub | motiv „zubatého řezu“ z loga |

## Sekce homepage → komponenty

| Sekce na webu | Komponenta knihovny | Varianta / poznámka |
|---|---|---|
| Červená horní lišta | Header › topbar | zubatá spodní hrana; jen „Volná pracovní pozice“ |
| Hlavička | Header | kontakt + prodejna od 1200/1362 px, výběr měny (dropdown) za košíkem, hamburger vpravo pod L |
| Lišta kategorií + mega menu | Header (navStyle bar) + mega menu | **nové:** stejná výška panelů, fotka kategorie vpravo s bílými zuby, ikonový štítek se zubem, plynulé prolnutí mezi kategoriemi, ztmavení + blur pozadí |
| Vyhledávání | SearchField | **nové:** našeptávač (kategorie / produkty / články), shoda kódu, zkratka „/“, fullscreen na mobilu |
| Hero „řezy“ | HeroBanners | **nová varianta:** svislé pásy, aktivní se rozevře; autopřepínání 7 s, najetí 0,6 s (červené plnění), mobil = řádky se zuby |
| USP | UspBar | varianta „velké číslo + popisek“, bez ikon a oddělovačů |
| Hlavní kategorie | CategoryTiles | **nová varianta:** 3 foto dlaždice na výšku + 4 podkategorie jako štítky; ostatní kategorie kompaktně |
| Vybrali jsme pro vás | ProductCarousel + TabBar + ProductCard | karta: fotka, tabulka parametrů (Ø/řez/otvor/zuby z názvu), název, popis 2 ř., sklad, cena s/bez DPH, množství + do košíku |
| Navigace carouselu | Pagination (slider) | **nové:** počítadlo 01/06 + čárky podle počtu posunů + šipky vlevo, tlačítko „Vše“ vpravo; použito i u recenzí |
| Prodejna, servis a výdej | PromoBanner | **nová varianta:** široké pruhy foto + panel se zuby, střídání stran, velké slovo přes fotku |
| Recenze | ReviewCarousel (nové) | Heureka, stejný slider |
| Rady a tipy | ArticleTeasers | **nová varianta:** nejnovější článek velký + seznam 3 s náhledem |
| Naše značky | BrandStrip | loga v šedé, barevná po najetí |
| Newsletter | NewsletterForm | — |
| Patička | Footer | **nová:** animace řezu (saw-edge.svg), velký telefon + stav „otevřeno teď“, 3 kontaktní osoby, doprava a platby, 3 sloupce odkazů, právní odkazy dole, obří logo |
| Tlačítka | Button | **nové:** hover – ze spodní hrany vyjede kotouč v barvě tlačítka, projede a zajede |

## Motiv pily

- `assets/img/saw-edge.svg` – samostatná animace (zuby + piliny), cyklus 9 s s pauzami; respektuje `prefers-reduced-motion`.
- Zub (`--tooth`) se opakuje na štítcích, badge „Akce“, hraně fotek, lištách.

## Přístupnost

Skutečné `button`/`a`/`input` s popisky, viditelný focus, ovládání klávesnicí (mega menu šipky + Esc, hero, slider, našeptávač), `prefers-reduced-motion` vypíná animace a autopřepínání.
