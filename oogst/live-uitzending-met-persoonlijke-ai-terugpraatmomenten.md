# Live-uitzending in snippets, met persoonlijke AI-terugpraatmomenten

**Voortgekomen uit:** Terugpraatradio (VPRO MediaLab, ai.vpro.nl)
**Fase:** eerste bouwdag — briefing en ontwerpkeuzes, vlak vóór de eerste echte proef-uitzending
**Omstandigheden:** één ochtend besteed aan een natuurlijke-taal-briefing en het scherpstellen daarvan tot 24 losse ontwerpkeuzes; diezelfde dag geïmplementeerd en met een kleine testgroep (proefgedraaid).

Dit is een vroege, basale oogst: de aanvankelijke opzet in gewone taal, gevolgd door de vragen die zich tijdens het scherpstellen aandienden en het antwoord dat toen is gekozen — nog geen post-hoc correcties uit een echte uitzending met publiek. Een uitgebreidere oogst, met wat er ná verder gebruik deze week daadwerkelijk moest worden bijgesteld (en waarom), volgt separaat.

## De aanvankelijke briefing

> Op /terugpraatradio wil ik vandaag een test draaien met een nieuw soort podcast, namelijk een soort live podcast die gesynchroniseerd wordt uitgezonden naar meerdere participerende luisteraars. De podcast is echter niet 1 mp3, maar het is een constante stroom aan content snippets die richting de client (de luisteraar) gaan. elke snippet heeft een inhoud en een type label, zodat de client weet wat het stuk tekst betreft.
>
> In de simpelste vorm stuurt de server regel voor regel (op het juiste tijdstip) een stukje uit de uitzending, iets wat door een van de mensen in de uitzending werd gezegd. De client kan kiezen om dat als tekst te vertonen of uit te spreken. er gaat een mogelijkheid zijn dat zoiets ook als mp3 wordt meegestuurd, nadat het is uitgesproken door een elevenlabs stem.
>
> Het idee is dat er ook momenten zijn waarop luisteraars actief worden opgeroepen om terug te praten, vandaar dat het experiment 'terugpraatradio' heet. Ze kunnen kiezen om te typen of iets in te spreken dat dan wordt getranscribeerd.
>
> Op allerlei plekken in dit proces is een AI component actief. De AI agent in de studio weet wanneer er iets aan de luisteraars gevraagd moet worden (want dat staat in het vooraf opgestelde draaiboek, of het wordt live aangeklikt in een live AI regisseurs-control-panel). ook 1-op-1 voor elke luisteraar is een AI actief die op zo'n verzoek kan reageren door de luisteraar de vraag te stellen, en het antwoord terug te geven of daarover in dissussie te gaan. De uitzending loopt ondertussen door. er wordt niet gewacht op het antwoord van de gebruikers. de AI in de studio kan worden gevraagd om alle binnenkomende antwoorden even samen te vatten. de output kan een tekst op het scherm zijn, of de AI spreekt het al uit, rechstreeks in de uitzending. Op zo'n moment komt er dus een improvisatie regel bij in het draaiboek, die ook richting de luisteraars wordt verzonden.
>
> Het draaiboek bestaat uit letterlijk uitgesproken teksten die letterlijk moeten worden uitgesproken of verzonden. Maar het draaiboek staat ook vol met allerlei regie-aanwijzingen voor de betrokken AI bots, zodat die weten wat er in de studio gebeurt en wat er vanuit de studio inmiddels bij de luisteraar is terecht gekomen. Het draaiboek heeft een begin en een eind en een vaste duur. De samenwerkende AI's gaan zorgen dat alles in het draaiboek tijdens de uitzending aan bod komt. Dat betekent dat er soms even tempo gemaakt moet worden, ofwel in de studio ofwel in het 1-op-1 contact met de luisteraar. In feite is de uitzending voor de luisteraar heel persoonlijk. De AI agent voor de luisteraar let erop dat de luisteraar ook op tijd klaar is met de uitzending, en dat alles wat relevant is, aan bod is gekomen.
>
> Dit hierboven is het basis principe, maar er zijn nog veel keuzes te maken. Het lijkt me het handigst om die per functionele unit goed helder en compleet te specificeren. Ik wil deze ochtend werken aan een uitgebreide /terugpraatradio/claude.md briefing die ik later vandaag kan laten implementeren.
>
> Kun je beginnen met een eerste versie van claude.md en kunnen we daarna in deze chat praten over alle keuzes waarover je nog wilt overleggen zodat we de beslissing kunnen verwerken in de claude.md tekst?

