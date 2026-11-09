# A mozgás szabadsága – honlap v1

Ez a csomag a honlap első, GitHubra és Cloudflare-re közvetlenül feltölthető statikus változata.

## Fájlszerkezet

```text
/
├── index.html
├── 404.html
├── robots.txt
├── sitemap.xml
├── site.webmanifest
├── kiadoknak/
│   └── index.html
├── adatkezeles/
│   └── index.html
└── assets/
    ├── css/
    │   └── styles.css
    ├── js/
    │   └── site.js
    └── images/
        ├── favicon.svg
        ├── og-cover.jpg
        ├── guggolas.jpg
        ├── mobilitas-allva.jpg
        ├── mobilitas-talajon.jpg
        └── ero-korlaton.jpg
```

## Feltöltés GitHubra

1. A repository gyökerében töröld vagy írd felül a jelenlegi `index.html` fájlt.
2. Töltsd fel a csomag teljes tartalmát úgy, hogy a mappaszerkezet megmaradjon.
3. Commitolj közvetlenül a `main` ágra.
4. A már összekapcsolt Cloudflare build automatikusan elindul.
5. A Cloudflare `Deployments` oldalán várd meg a `Ready` állapotot, majd frissítsd a honlapot.

A honlap nem igényel buildelést, Node.js-t vagy külső könyvtárat.

## Helyi ellenőrzés

A mappában futtasd:

```bash
python -m http.server 8080
```

Ezután nyisd meg:

```text
http://localhost:8080
```

## Fontos tudnivalók

- A hírlevél és a kapcsolatfelvételi űrlap szándékosan nincs bekapcsolva. Így az oldal nem tesz úgy, mintha adatot gyűjtene.
- A honlap jelenlegi változata nem használ saját sütiket, analitikát vagy külső betűkészletet.
- A `kiadoknak` oldal nyomtatható, illetve a böngészőből PDF-be menthető.
- A mobilmenü, a 404 oldal, a közösségimédia-előnézet, a favicon, a robots és a sitemap már része a csomagnak.
- Az eredeti könyvillusztrációk külön képfájlokban vannak, nem Base64-ként a HTML-be ágyazva.

## Saját domain beállítása után

A következő fájlokban cseréld le a jelenlegi `workers.dev` címet a saját domainre:

- `index.html`
- `kiadoknak/index.html`
- `adatkezeles/index.html`
- `robots.txt`
- `sitemap.xml`

Keresendő cím:

```text
https://amozgasszabadsaga.lymphater69.workers.dev
```

## Következő fejlesztési lépés

A második verzióban érdemes bekötni egy valódi hírlevél-szolgáltatást, hozzáadni a végleges kapcsolati e-mail-címet, majd ezekhez igazítani az adatkezelési tájékoztatót.
