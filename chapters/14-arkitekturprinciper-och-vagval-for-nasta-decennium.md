# Kapitel 14: Arkitekturprinciper och vägval för nästa decennium

## Varför detta kapitel finns

AI kommer inte att vara ett separat teknikspår vid sidan av övrig digitalisering. Den kommer gradvis att vävas in i verksamhetsprocesser, informationsflöden, användargränssnitt, utvecklingsverktyg, beslutsstöd, integrationsmönster och förvaltningsmodeller. För offentlig sektor innebär det att AI behöver förstås som en del av den digitala infrastrukturen, inte som en serie isolerade innovationsexperiment.

Det här avslutande kapitlet samlar bokens viktigaste resonemang till ett antal arkitekturprinciper och strategiska vägval. Syftet är inte att formulera en färdig standard som passar alla organisationer. Syftet är att ge IT-arkitekter ett beslutsstöd för den kommande perioden, där AI-förmågor behöver införas med både handlingskraft och återhållsamhet.

I tidigare kapitel har vi behandlat arkitektens förändrade uppdrag, förmågedesign, AI-stött arkitekturarbete, governance, risk, offentlig sektors särskilda villkor, dataarkitektur, integration, plattformar, säkerhet, livscykel, målarkitektur och kompetens. Nu behöver dessa delar hållas ihop.

Den centrala frågan är: vilka principer bör styra offentlig sektors AI-arkitektur när tekniken förändras snabbare än organisationernas styrning, upphandling, kompetens och förvaltning?

## Lärandemål

Efter kapitlet ska läsaren kunna:

- formulera långsiktiga arkitekturprinciper för AI i offentlig sektor
- skilja mellan principer som bör vara stabila och teknikval som bör vara utbytbara
- resonera om centrala vägval kring centralisering, suveränitet, plattformar, data, ansvar och innovationstakt
- identifiera anti-patterns som riskerar att skapa svag AI-arkitektur över tid
- använda bokens samlade begrepp för att skapa en strategisk riktning för AI-arkitektur

## Innan vi börjar

Det här kapitlet bygger på hela bokens canon. Särskilt viktiga begrepp är:

- **AI-förmåga**: AI som kombination av data, teknik, ansvar, processer, kontroller, kompetens och uppföljning.
- **Capability architecture**: fokus på verksamhetsförmågor snarare än enskilda system.
- **AI governance**: styrning av hur AI väljs, byggs, införs, används, följs upp och avvecklas.
- **Data lineage** och **metadata**: spårbarhet och beskrivning av data som används i AI-sammanhang.
- **Reference architecture**: återanvändbar målbild för komponenter, relationer och principer.
- **AI operating model**: hur organisationen praktiskt driver och förvaltar AI över tid.
- **Digital suveränitet**: förmågan att behålla kontroll över kritisk digital infrastruktur, data, regler och beroenden.

Kapitlet introducerar tre avslutande begrepp: **adaptive architecture**, **resilient governance** och **public value**. De används för att sammanfatta vilken typ av arkitekturförmåga offentlig sektor behöver utveckla.

## Huvudförklaring

### Arkitekturprinciper behövs när detaljerna förändras

AI-området förändras snabbt. Modeller, verktyg, plattformar, regler, kostnadsmodeller och säkerhetsmönster kommer att fortsätta förändras. Det gör det riskabelt att bygga arkitekturstrategi på detaljer som är starkt knutna till en viss leverantör, modellgeneration eller teknisk trend.

Samtidigt går det inte att vänta tills allt stabiliseras. Offentlig sektor behöver kunna använda AI där det stärker samhällsnytta, effektivitet, tillgänglighet och kvalitet. Arkitektens uppgift blir därför att skapa stabilitet på rätt nivå.

En bra arkitekturprincip är inte en detaljerad lösningsbeskrivning. Den är en norm som hjälper organisationen att fatta konsekventa beslut även när tekniken förändras. Principen ska vara tillräckligt konkret för att vägleda, men tillräckligt stabil för att överleva flera teknikskiften.

Exempel:

- Svag princip: “Vi ska använda en viss AI-plattform för alla AI-lösningar.”
- Starkare princip: “AI-förmågor som påverkar myndighetsutövning ska kunna granskas, följas upp och avvecklas utan att organisationen förlorar kontroll över data, beslutspåverkan eller ansvarskedja.”

