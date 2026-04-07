# Inventarizační analýza mirroru banka-projektu.cz

> **Zdroj:** `D:\!Mira Main\Banka-projektu\banka-projektu\www.banka-projektu.cz\`
> **Datum analýzy:** 7. dubna 2026
> **Účel:** Podklad pro migraci ze statického mirroru WordPress webu do Astro

---

## 1. Souhrn mirroru

| Metrika | Hodnota |
|---|---|
| Celkem souborů | 370 |
| HTML souborů | 310 |
| JPG | 38 |
| GIF | 10 |
| PNG | 5 |
| PDF | 3 |
| CSS | 1 |
| JS | 1 |
| XML (RSS feed) | 1 |
| TXT (robots.txt apod.) | 1 |
| **Celková velikost** | **15 MB** |
| Nejstarší soubor | 16. 4. 2010 (feed/index.html — RSS) |
| Nejnovější soubory | 7. 4. 2026 (stažení mirroru — Byty-1.jpg, Byty-5.jpg, rekonstrukce1.jpg) |

Reálný obsah webu pochází z období **2010–2011**. Novější datumy odpovídají okamžiku stažení HTTrack mirrorem. Web nebyl po roce 2010 obsahově aktualizován.

---

## 2. Mapa top-level adresářů

| Adresář | HTML souborů | Hodnocení | Důvod |
|---|---|---|---|
| `sablony/` | 289 | **PATŘÍ DO MIGRACE** | Jádro webu — všechny projektové šablony s kapitolami |
| `caste-dotazy/` | 2 | **PATŘÍ DO MIGRACE** | Obsahová stránka (FAQ) |
| `dalsi-doporuceni/` | 1 | **PATŘÍ DO MIGRACE** | Obsahová stránka |
| `kontakt/` | 1 | **PATŘÍ DO MIGRACE** | Kontaktní stránka |
| `nabidka-sluzeb/` | 2 | **PATŘÍ DO MIGRACE** | Obsahová stránka |
| `nejcastejsi-rizika-a-chyby/` | 1 | **PATŘÍ DO MIGRACE** | Obsahová stránka |
| `o-nas/` | 2 | **PATŘÍ DO MIGRACE** | Obsahová stránka |
| `projektovy-dotahovac/` | 2 | **PATŘÍ DO MIGRACE** | Obsahová stránka |
| `rizeni-projektu/` | 2 | **PATŘÍ DO MIGRACE** | Obsahová stránka |
| `seminare/` | 2 | **PATŘÍ DO MIGRACE** | Obsahová stránka |
| `ucast-firmy-na-veletrhu/` | 1 | **OVĚŘIT** | Existuje i jako šablona v `sablony/` — může být duplikát |
| `feed/` | 1 | **IGNOROVAT** | RSS feed (XML soubor s příponou .html) |
| `wp-content/` | 0 | **ČÁSTEČNĚ MIGROVAT** | Obrázky a přílohy z `uploads/` ano; téma a engine ne |
| `wp-includes/` | 0 | **IGNOROVAT** | WordPress engine soubory |

Soubory v kořeni:
- `index.html` — **PATŘÍ DO MIGRACE** (hlavní stránka)
- `favicon.html` — **IGNOROVAT** (crawl artefakt, HTTrack přejmenoval favicon.ico)
- `xmlrpc.html`, `xmlrpc0db0.html` — **IGNOROVAT** (WordPress XML-RPC endpoint, bezpečnostní riziko)

---

## 3. Inventář šablon (sablony/)

Celkem **18 adresářů šablon** + 1 soubor `index.html` (rozcestník) + 1 `feed/` (RSS).

### Plně rozvinuté šablony (12)

| # | Slug | Lidský název | Kapitol | HTML souborů | index.html (KB) |
|---|---|---|---|---|---|
| 1 | `akce-maturitniho-rocniku` | Akce maturitního ročníku | 11 | 24 | 39,0 |
| 2 | `koupe-bytu` | Příprava a organizace koupě bytu | 9 | 20 | 73,6 |
| 3 | `letni-brigada-v-zahranici-eu` | Letní brigáda v zahraničí (EU) | 11 | 24 | 39,0 |
| 4 | `organizace-sportovniho-turnaje` | Organizace sportovního turnaje | 11 | 24 | 37,9 |
| 5 | `poradani-detskeho-dne` | Pořádání dětského dne | 11 | 24 | 38,5 |
| 6 | `prechod-firmy-na-euro` | Přechod firmy na euro | 11 | 23 | 37,9 |
| 7 | `prechod-na-platce-dph` | Přechod na plátce DPH | 9 | 20 | 89,5 |
| 8 | `rekonstrukce-bytoveho-jadra` | Rekonstrukce bytového jádra | 9 | 20 | 39,7 |
| 9 | `spolufinancovani-z-fondu-eu` | Spolufinancování z fondů EU | 10 | 23 | 66,0 |
| 10 | `svatba` | Příprava a organizace svatby | 13 | 28 | 54,9 |
| 11 | `ucast-firmy-na-veletrhu` | Účast firmy na veletrhu | 10 | 22 | 36,5 |
| 12 | `zalozeni-obcanskeho-sdruzeni` | Založení občanského sdružení | 11 | 24 | 35,9 |

### Neúplné / stub šablony (5)

| Slug | HTML souborů | Poznámka |
|---|---|---|
| `expanze-firmy-do-zahranici` | 2 | Pouze rozcestník + feed, žádné kapitoly |
| `poradani-konference` | 2 | Pouze rozcestník + feed |
| `porizeni-webovych-stranek` | 2 | Pouze rozcestník + feed |
| `predani-rodinneho-podniku` | 2 | Pouze rozcestník + feed |
| `stavba-rodinneho-domu` | 2 | Pouze rozcestník + feed |

### Redirect (1)

| Slug | Poznámka |
|---|---|
| `pracovni-pozice` | 0,9 KB — redirect stránka ("Page has moved"), ne skutečná šablona |

### Společné kapitoly (jádro)

Většina plných šablon sdílí tento standardní set kapitol:
- `cile-a-prinosy-projektu`
- `mozne-pristupy-a-strategie-projektu`
- `nejcastejsi-rizika-a-chyby`
- `obvykle-zainteresovane-strany`
- `poznamky-k-jednotlivym-aktivitam-a-realizaci-projektu`
- `pravni-uprava-predmetu-projektu-ci-jeho-realizace`
- `priklad-rozpoctu-a-finance-projektu`
- `urceni-rozsahu-a-struktury-aktivit-v-projektu`
- `dalsi-doporuceni-informacni-zdroje-firmy-atp`

Některé šablony mají navíc přílohy (`priloha-*`). Šablona `ucast-firmy-na-veletrhu` používá odlišnou konvenci — ke každému slugu přidává suffix `-veletrh`.

### Distribuce počtu kapitol

| Kapitol | Šablon |
|---|---|
| 0 (stub/redirect) | 6 |
| 9 | 3 |
| 10 | 2 |
| 11 | 6 |
| 13 | 1 |

---

## 4. Analýza HTML struktury

### Analyzované soubory

1. **Hlavní stránka:** `index.html`
2. **Rozcestník šablony:** `sablony/stavba-rodinneho-domu/index.html`
3. **Kapitola:** `sablony/spolufinancovani-z-fondu-eu/mozne-pristupy-a-strategie-projektu/index.html`

### Layout (shodný napříč všemi třemi)

```
<body>
  <DIV id="main">
    <DIV id="header">            ← logo (#hlogo), motto (#hmotto), breadcrumb (.breadcrumb)
    <div class="colmask leftmenu">
      <div class="colright">
        <div class="col1wrap">
          <div class="col1">
            <div class="rounded ...">
              <div id="dvobsah">   ← HLAVNÍ OBSAHOVÝ KONTEJNER
                <div class="inside">
                  <div class="title"><h1>...</h1></div>
                  <div class="content_text">
                    <div class="indentX">  ← ČLÁNKOVÝ TEXT
        <div class="col2">          ← LEVÝ SIDEBAR (navigace)
  <div id="footer">                 ← PATIČKA

  <div style="display:none">        ← SPAM (viz sekce 6)
  <div style="display:none">        ← SPAM
```

### Selektor pro hlavní obsah

**`#dvobsah .inside`** — obsahuje nadpis (`h1`) i text článku.

Pro jemnější extrakci:
- Nadpis: `#dvobsah .title h1`
- Tělo článku: `#dvobsah .content_text .indentX`

### Selektory k odstranění

| Co | Selektor |
|---|---|
| Header (logo, motto, drobečky) | `#header` |
| Levý sidebar s navigací | `.col2` |
| Patička | `#footer` |
| Metadata příspěvku | `.postmetadata` |
| Komentáře (výpis) | `h3#comments`, `ol.commentlist` |
| Komentářový formulář | `h3#respond`, `form#commentform` |
| Spacer obrázky | `img[src*="spacer.gif"]` |
| Spam divy | `div[style="display:none"]` |
| Všechny skripty | `<script>` (GA tracker + rounded-corners.js) |

### Formuláře, iframy, embeddy

| Prvek | Hlavní str. | Rozcestník | Kapitola |
|---|---|---|---|
| `<form>` | Ne | Ano (komentáře) | Ano (komentáře) |
| `<iframe>` | Ne | Ne | Ne |
| JS embed | Ne | Ne | Ne |

### Tracking skripty

- **Google Analytics** (klasický `ga.js`): ANO, tracker `UA-15865053-1` — přítomen na všech stránkách
- Facebook Pixel: Ne
- Smartlook: Ne
- Jiný tracking: Ne

### WordPress verze a pluginy

- **WordPress 2.9.2** (z `<meta name="generator">`)
- **All in One SEO Pack 1.6.10.2** (z HTML komentáře)
- **Breadcrumb NavXT 3.4.1** (z HTML komentáře, na podstránkách)
- Žádné moderní pluginy (Elementor, Gutenberg bloky apod.)

### Navržený FINÁLNÍ extraktor

```
EXTRACT:    #dvobsah
  title:    #dvobsah .title h1
  body:     #dvobsah .content_text .indentX

REMOVE:
  #header
  .col2
  #footer
  h3#comments
  ol.commentlist
  h3#respond
  form#commentform
  .postmetadata
  img[src*="spacer.gif"]
  div[style="display:none"]
  script
```

Struktura je **konzistentní** na všech třech typech stránek. Jeden extraktor pokryje celý web.

---

## 5. Analýza komentářové sekce

### Struktura HTML komentářů

```html
<!-- Výpis existujících komentářů (pouze 14 stránek) -->
<h3 id="comments">Komentare (3)</h3>
<ol class="commentlist">
  <li class="alt" id="comment-84">
    <strong><a class="url">jméno autora</a></strong>
    <small class="commentmetadata">datum</small>
    <p>text komentáře</p>
  </li>
</ol>

<!-- Formulář pro přidání komentáře (141 stránek) -->
<h3 id="respond">Vylepsete komentarem tento obsah.</h3>
<form action="wp-comments-post.php" method="post" id="commentform">
  <textarea name="comment" id="comment"></textarea>
  <input name="submit" id="submit" value="Pridej komentar" />
</form>
```

### Statistiky

| Prvek | Počet souborů |
|---|---|
| `<form` (jakýkoli formulář) | 141 |
| `id="commentform"` | 141 |
| `id="respond"` | 142 |
| Skutečné komentáře (`ol.commentlist`) | 14 |

### Selektory k odstranění

```
#respond          (nadpis "Vylepšete komentářem...")
#commentform      (formulář)
#comments         (nadpis "Komentáře (N)")
ol.commentlist    (výpis komentářů)
```

Komentáře jsou vesměs legitimní (uživatelské reakce na obsah). Při migraci je můžeme bezpečně zahodit — není jich dost na to, aby stálo za to je převádět.

---

## 6. Analýza spamu / kompromitace

### VERDIKT: WEB BYL KOMPROMITOVÁN

**155 ze 310 HTML souborů (50 %)** obsahuje indonéský gambling spam injektovaný do skrytých `<div>` bloků.

### Nalezené termy

| Hledaný řetězec | Počet souborů |
|---|---|
| `judi slot` | 155 |
| `slot gacor` | 155 |
| `joker123` | 155 |
| `slot pulsa` | 155 |
| `slot deposit` | 155 |
| `slot terpercaya` | 155 |
| `Slot88` | 155 |
| `slot 2022` | 0 |
| `togel` | 0 |
| `casino` | 0 |

### Umístění

Spam je na konci `<body>`, těsně před `</body></html>`, ve **dvou `<div style="display:none">` blocích**. Klasická SEO spam injekce — neviditelná pro uživatele, ale čitelná pro vyhledávače.

### Ukázka kontextu

```html
<div style="display:none">
<a href="../external.html?link=https://restorecal.org/">judi slot gacor</a>
<a href="../external.html?link=https://slot88.media-b2c.quotatis.fr/">Slot88</a>
<a href="../external.html?link=https://popacular.com/">slot pulsa</a>
...
</div>
```

Každý blok obsahuje ~8–10 odkazů na gambling domény s indonéskými anchor texty. URL jsou přepsané přes HTTrack `external.html?link=` wrapper.

### Vzorové zasažené soubory

- `index.html`
- `caste-dotazy/index.html`
- `favicon.html`
- `sablony/svatba/index.html`
- `sablony/koupe-bytu/cile-a-prinosy-projektu/index.html`

### Dopad na migraci

Selektor `div[style="display:none"]` v extraktoru spolehlivě odstraní veškerý spam. Žádný z legitimních obsahů webu nepoužívá `display:none`.

---

## 7. Analýza obrázků a příloh

### Soubory v wp-content/uploads/ (45 souborů)

#### Velké soubory (> 100 KB)

| Soubor | Velikost |
|---|---|
| Byty-1.jpg | 1 557 KB |
| Byty-5.jpg | 891 KB |
| rekonstrukce1.jpg | 552 KB |
| Spolufinancování-z-fondů-EU-rozpočet.jpg | 442 KB |
| moderni-tablo.jpg | 386 KB |
| Spolufinancování-z-fondů-EU-rozpočet-1024x963.jpg | 306 KB |
| Dotazník-k-uzavření-manželství-Uherské-Hradiště.pdf | 280 KB |
| Struktura-aktivit-projektu.png | 184 KB |
| Foto8.jpg | 129 KB |

#### WordPress thumbnail varianty (15 souborů)

Soubory s příponou `-300x200`, `-300x201`, `-200x300`, `-300x233`, `-300x196`, `-1024x963` jsou automaticky generované thumbnaily. Všechny > 5 KB.

#### Soubory < 5 KB (potenciálně poškozené)

| Soubor | Velikost |
|---|---|
| **pohar.jpg** | **4,5 KB** |

Pouze jeden soubor pod hranicí. Při 4,5 KB to může být legitimní malá ikona.

#### PDF přílohy

| Soubor | Velikost |
|---|---|
| Dotazník-k-uzavření-manželství-Uherské-Hradiště.pdf | 280 KB |
| Vzor_predmanzelska_smlouva.pdf | 47 KB |
| Osvedceni_o_uzavreni_cirkevniho_snatku.pdf | 43 KB |

Všechny tři PDF se vztahují k šabloně `svatba`.

### Sirotci (soubory bez odkazu z HTML)

**Žádní skuteční sirotci.** Všechny soubory v `uploads/` jsou odkazované z HTML. Některé mají v HTML URL-enkódované názvy (české znaky → `%c3%a1` apod.), ale prohlížeč je rozřeší správně.

### Chybějící přílohy

**Žádné chybějící přílohy** pro `wp-content/uploads/`. Všechny `<img src>` a `<a href>` směřující na uploads se rozřeší na existující soubory.

Jeden chybějící soubor v tématu:
- `wp-content/themes/theme665/images/bgpata.png` — odkazován v CSS, ale na disku neexistuje (pozadí patičky). Nedůležité pro migraci.

### Soubory v wp-content/themes/ (11 souborů)

| Soubor | Velikost | Použití |
|---|---|---|
| bgstin.gif | 26,9 KB | CSS pozadí sloupců |
| style-n.css | 9,4 KB | Jediný stylesheet |
| rounded-corners.js | 8,1 KB | JS pro zaoblené rohy |
| motto.gif | 4,0 KB | Logo motto v headeru |
| logon.png | 2,9 KB | Logo obrázek |
| pimp2.gif | 1,0 KB | Ikona komentářů |
| bgbody.gif | 0,4 KB | CSS pozadí body |
| rss.png | 0,4 KB | RSS ikona |
| pimp1.gif | < 0,1 KB | Odrážka v navigaci |
| line.gif | < 0,1 KB | Oddělovací linka |
| spacer.gif | < 0,1 KB | Spacer (145 HTML souborů) |

---

## 8. Externí odkazy

### Legitimní domény

| Doména | Odkazů | Vzorové URL |
|---|---|---|
| www.banka-projektu.cz | 155 | Self-referenční odkazy (absolutní URL v mirroru) |
| www.utb.cz | 5 | Univerzita Tomáše Bati |
| www.hranostaj.cz | 1 | Dětské hry |
| www.babyoffice.cz | 1 | Dětský nábytek |
| zpravy.aktualne.cz | 1 | Zpravodajský server |
| www.svetinterieru.cz | 1 | Interiérový magazín |
| www.sportovnipohary.cz | 1 | Sportovní poháry |
| www.ridelliconstruction.cz | 1 | Stavební firma |
| www.psp.cz | 1 | Parlament ČR |
| www.prozi.cz | 1 | Projektový management |
| www.prace-v-zahranici.superko.com | 1 | Práce v zahraničí |
| www.centrumprace.eu | 1 | Centrum práce |
| www.9pramenu.cz | 1 | Restaurace/hotel |
| finance.idnes.cz | 1 | Finanční zpravodajství |
| decisionlab.fsv.cvut.cz | 1 | ČVUT laboratoř |

### Podezřelé / spam domény (17 domén)

Všechny pocházejí z injektovaných spam bloků (`display:none`):

| Doména | Odkazů | Poznámka |
|---|---|---|
| restorecal.org | 5 | Gambling redirect |
| slot88.media-b2c.quotatis.fr | 5 | Hijacked subdomain |
| slot-pulsa.test-infrastructure.fourthwall.com | 5 | Hijacked subdomain |
| slot-pulsa.dev2.enlightedinc.com | 5 | Hijacked subdomain |
| slot-pulsa.5thanniv.finalfantasyrecordkeeper.com | 5 | Hijacked subdomain |
| slot-gacor.kc-core-dev.gcp.oreilly.com | 5 | Hijacked subdomain O'Reilly |
| savayaslot303.arte-dev.artefact.com | 5 | Hijacked subdomain |
| savaya303.cloud.gigaspaces.com | 5 | Hijacked subdomain |
| popacular.com | 5 | Gambling redirect |
| occmakeup.com | 5 | Gambling redirect |
| link-slot-gacor.topacademy.wagor.tc.edu.tw | 5 | Hijacked .edu.tw subdomain |
| kreditgratis.com | 5 | Gambling |
| joker123.ouroboros.ultimaker.com | 5 | Hijacked subdomain Ultimaker |
| slot88.p1.wrc.com | 5 | Hijacked subdomain WRC |
| slot-deposit-pulsa.learning.moleskine.com | 5 | Hijacked subdomain Moleskine |
| dev.binderhub.gcp.oreilly.com | 10 | Hijacked subdomain O'Reilly |

Útočník využil hijacknuté subdomény legitimních firem (O'Reilly, Moleskine, Ultimaker, Fourthwall, GigaSpaces, WRC) jako redirect cíle.

---

## 9. Rozbité interní odkazy

### a) Cílový soubor neexistuje v mirroru

**Počet: 2**

1. `/favicon.ico` — odkazován z HTML, ale v mirroru existuje pouze `favicon.html` (crawl artefakt)
2. Relativní odkazy bez koncového lomítka (`../priklad-rozpoctu-a-finance-projektu`) — adresář existuje s `index.html` uvnitř, ale závisí na konfiguraci serveru, zda se přesměruje

### b) Zdvojené cesty `/sablony/X/sablony/Y/`

**Počet: 3 soubory** (crawl artefakty z HTTrack)

| Soubor | Odkazováno z |
|---|---|
| `sablony/poradani-detskeho-dne/sablony/letni-brigada-v-zahranici-eu/index.html` | Sidebar navigace v poradani-detskeho-dne |
| `sablony/poradani-detskeho-dne/sablony/prechod-firmy-na-euro/index.html` | Sidebar navigace v poradani-detskeho-dne |
| `sablony/prechod-firmy-na-euro/sablony/svatba/index.html` | Sidebar navigace v prechod-firmy-na-euro |

Tyto 3 soubory jsou **duplikáty** skutečných stránek, které HTTrack vytvořil, když následoval relativní sidebar odkazy. Při migraci je ignorovat.

### c) Crawl artefakt

- `sablony/spolufinancovani-z-fondu-eu/dalsi-doporuceni-informacni-zdroje-firmy-atp/www.rra.html` — HTTrack zachytil externí odkaz na www.rra.cz jako lokální soubor. Ignorovat.

---

## 10. Analýza stylu webu

### CSS soubory

Web načítá **jediný stylesheet:**
- `wp-content/themes/theme665/style-n.css` (9,4 KB)

### Fonty

- **Font-family:** `Tahoma` (definován na `body`)
- Žádné webfonty (Google Fonts, @font-face) — web používá pouze systémový font
- Input/textarea: `Tahoma 11px`

### Barevná paleta (5 nejčastějších)

| Barva | Hex | Použití |
|---|---|---|
| Černá | `#000000` | Text, ohraničení (7× v CSS) |
| Šedá | `#86888e` | Body text, metadata (4×) |
| Oranžovo-červená | `#e6633c` | Zvýrazněné popisky `.phlaska` (2×) |
| Tmavě hnědá | `#4a3b22` | Nadpisy h2 (2×) |
| Tmavě šedá | `#3a3a3a` | Patička, horní border (2×) |

Další důležité barvy:
- `#4c9cd2` — odkazy (modrá)
- `#e5e5e5` — pozadí body (světle šedá)
- `#fff` / `#ffffff` — pozadí obsahu (bílá)
- `#dbdbdb` — border pod h1

### Rozměry a typografie

| Vlastnost | Hodnota |
|---|---|
| Šířka kontejneru | `min-width: 50em; max-width: 80em` (na `#main`) |
| Šířka obsahového sloupce | Dynamická (2-column layout, sidebar 13.5em) |
| Font-size (body) | `100%` (= 16px výchozí) |
| Line-height | `1.3` |
| H1 font-size | `1.3em` (~21px) |
| H1 letter-spacing | `1px` |
| Max-width odstavce | `50em` |
| Margin `#dvobsah` | `0 3em` |

### Vizuální charakter

Layout je **dvousloupcový** s levým sidebarem. Obsahový blok má bílé pozadí se zaoblenými rohy (generované JavaScriptem, ne CSS `border-radius` — web je z éry IE6/7). Celkový dojem: čistý, minimalistický, ale zastaralý design z roku ~2010.

---

## 11. WordPress specifika

### Verze

| Komponenta | Verze |
|---|---|
| **WordPress** | **2.9.2** (leden 2010, kriticky zastaralý) |
| Téma | `theme665` (custom/zakoupené, žádná identifikace autora) |
| All in One SEO Pack | 1.6.10.2 |
| Breadcrumb NavXT | 3.4.1 |

### JavaScript knihovny

- **jQuery:** NE — web nepoužívá jQuery (neobvyklé pro WP, ale konzistentní s minimalistickým tématem)
- `rounded-corners.js` — custom skript od Pacholliniho (Matěj Novák, seky.nahory.net) pro CSS zaoblené rohy přes JavaScript (řešení pro IE)
- Google Analytics (`ga.js`) — klasická verze, ne Universal Analytics

### Bezpečnostní kontext

WordPress 2.9.2 je z ledna 2010 — má **16+ let** neaplikovaných bezpečnostních záplat. To vysvětluje:
1. Gambling spam injekci (50 % stránek)
2. Přístupný `xmlrpc.php` (zachycen jako `xmlrpc.html`)
3. Žádné moderní bezpečnostní hlavičky

Web byl s největší pravděpodobností kompromitován přes známou zranitelnost WP 2.x a používán jako farma SEO spam odkazů.

---

## 12. Doporučení pro další krok

### Strategie extrakce

**Doporučená knihovna: `cheerio` (Node.js)**

Důvody:
- HTML je jednoduchý, validní, bez JS-renderovaného obsahu
- Cheerio je rychlé, lehké, s jQuery-like API pro CSS selektory
- Zvládne 310 souborů za sekundy
- Alternativy `node-html-parser` (rychlejší, ale méně robustní) nebo `jsdom` (těžší, zbytečný overhead) nejsou potřeba

### Postup extrakce (návrh)

```
Pro každý HTML soubor:
1. Načti cheerio
2. Odstraň: #header, .col2, #footer, h3#comments, ol.commentlist,
   h3#respond, form#commentform, .postmetadata, img[src*="spacer.gif"],
   div[style="display:none"], script
3. Extrahuj title z: #dvobsah .title h1
4. Extrahuj body z: #dvobsah .content_text .indentX
5. Převeď na Markdown (turndown / rehype)
6. Ulož s frontmatter (title, slug, template, chapter-order)
```

### Co bude nejtěžší

1. **URL-enkódované české znaky v cestách k obrázkům** — soubory na disku mají UTF-8 názvy (např. `Spolufinancování-z-fondů-EU-rozpočet.jpg`), ale HTML na ně odkazuje přes `%c3%...` enkódování. Import skript musí tyto cesty správně přeložit.
2. **Rozlišení stub šablon od plných** — 5 šablon nemá kapitoly (jen rozcestník). Rozhodnout, zda je migrovat jako placeholdery nebo vynechat.
3. **Crawl artefakty** — 3 zdvojené cesty, 1 `www.rra.html`, `favicon.html` — musíme je explicitně vyloučit.

### Co mě překvapilo

- **WordPress 2.9.2** — tak starý web jsem nečekal. Je to verze z ledna 2010, nikdy nebyla aktualizována.
- **50 % stránek obsahuje gambling spam** — kompromitace je rozsáhlá, ale naštěstí izolovaná do `display:none` bloků, takže ji snadno odstraníme.
- **Žádný jQuery** — neobvyklé pro WordPress jakékoli éry.
- **Konzistence layoutu** — celý web používá identickou strukturu. Jeden extraktor pokryje 100 % stránek.
- **Žádné chybějící obrázky** — mirror je kompletní.

### Alternativní přístup k "tupý mirror → markdown"

Místo tupého převodu každého HTML na jeden Markdown soubor doporučuji:

1. **Strukturovaná kolekce v Astro** — každá šablona = 1 Astro content collection, každá kapitola = 1 Markdown soubor s `order` frontmatter. Rozcestník šablony generovat automaticky z metadat kolekcí.
2. **Thumbnail varianty ignorovat** — do migrace tahat pouze originální obrázky, Astro/Sharp vygeneruje responsive varianty.
3. **Stub šablony** — migrovat pouze rozcestníkový text jako draft, dokud se nerozhodne o jejich budoucnosti.
4. **Feed/RSS soubory** — nemigovat, Astro může generovat RSS z obsahu automaticky.

---

## 13. Další zjištění

### RSS feed

Soubor `feed/index.html` je ve skutečnosti XML (RSS 2.0). Obsahuje 2 příspěvky z dubna 2010 ("Probíhající průzkum" a "Zkušební provoz služby"). Potvrzuje, že web byl spuštěn v dubnu 2010 a od té doby nebyl obsahově aktualizován.

### Téma webu

Název tématu `theme665` naznačuje zakoupený/stažený šablonový theme (číslo = katalogové číslo). Nejde o custom vývoj.

### Spacer.gif

145 ze 310 HTML souborů obsahuje `spacer.gif` (průhledný 1×1px obrázek pro layout). Typický přežitek z éry tabulkových layoutů.

### HTTrack artefakty

Mirror byl stažen nástrojem HTTrack. Poznávací znaky:
- `external.html?link=` wrapper pro externí odkazy
- Duplicitní cesty (`/sablony/X/sablony/Y/`)
- `www.rra.html` (zachycený externí odkaz jako lokální soubor)
- Přejmenované soubory (favicon.ico → favicon.html, xmlrpc.php → xmlrpc.html)

### Soubor robots.txt

V mirroru existuje `.txt` soubor (pravděpodobně robots.txt), nebyl analyzován detailně — při migraci ignorovat.

### Kontaktní formulář

Na stránce `kontakt/` může být kontaktní formulář — pokud ano, bude potřeba ho nahradit statickou alternativou (mailto odkaz, nebo služba jako Formspree/Netlify Forms).