## De vragen die dit aanscherpten

Bij het uitwerken van deze briefing tot een concrete implementatie-briefing moesten 24 losse ontwerpvragen worden beantwoord. Per vraag staat hier wat is gekozen, en welk alternatief daarmee terzijde is geschoven (waar dat alternatief niet expliciet is besproken, staat dat vermeld — dan is het een reconstructie achteraf, geen letterlijk overwogen optie).

**Q1 — Synchronisatie tussen luisteraars**
Gekozen: zachte synchronisatie — luisteraars zitten ongeveer gelijk op, maar de eigen luisteraar-AI mag een snippet een fractie uitstellen om een gesprek/zin af te maken; server houdt een eigen cursor per luisteraar bij.
Alternatief (niet expliciet besproken): harde synchronisatie met één globale cursor voor iedereen.

**Q2 — Tijdsdruk bij de luisteraar-AI**
Gekozen: ruime persoonlijke marge, met de luisteraar-AI als bewaker; bij oplopende achterstand maakt die zelf een inhaal-samenvatting van gemiste snippets.
Alternatief (niet expliciet besproken): strakke tijdslimiet zonder marge, of gemiste snippets alsnog stuk voor stuk laten inhalen.

**Q3 — Formaat van het draaiboek**
Gekozen: platte tekst/markdown, geparsed door de (studio-)AI — een lichte conventie (`SPREKER:`, `[regie: ...]`, `[vraag]`).
Alternatief (niet expliciet besproken): een strikt machineleesbaar formaat (bv. JSON) dat de redacteur zelf al gestructureerd zou moeten aanleveren.

**Q4 — Tempo-aansturing**
Gekozen: AI-gedreven tempo vanaf dag 1 — de studio-AI bepaalt per stap het echte verzendmoment, kan optionele items overslaan/activeren op basis van binnengekomen reacties.
Alternatief (expliciet afgewezen): een vaste scheduler die op vooraf bepaalde tijden de klok volgt.

**Q5 — Ad-hoc terugpraat-triggers**
Gekozen: ja, mogelijk — de mens-regisseur kan via het control panel ook los van het draaiboek een terugpraat-moment starten.
Alternatief (niet expliciet besproken): alleen wat vooraf in het draaiboek staat, geen live ad-hoc ingrijpen.

**Q6 — Editor-UI voor draaiboeken**
Gekozen: er is nu al een editor-scherm nodig om een draaiboek te schrijven/bewerken en op te slaan.
Alternatief (expliciet afgewezen): alleen één hardcoded testdraaiboek, geen editor-UI die dag.

**Q7 — Transportmechanisme naar de client**
Gekozen: polling — consistent met een bestaand prototype in dezelfde codebase, past beter bij serverless hosting (geen langlevende verbindingen nodig).
Alternatief (expliciet afgewezen): SSE/WebSocket.

**Q8 — Polling-interval**
Gekozen: strakker interval, ~1-2 seconden.
Alternatief (expliciet afgewezen): het 4s-interval van het bestaande eerdere prototype aanhouden.

**Q9 — Timing van tekst versus audio**
Gekozen: tekst direct verzenden zodra bekend; audio volgt later als patch op dezelfde snippet. Client valt in de tussentijd terug op browser-TTS.
Alternatief (niet expliciet besproken): wachten met versturen tot de audio ook klaar is.

**Q10 — Audio-modus per sessie**
Gekozen: per-sessie instelbaar (ElevenLabs of browser-TTS) — een kostenschakelaar voor als ElevenLabs met veel gelijktijdige luisteraars te duur wordt.
Alternatief (niet expliciet besproken): één vaste, systeembrede instelling zonder per-sessie keuze.