Den första principen är egentligen ett teknikval. Den andra anger en styrande kvalitet som kan tillämpas oavsett teknik.

### Adaptive architecture: arkitektur som kan förändras utan att tappa kontroll

AI gör förändringstakten högre, men offentlig sektor kan inte bygga på permanent improvisation. Organisationer behöver arkitektur som kan anpassas utan att varje förändring blir ett nytt specialfall.

**Adaptive architecture** innebär att arkitekturen utformas för förändring. Det handlar inte om att allt ska vara flexibelt. Det handlar om att veta vilka delar som behöver vara stabila och vilka delar som bör kunna bytas, utvecklas eller avvecklas.

Stabila delar kan vara:

- ansvarsfördelning
- informationsklassning
- loggning och spårbarhet
- krav på mänsklig kontroll
- principer för dataminimering
- krav på dokumentation och uppföljning
- arkitekturforum och beslutsprocesser

Utbytbara delar kan vara:

- enskilda modeller
- specifika AI-tjänster
- promptmallar
- utvärderingsmetoder
- användargränssnitt
- integrationsadaptrar
- leverantörsspecifika komponenter

För arkitekten innebär detta att målarkitekturen inte bör beskriva AI som en fast uppsättning produkter, utan som ett ekosystem av kontrollerade förmågor. En AI-tjänst ska kunna bytas utan att hela ansvarskedjan, säkerhetsmodellen eller informationsstyrningen faller sönder.

### Resilient governance: styrning som tål osäkerhet

Traditionell governance kan bli för långsam om varje AI-fråga måste behandlas som ett helt nytt undantag. Samtidigt kan för svag governance leda till skugg-AI, otydliga beslut, svag informationskontroll och lösningar som inte går att förvalta.

**Resilient governance** innebär styrning som är robust nog att hantera risk, men smidig nog att stödja lärande. Den bygger på tydliga principer, risknivåer, beslutsmandat och uppföljning snarare än på detaljkontroll av varje teknisk parameter.

För offentlig sektor är detta särskilt viktigt eftersom AI kan påverka rättssäkerhet, insyn, likabehandling och förtroende. Styrning behöver därför vara mer än intern effektivitet. Den behöver kunna visa varför en AI-förmåga används, vilka begränsningar den har, hur risker hanteras och vem som ansvarar för beslut.

Resilient governance kräver också att organisationen accepterar att AI-förmågor förändras över tid. En AI-lösning som var lämplig vid införandet kan bli olämplig när verksamheten, regelverket, datakvaliteten, hotbilden eller leverantörens villkor förändras. Governance måste därför omfatta hela livscykeln: idé, prioritering, utveckling, anskaffning, införande, användning, uppföljning, förbättring och avveckling.

### Public value: AI ska skapa offentligt värde, inte bara teknisk nyhet

I privat sektor mäts AI-satsningar ofta i effektivitet, intäkt, kundupplevelse eller konkurrensfördel. Offentlig sektor behöver också tänka på effektivitet, men måttet är bredare. AI måste ytterst kunna motiveras genom **public value**: värde för medborgare, samhälle, demokratiska institutioner och offentlig verksamhet.

Public value kan handla om:

- mer tillgänglig service
- snabbare handläggning
- bättre beslutsunderlag
- högre kvalitet i tillsyn
- bättre resursanvändning
- minskad administrativ börda
- mer proaktiv service
- förbättrad krisberedskap
- bättre upptäckt av fel, risker eller avvikelser

Men public value kräver också att värdet skapas på ett legitimt sätt. En lösning som är tekniskt imponerande men svår att förklara, svår att granska eller svår att ansvarsätta kan skada tilliten även om den ger kortsiktiga effektivitetsvinster.

Arkitektens uppgift är därför att koppla AI-vägval till både nytta och legitimitet. Frågan är inte bara “fungerar lösningen?”, utan också “är detta ett rimligt, transparent, förvaltningsbart och rättssäkert sätt att skapa offentlig nytta?”

### Princip 1: Utgå från förmåga före teknik

AI bör inte införas för att organisationen har tillgång till en modell eller plattform. AI bör införas när den stärker en prioriterad verksamhetsförmåga och när organisationen kan hantera de konsekvenser som följer.

Det innebär att arkitekturarbetet bör börja med frågor som:

