# code-vrij

**Een repository voor intenties. Hier staat geen code, en hier komt geen code.**

Wat hier staat beschrijft wat iemand wilde: het doel, de omstandigheden, de keuzes onderweg, en wat er wel en niet bleek te werken. Uw eigen AI coding agent leest dat, praat met u over uw situatie, en bouwt er iets van dat bij u past. Geen clone, geen dependencies, geen "works on my machine".

Wat een agent ermee maakt is van u, staat ergens anders, en mag weg zodra het niet meer past.

## Het groeipad

Een intentie is hier niet af zodra hij opgeschreven is. Hij doorloopt een weg, en die weg is de reden dat deze repository iets waard is.

Het begint met een **voornemen**: dit willen we, er is nog niets over bekend. Daarna wordt het ergens gebouwd — buiten deze repository, door een agent, voor één situatie. Als dat systeem af is en er mee gewerkt is, komt de intentie terug. Niet de code, maar wat er van de bedoeling overbleef nadat de werkelijkheid eroverheen is gegaan. Dat heet hier een **geoogste** intentie, en die krijgt een label dat zegt hoe het uitpakte, met de omstandigheden en de datum erbij.

Een geoogste intentie is dus meer waard dan het voornemen waar hij uit voortkwam. Het verschil tussen die twee is precies waar iemand anders iets aan heeft.

Hoop en bewijs mogen naast elkaar staan, zolang elke regel zijn eigen herkomst draagt. De labels staan in `protocol/status.md`.

## De aanpak

1. **Eén intentie is één bestand.** Hij bestaat één keer, hoeveel mensen hem ook kunnen gebruiken.
2. **Elke regel draagt zijn herkomst**, en als hij geoogst is ook zijn uitkomst.
3. **Geoogste regels worden nooit herschreven.** Een nieuwere komt eronder en mag de oudere tegenspreken. Wat vorig jaar niet werkte, werkt volgend kwartaal misschien wel.
4. **Nieuwe ideeën komen binnen als issue**, niet als bestand. Ze worden pas een regel als ze een intentie aanscherpen of iets rapporteren dat daadwerkelijk gebouwd is.
5. **Lees `protocol/` voordat u iets toevoegt.** Zonder die vorm wordt dit een vergaarbak van proza.

## Wat waar staat

```
code-vrij/
│
├── README.md              deze kaart
├── AGENTS.md              korte instructie voor AI coding agents, wijst door naar protocol/
├── LICENSE                CC0 1.0 — publiek domein
│
├── protocol/              hoe deze repository werkt — lezen vóór u iets toevoegt
│   ├── vorm.md                waaruit een intentie bestaat, en waar de grens ligt
│   ├── status.md              de labels: herkomst, en uitkomst na het oogsten
│   ├── groeipad.md            van voornemen tot geoogste intentie, stap voor stap
│   ├── niveaus.md             sandbox, persoonlijk, gedeeld, publiek
│   └── bijdragen.md           hoe mensen en agents hier iets achterlaten
│
├── achtergrond/           waarom deze repository bestaat
│   └── ...                    de redenering, de aanleiding, het logboek
│
├── intenties/             de kern — wat we wilden, per onderwerp
│   └── ...                    één bestand per onderwerp, plat zolang dat kan
│
└── voor-wie/              leespaden naar de intenties die bij u passen
    └── ...                    één bestand per bestemming, zie hieronder
```

## Over `voor-wie/`

Een mappenstructuur kan maar één ordening aan, en dat is het onderwerp. Voor wie iets bedoeld is, is een tweede dimensie — die past er niet naast zonder alles dubbel op te schrijven.

Daarom staat in `voor-wie/` per bestemming één bestand dat vertelt wie u bent, wat hier voor u te halen valt, en in welke volgorde u het leest. Het bevat zelf geen intenties, alleen verwijzingen. Zo bestaat elke intentie één keer en kan hij in vijf leespaden voorkomen.

Wat een bestemming is, staat open. Het kan een beroep zijn, een situatie, of een manier van leven. Ze worden geschreven zodra er iets is om naar te wijzen, niet alvast bedacht — want een indeling die vooraf vaststaat, bepaalt later wat er niet in past.

Staat uw bestemming er niet bij? Schrijf hem. Het is een paar alinea's plus een volgorde.

## Waar u begint

Bent u een mens: `voor-wie/`, of anders `achtergrond/`.
Bent u een agent: `AGENTS.md`, en daarna pas `intenties/`.
Wilt u hier iets toevoegen: `protocol/`.

## Licentie

[CC0 1.0](LICENSE) — publiek domein. Neem het mee, herschrijf het, verzwijg waar u het vandaan had. Wat een agent hieruit bouwt is van u; daar rust niets op vanuit deze kant. Wie hier iets achterlaat, doet dat onder dezelfde licentie.