**Q11 — Wanneer audio genereren**
Gekozen: just-in-time, ook voor vooraf geschreven draaiboekregels.
Alternatief (expliciet afgewezen): bulk-pregeneratie van alle audio op het moment dat het draaiboek wordt opgeslagen.

**Q12 — Wie bepaalt of iets wordt uitgesproken**
Gekozen: de luisteraar kiest zelf, via een globale instelling in de client ("spreek voor" aan/uit).
Alternatief (expliciet afgewezen): gedrag vastleggen per snippet-type.

**Q13 — Spraakherkenning voor terugpraten**
Gekozen: browser Web Speech API voor deze eerste test.
Alternatief (bewaard voor later): een realtime-transcriptiedienst van een externe partij — gedeeltelijk al gebouwd elders in dezelfde codebase, mogelijke latere upgrade.

**Q14 — Route van een luisteraarsantwoord**
Gekozen: altijd via de luisteraar-AI — elk antwoord gaat eerst door het 1-op-1-gesprek.
Alternatief (expliciet afgewezen): een directe shortcut waarbij de luisteraar iets rechtstreeks (ongefilterd) in de studio-queue kan zetten.

**Q15 — Harde bovengrens op een terugpraat-moment**
Gekozen: naast de AI-beoordeling (Q2) ook een expliciete harde bovengrens (max. aantal beurten en/of max. seconden) als vangnet.
Alternatief (niet expliciet besproken): alleen vertrouwen op het eigen oordeel van de luisteraar-AI.

**Q16 — Hoe het draaiboek "tikt"**
Gekozen: periodieke automatische tick, extern getriggerd.
Alternatief (expliciet afgewezen): een puur handmatige "volgende beurt"-knop als enige mechanisme.

**Q17 — Autonomie van de studio-AI**
Gekozen: grotendeels autonoom, mens-regisseur kan altijd overrulen/ingrijpen via ad-hoc triggers.
Alternatief (expliciet uitgesteld): volledig autonome AI-regie zonder mens in de loop.

**Q18 — Omvang van het control panel**
Gekozen: een minimaal panel is nu al nodig — sessie starten/stoppen, voortgang zien, ad-hoc terugpraat-moment triggeren.
Alternatief (niet expliciet besproken): de volledige, uitgebreide regie-UI — expliciet doorgeschoven naar later.

**Q19 — Context voor de luisteraar-AI**
Gekozen: compacte, doorlopend bijgewerkte voortgangs-samenvatting, gecombineerd met de eigen gespreksgeschiedenis van díe luisteraar.
Alternatief (expliciet afgewezen): elke beurt het hele draaiboek plus de volledige geschiedenis meesturen.

**Q20 — Afronden van een 1-op-1-gesprek**
Gekozen: de luisteraar-AI kapt het gesprek netjes af zodra de tijd dringt ("we moeten door, dank je voor je antwoord").
Alternatief (expliciet afgewezen): het gesprek onafgemaakt laten liggen.

**Q21 — Admin-authenticatie**
Gekozen: een nieuw, eigen wachtwoord voor dit project, los van de rest van de bestaande site.
Alternatief (expliciet afgewezen): hergebruik van een bestaand wachtwoord — gedeelde login met een ander, ouder onderdeel.

**Q22 — (geen keuzevraag, waarschuwing)**
Bucket-backed opslag zoals de rest van de codebase: bij elke test-write eerst ophalen wat er al staat, nooit blind een leeg/test-resultaat terugzetten als "opruimen" — gebaseerd op een eerdere incident-notitie elders in dezelfde codebase.

**Q23 — Reikwijdte van de eerste testrun**
Gekozen: de volledige stack in één keer testen — snippet-stroom+timing, terugpraten (typen én spreken), audio, en het minimale control panel, alles tegelijk.
Alternatief (expliciet afgewezen): een gefaseerde aanpak, eerst tekst-only, de rest later toevoegen.

**Q24 — Schaal van de eerste test**
Gekozen: klein aantal testluisteraars — één tester in meerdere tabs en/of een handvol collega's.
Alternatief (expliciet uitgesteld): schaal naar honderden gelijktijdige luisteraars.