- Vilken verksamhetsförmåga ska stärkas?
- Vilket beslut, flöde eller resultat ska förbättras?
- Vilken data krävs?
- Vilka risker uppstår?
- Vem ansvarar för användning och uppföljning?
- Hur vet vi att AI-förmågan skapar nytta?

Teknikvalet kommer senare. Denna princip skyddar organisationen från att låta leverantörsdemonstrationer, pilottryck eller intern nyfikenhet bli den egentliga strategin.

### Princip 2: Gör ansvarskedjan synlig

AI-förmågor skapar ofta oklarhet kring ansvar. Det kan vara svårt att se vem som ansvarar för data, modell, promptar, användning, beslutspåverkan, fel, uppföljning och avveckling. I offentlig sektor är detta inte en administrativ detalj, utan en grundläggande arkitekturfråga.

En AI-förmåga bör inte betraktas som arkitekturellt mogen förrän ansvarskedjan är synlig. Det betyder att organisationen behöver kunna beskriva:

- vem som äger syftet
- vem som ansvarar för data
- vem som ansvarar för modell eller tjänst
- vem som ansvarar för integration och drift
- vem som ansvarar för säkerhet och åtkomst
- vem som ansvarar för användarstöd och utbildning
- vem som följer upp kvalitet, risk och effekt
- vem som kan besluta om ändring eller avveckling

När ansvarskedjan saknas blir AI lätt ett tekniskt objekt utan organisatorisk hemvist. Då ökar risken för att lösningen används på sätt som ingen fullt ut har tagit ansvar för.

### Princip 3: Separera policy, plattform och användningsfall

Ett återkommande problem i AI-arkitektur är att policy, plattform och användningsfall blandas ihop. Organisationen skaffar en plattform och låter den bli både teknisk lösning, styrmodell och prioriteringsmekanism. Eller så drivs varje användningsfall som ett isolerat projekt, utan gemensam policy eller återanvändbar plattform.

En mer hållbar arkitektur skiljer mellan tre nivåer:

- **Policy layer**: principer, risknivåer, ansvar, informationsklassning, godkännande och uppföljning.
- **Platform layer**: gemensamma tekniska tjänster, integration, loggning, identitet, övervakning och modellåtkomst.
- **Use case layer**: konkreta verksamhetsnära tillämpningar.

Separationen gör det möjligt att styra gemensamt utan att kväva lokal innovation. Den gör också att plattformen inte behöver bära hela governance-ansvaret och att enskilda användningsfall inte behöver uppfinna all grundläggande kontroll själva.

### Princip 4: Bygg för spårbarhet och revision från början

AI-lösningar som införs utan spårbarhet blir svåra att granska i efterhand. Det gäller särskilt generativ AI, beslutsstöd och AI-tjänster som sammanfattar, klassificerar eller prioriterar information.

Spårbarhet behöver därför vara en arkitekturprincip, inte en efterhandsfunktion. Organisationen behöver veta vilken data som använts, vilken modell eller tjänst som varit aktiv, vilka versioner som gällt, vilka instruktioner som styrt beteendet, vilka användare som haft åtkomst och hur resultat har använts.

Det innebär inte att allt alltid måste sparas i detalj. Informationssäkerhet, integritet och dataminimering kan begränsa vad som bör loggas. Men arkitekturen måste medvetet balansera spårbarhet, sekretess, integritet och operativ nytta.

### Princip 5: Behandla modeller som utbytbara komponenter

En vanlig felsatsning är att låta en specifik modell bli arkitekturens centrum. Det kan skapa snabb framdrift i början, men riskerar att ge svag förvaltningsbarhet över tid.

Modeller förändras. Kostnader förändras. Licensvillkor förändras. Prestanda förändras. Säkerhetsbedömningar förändras. Regler kan förändras. Nya modeller kan bli bättre för vissa användningsfall och sämre för andra.

Arkitekturen bör därför utformas så att modeller i rimlig grad kan bytas, jämföras, utvärderas och avvecklas. Det kräver tydliga gränssnitt, dokumenterade beroenden, test- och utvärderingsrutiner, loggning och en sourcingstrategi som inte låser organisationen mer än nödvändigt.

Det betyder inte att alla modeller alltid måste vara enkelt utbytbara. I vissa fall kan ett starkt beroende vara acceptabelt. Men beroendet ska vara ett medvetet arkitekturbeslut, inte en oavsiktlig konsekvens av första pilotprojektet.

