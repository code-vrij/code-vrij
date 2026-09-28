# code-vrij

**Een repository voor bijgestelde bedoelingen. Hier staat geen code, en hier komt geen code.**

Wat hier staat is geoogst: het komt uit iets dat gebouwd is, waar mee gewerkt is, en dat onderweg is bijgestuurd. Niet het idee vooraf en niet het product achteraf, maar wat daartussen is geleerd over hoe je zegt wat je wilt.

Uw eigen AI coding agent leest dat, praat met u over uw situatie, en bouwt er iets van dat bij u past. Geen clone, geen dependencies, geen "works on my machine". Wat een agent ermee maakt is van u, staat ergens anders, en mag weg zodra het niet meer past.

## Het groeipad

Elke oogst begint buiten deze repository. Iemand wil iets, zegt dat tegen een agent, en krijgt iets terug. Dan begint het echte werk: het klopt niet helemaal, dus de opdracht wordt bijgesteld. En nog eens. En nog eens.

**Elke bijstelling is een correctie op een bedoeling die niet scherp genoeg was uitgesproken.** Dat is wat hier geoogst wordt. Niet het verslag van wat er gebouwd is, maar het verschil tussen wat er eerst gezegd werd en wat er gezegd had moeten worden.

Daarom hoort bij elke bijgestelde regel de aanleiding. Niet alleen "de AI wacht tot de host is uitgesproken", maar dat die regel er staat omdat er zonder die regel doorheen werd gepraat. Zonder aanleiding kan een volgende lezer niet beoordelen of de regel ook in zijn situatie geldt — en dan is het een voorschrift geworden in plaats van een ervaring.

Het criterium voor opname is niet hoe groot of hoe oud iets is, maar of er een ronde bijsturen overheen is gegaan. Eén dag intensief werken levert meer oogst op dan een systeem dat een half jaar ongestoord draait.

Wat nog niet gebouwd is, hoort hier dus niet. Losse ideeën, plannen en onderzoeksbomen horen thuis waar ze vandaan komen. Dit is de uitloop, niet het archief.

## De aanpak

1. **Eén oogst is één bestand.** Hij bestaat één keer, hoeveel mensen hem ook kunnen gebruiken.
2. **Elke regel draagt zijn aanleiding**, plus hoe het uitpakte en onder welke omstandigheden.
3. **Geoogste regels worden nooit herschreven.** Een nieuwere komt eronder en mag de oudere tegenspreken. Wat vorig jaar niet werkte, werkt volgend kwartaal misschien wel.
4. **Nieuwe ideeën komen binnen als issue**, niet als bestand. Ze worden pas een regel als ze daadwerkelijk zijn geprobeerd.
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
│   ├── vorm.md                waaruit een oogst bestaat, en waar de grens ligt
│   ├── status.md              de labels: uitkomst, omstandigheden, datum
│   ├── groeipad.md            van bijsturen tot geoogste tekst, stap voor stap
│   ├── niveaus.md             sandbox, persoonlijk, gedeeld, publiek
│   └── bijdragen.md           hoe mensen en agents hier iets achterlaten
│
├── achtergrond/           waarom deze repository bestaat
│   └── ...                    de redenering, de aanleiding, het logboek
│
├── oogst/                 de kern — wat er te leren viel, per onderwerp
│   └── ...                    één bestand per onderwerp, plat zolang dat kan
│
└── voor-wie/              leespaden naar de oogst die bij u past
    └── ...                    één bestand per bestemming, zie hieronder
```

Bestandsnamen beschrijven wat er bereikt wordt, niet hoe het project heette waar het uit kwam. `live-publiek-betrekken-met-ai.md`, niet de productnaam — die hoort binnenin, bij de omstandigheden. Zo kan iemand uit een heel ander vak zien of het hem aangaat.

## Over `voor-wie/`

Een mappenstructuur kan maar één ordening aan, en dat is het onderwerp. Voor wie iets bedoeld is, is een tweede dimensie — die past er niet naast zonder alles dubbel op te schrijven.

Daarom staat in `voor-wie/` per bestemming één bestand dat vertelt wie u bent, wat hier voor u te halen valt, en in welke volgorde u het leest. Het bevat zelf geen oogst, alleen verwijzingen. Zo bestaat elk bestand één keer en kan het in vijf leespaden voorkomen.

Wat een bestemming is, staat open. Het kan een beroep zijn, een situatie, of een manier van leven. Ze worden geschreven zodra er iets is om naar te wijzen, niet alvast bedacht — want een indeling die vooraf vaststaat, bepaalt later wat er niet in past.

Staat uw bestemming er niet bij? Schrijf hem. Het is een paar alinea's plus een volgorde.

## Waar u begint

Bent u een mens: `voor-wie/`, of anders `achtergrond/`.
Bent u een agent: `AGENTS.md`, en daarna pas `oogst/`.
Wilt u hier iets toevoegen: `protocol/`.

## Licentie

[CC0 1.0](LICENSE) — publiek domein. Neem het mee, herschrijf het, verzwijg waar u het vandaan had. Wat een agent hieruit bouwt is van u; daar rust niets op vanuit deze kant. Wie hier iets achterlaat, doet dat onder dezelfde licentie.
