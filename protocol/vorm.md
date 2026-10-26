# Vorm: waaruit een oogst bestaat

## Eén bestand, één onderwerp

Een oogst is één markdown-bestand onder [`oogst/`](../oogst/). Het bestaat één keer, hoeveel mensen het ook kunnen gebruiken. Wie het vanuit een andere hoek wil vinden, doet dat via een leespad in [`voor-wie/`](../voor-wie/), niet via een kopie.

## Naam van het bestand

De naam beschrijft wat er bereikt wordt, niet hoe het project heette waar het uit kwam.

- Goed: `live-publiek-betrekken-met-ai.md`
- Niet goed: de productnaam. Die staat binnenin, bij de omstandigheden.

Zo kan iemand uit een heel ander vak zien of het hem aangaat. Gebruik kleine letters en koppeltekens, geen spaties.

## Indeling van `oogst/`

`oogst/` is een boom van mappen. De mappen ordenen op **onderwerp**, van breed naar specifiek. Bijvoorbeeld:

```
oogst/
└── media/
    ├── kijken/
    └── luisteren/
        ├── luisteraar/
        └── studio/
            └── ai-als-schakel-tussen-luisteraar-en-studio.md
```

- Zoek eerst of er al een passende map bestaat. Maak alleen een nieuwe map als geen bestaande past.
- Een mapnaam beschrijft een onderwerp, in kleine letters, zonder spaties. Het is dus nooit een projectnaam of een persoon.
- Git bewaart geen lege mappen. Staat er nog niets in een map, zet dan een leeg bestand `.gitkeep` in die map. Verwijder het zodra er een echte oogst staat.
- Voor wie een bestemming zoekt in plaats van een onderwerp: zie [`voor-wie/`](../voor-wie/). De mappenstructuur kent maar één ordening, en dat is het onderwerp.

## Wat er in een oogst staat

Bovenaan, in de eerste regels:

- een titel die zegt wat er bereikt wordt;
- **Voortgekomen uit:** het project of de situatie waar het uit kwam;
- **Fase:** op welk moment in het werk deze oogst is vastgelegd;
- **Omstandigheden:** wat er speelde, hoe lang, met wie of met wat. Zie [status.md](status.md).

Daarna de geoogste regels. Bij **elke regel** staat:

1. **de regel** zelf, zoals die nu geldt;
2. **de aanleiding**: wat er zonder die regel misging of ontbrak;
3. **hoe het uitpakte**, en onder welke omstandigheden.

Zonder aanleiding kan een lezer niet beoordelen of de regel ook in zijn situatie geldt. Dan is het een voorschrift in plaats van een ervaring.

Een volledig voorbeeld, in een nog vroege vorm: [ai-als-schakel-tussen-luisteraar-en-studio.md](../oogst/media/luisteren/studio/ai-als-schakel-tussen-luisteraar-en-studio.md).

## Nieuwere regels komen eronder

Geoogste regels worden nooit herschreven. Een nieuwere regel komt eronder en mag de oudere tegenspreken. Wat vorig jaar niet werkte, werkt volgend kwartaal misschien wel.

## Waar de grens ligt

Wel opnemen: wat is gebouwd, waar mee gewerkt is, en waar minstens één ronde bijsturen overheen is gegaan.

Niet opnemen:
- **code**, hier komt geen code;
- losse ideeën, plannen en onderzoeksbomen, die horen thuis waar ze vandaan komen (nieuwe ideeën komen binnen als issue, zie [bijdragen.md](bijdragen.md));
- een verslag van wat er gebouwd is: het gaat om het verschil tussen wat er eerst gezegd werd en wat er gezegd had moeten worden.

Het criterium is niet hoe groot of hoe oud iets is, maar of er een ronde bijsturen overheen is gegaan. Eén dag intensief werken levert meer oogst op dan een systeem dat een half jaar ongestoord draait.