### Princip 6: Centralisera det som skapar kontroll, decentralisera det som skapar verksamhetsnytta

AI i offentlig sektor kräver balans mellan central styrning och verksamhetsnära utveckling. För mycket centralisering kan skapa flaskhalsar, låg relevans och långsam innovation. För mycket decentralisering kan skapa fragmentering, varierande risknivå, svag kontroll och upprepade investeringar.

En användbar princip är att centralisera det som skapar kontroll och återanvändning, men decentralisera det som kräver verksamhetskunskap.

Centraliseras ofta bäst:

- gemensamma AI-principer
- riskklassning och beslutsmodeller
- informationssäkerhetskrav
- identitet och åtkomstmönster
- loggning och övervakning
- plattformstjänster
- upphandlingsstöd
- referensarkitektur
- mönster och anti-patterns

Decentraliseras ofta bäst:

- behovsanalys
- verksamhetsnära användningsfall
- förändringsledning
- användarutbildning
- effektuppföljning nära processen
- lokala förbättringsförslag

Arkitektens roll blir att skapa gränssnittet mellan dessa nivåer.

### Princip 7: Utforma AI för mänskligt omdöme, inte bara automation

AI kan automatisera, men allt som kan automatiseras bör inte automatiseras. I offentlig sektor behöver arkitekturen ofta stödja mänskligt omdöme, särskilt där beslut påverkar individer, rättigheter, skyldigheter eller tillit.

Det innebär att användargränssnitt, arbetsflöden, loggning och ansvar behöver utformas så att AI inte osynligt tar över beslut. Om AI används som beslutsstöd behöver det vara tydligt vad som är AI-genererat, hur underlaget ska tolkas, vilka begränsningar som finns och när användaren bör avstå från att följa rekommendationen.

En arkitektur som säger “human in the loop” men inte ger människan tid, kompetens, information eller mandat att faktiskt utöva kontroll har inte löst ansvarsfrågan. Den har bara flyttat den.

### Princip 8: Gör avveckling till en del av arkitekturen

AI-satsningar diskuteras ofta utifrån införande. Men offentlig sektor behöver också kunna avveckla AI-förmågor. En AI-tjänst kan bli olämplig, onödig, för dyr, för riskfylld eller ersatt av bättre mönster.

Avveckling kräver att organisationen vet:

- vilka processer som använder AI-förmågan
- vilka dataflöden och integrationer som påverkas
- vilka användare som berörs
- vilka beslut eller underlag som historiskt har påverkats
- vilka loggar och dokumentation som behöver bevaras
- hur verksamheten fungerar utan AI-förmågan
- vilka leverantörsavtal eller licenser som behöver avslutas

En AI-förmåga utan avvecklingsbarhet riskerar att bli teknisk skuld, även om den var värdefull vid införandet.

## Strategiska vägval och arkitektöverväganden

### Vägval 1: Ska AI vara central plattformsförmåga eller distribuerad verksamhetsförmåga?

Det första vägvalet gäller styrmodell och arkitekturell tyngdpunkt.

En central plattformsstrategi ger bättre kontroll, återanvändning, säkerhet och upphandling. Den kan också göra det lättare att bygga gemensam loggning, modellåtkomst, integrationsmönster och governance.

En distribuerad strategi ger närhet till verksamhetsproblem, snabbare lärande och bättre anpassning till lokala behov. Den kan samtidigt öka risken för fragmentering, skugg-AI och varierande kvalitet.

Offentlig sektor behöver ofta en hybrid: centrala principer och plattformsmönster, men verksamhetsnära utveckling av användningsfall.

Arkitekten bör fråga:

- Vilka kontroller måste vara gemensamma?
- Vilka beslut bör fattas nära verksamheten?
- Hur förhindrar vi både flaskhalsar och fragmentering?
- Hur återförs lokala lärdomar till gemensam arkitektur?

### Vägval 2: Hur mycket leverantörsberoende är acceptabelt?

AI-marknaden drivs starkt av plattformar och ekosystem. Det är sällan realistiskt att undvika leverantörsberoenden helt. Frågan är snarare vilka beroenden som är acceptabla och hur de ska hanteras.

Ett beroende kan vara rimligt om det ger säkerhet, kvalitet, driftstabilitet, snabb utveckling eller kostnadseffektivitet som organisationen inte kan skapa själv. Men beroendet blir problematiskt om det gör det svårt att förstå, granska, flytta, avveckla eller konkurrensutsätta lösningen.

Arkitekten bör fråga:

- Vilken data exponeras för leverantören?
- Kan lösningen granskas tillräckligt?
- Finns exit-strategi?
- Går det att byta modell eller tjänst?
- Vilka avtalsvillkor påverkar arkitekturen?
- Hur förändras risken om tjänsten blir verksamhetskritisk?

### Vägval 3: Ska organisationen prioritera innovationstakt eller riskkontroll?

Detta vägval är ofta falskt formulerat. Organisationer behöver både innovation och kontroll. Men i praktiken måste arkitekten hjälpa till att utforma olika styrspår för olika risknivåer.

Lågrisk-användning kan tillåta snabbare experiment, särskilt om den inte omfattar känsliga uppgifter, myndighetsutövning eller beslutspåverkan. Högre risk kräver tydligare granskning, dokumentation, testning och ansvar.

Arkitekten bör undvika en modell där allt behandlas som högrisk. Då flyttar experimenten utanför styrningen. Arkitekten bör också undvika en modell där allt behandlas som innovation. Då kommer riskerna ikapp när lösningarna börjar användas i skarpa processer.

### Vägval 4: Ska AI-strategin drivas av data, process eller användarupplevelse?

AI kan starta från flera håll. Ibland utgår organisationen från tillgängliga datamängder. Ibland från ineffektiva processer. Ibland från användarbehov. Alla perspektiv kan vara legitima, men de ger olika arkitekturkonsekvenser.

En datadriven start kan leda till stark dataförvaltning men riskerar att skapa lösningar utan tydlig verksamhetsnytta. En processdriven start kan ge tydlig effektivisering men riskerar att cementera gamla arbetssätt. En användarupplevelsedriven start kan skapa synlig nytta men riskerar att underskatta bakomliggande informations- och ansvarskrav.

Arkitekten bör hjälpa organisationen att koppla ihop perspektiven. AI-förmågan bör kunna motiveras genom dataförutsättningar, processförändring och användarvärde.

### Vägval 5: Ska arkitekturen optimera för nuvarande teknik eller framtida utbytbarhet?

För hög utbytbarhet kan bli dyrt och komplext. För låg utbytbarhet kan skapa inlåsning och teknisk skuld. Arkitektens uppgift är att välja var flexibilitet är värd kostnaden.

Utbytbarhet är särskilt viktig där:

- tekniken förändras snabbt
- leverantörsberoendet är stort
- lösningen blir verksamhetskritisk
- informationsklassningen är känslig
- regelverket kan påverka användningen
- flera modeller behöver jämföras över tid

Där användningsfallet är avgränsat, risken låg och livslängden kort kan enklare arkitektur vara rimlig. Strategisk arkitektur betyder inte maximal abstraktion överallt. Det betyder medveten abstraktion där den behövs.

## Vanliga felsatsningar

### Att skriva AI-principer som egentligen är teknikval

Organisationer kan snabbt låsa sig genom att formulera principer kring dagens verktyg. Det gör strategin skör. Principer bör uttrycka önskade arkitekturella egenskaper, inte bara val av produkt eller plattform.

### Att behandla AI som ett innovationsspår utan förvaltning

AI-piloter kan skapa lärande, men om de inte kopplas till ansvar, dataförvaltning, säkerhet, drift och uppföljning blir de inte hållbara AI-förmågor.

### Att centralisera allt av rädsla

Rädsla för risk kan leda till att all AI-användning måste passera samma centrala process. Det kan skapa kontroll på papperet men driva användningen utanför den officiella arkitekturen.

### Att decentralisera allt av hastighetsskäl

Snabb lokal utveckling kan vara värdefull, men utan gemensamma principer uppstår snabbt duplicering, svag spårbarhet, leverantörsspridning och okontrollerade datarisker.

### Att underskatta avveckling

Många AI-lösningar planeras för införande men inte för avslut. Det gör organisationen sårbar när kostnader, risker, leverantörsvillkor eller verksamhetsbehov förändras.

### Att mäta framgång för snävt

AI-satsningar som bara mäts i tidsbesparing eller antal användare kan missa rättssäkerhet, kvalitet, tillit, arbetsmiljö, kostnadsutveckling och långsiktig förvaltningsbarhet.

## Arkitektens checklista

### Strategisk riktning

- Finns tydliga arkitekturprinciper för AI?
- Skiljer principerna mellan stabila styrnormer och föränderliga teknikval?
- Är AI-strategin kopplad till verksamhetsförmågor och offentlig nytta?
- Finns en tydlig koppling mellan målarkitektur, governance och portföljstyrning?

### Ansvar och styrning

- Är ansvarskedjan definierad för varje viktig AI-förmåga?
- Finns risknivåer som avgör vilken styrning som krävs?
- Finns forum där AI-relaterade arkitekturbeslut kan granskas?
- Finns uppföljning efter införande, inte bara godkännande före införande?

### Data och spårbarhet

- Är dataägarskap, metadata och data lineage tillräckligt tydliga?
- Finns loggning och revisionsbarhet där det behövs?
- Är balansen mellan spårbarhet, integritet och sekretess medvetet hanterad?
- Finns krav på dokumentation av modell, tjänst, version och användningskontext?

### Plattform och leverantörer

- Är plattformen ett stöd för governance eller har den blivit governance i sig?
- Finns strategi för leverantörsberoenden och exit?
- Kan modeller eller tjänster bytas där det är viktigt?
- Är avtalskrav kopplade till arkitekturkrav?

### Förvaltning och förändring

- Finns en AI operating model för drift, uppföljning, förbättring och avveckling?
- Finns kompetens för både central styrning och verksamhetsnära användning?
- Återförs lärdomar från AI-initiativ till referensarkitektur och mönsterbibliotek?
- Finns kriterier för när AI-förmågor ska stoppas, ändras eller avvecklas?

### Offentlig legitimitet

- Kan organisationen förklara varför AI används i ett visst sammanhang?
- Är mänskligt ansvar tydligt där AI påverkar beslut?
- Finns hänsyn till rättssäkerhet, transparens, likabehandling och tillit?
- Skapar lösningen public value på ett sätt som går att motivera?

## Snabb sammanfattning

- AI kräver arkitekturprinciper som är stabila nog att överleva teknikskiften.
- Offentlig sektor bör se AI som långsiktig digital infrastruktur, inte en serie isolerade piloter.
- Adaptive architecture innebär att stabila styrande delar kombineras med utbytbara tekniska komponenter.
- Resilient governance innebär styrning som både hanterar risk och möjliggör lärande.
- Public value innebär att AI ska skapa legitim samhällsnytta, inte bara teknisk effektivitet.
- Centrala vägval gäller centralisering, leverantörsberoenden, innovationstakt, data, plattform och utbytbarhet.
- Arkitektens uppgift är att skapa riktning, ansvar, spårbarhet och förvaltningsbarhet när tekniken förändras.
- Den viktigaste frågan är inte vilken AI-lösning organisationen väljer först, utan vilken arkitekturförmåga den bygger för nästa decennium.

## Reflektionsfrågor

1. Vilka AI-principer i er organisation är verkliga arkitekturprinciper och vilka är egentligen teknikval?
2. Var behöver er AI-arkitektur vara stabil, och var behöver den vara utbytbar?
3. Vilka AI-förmågor riskerar att sakna tydlig ansvarskedja?
4. Vilka delar av AI-governance bör centraliseras och vilka bör ligga nära verksamheten?
5. Hur hanterar ni leverantörsberoenden som kan bli verksamhetskritiska?
6. Vilka AI-lösningar skulle vara svåra att avveckla om förutsättningarna förändrades?
7. Hur definierar ni public value för AI-satsningar i er organisation?
8. Vad behöver förändras i er målarkitektur för att stödja AI under nästa decennium?

## Nästa steg

Boken har nu följt en progression från arkitektens förändrade uppdrag till strategiska principer för nästa decennium. Nästa steg i bokprojektet är inte att lägga till fler begrepp, utan att granska helheten: terminologi, progression, överlapp, kapitelbalans, referenser, exempel och publiceringsformat.

Vid en slutgranskning bör särskild uppmärksamhet läggas på fyra frågor:

- Är begrepp introducerade i rätt ordning?
- Är offentlig sektors villkor tydliga genom hela boken?
- Finns en konsekvent balans mellan strategi, teknik, styrning och ansvar?
- Behöver aktuella regler, standarder och tekniska rekommendationer verifieras mot officiella källor före publicering?

När dessa frågor är hanterade kan boken vidareutvecklas från kapitelutkast till en sammanhållen första utgåva.
