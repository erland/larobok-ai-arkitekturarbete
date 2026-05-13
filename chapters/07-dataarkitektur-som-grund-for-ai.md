# Kapitel 7: Dataarkitektur som grund för AI

## Varför detta kapitel finns

AI-förmågor byggs inte ovanpå modellvalet i första hand. De byggs ovanpå data, informationsstyrning, åtkomst, metadata, kvalitet, spårbarhet och förmågan att förstå vad data faktiskt betyder i verksamheten. För offentlig sektor blir detta särskilt viktigt eftersom data ofta är känslig, reglerad, spridd över många system och bunden till långa förvaltningscykler.

Många organisationer börjar sin AI-resa med frågan: ”Vilken modell ska vi använda?” En mer arkitekturellt hållbar fråga är: ”Vilka dataförutsättningar behöver vi för att AI ska kunna användas säkert, rättssäkert och meningsfullt?” Svaret handlar sällan bara om datalager eller integrationsplattformar. Det handlar om ansvar, begrepp, informationsmodeller, klassning, kontext, livscykel och styrning.

I tidigare kapitel har vi beskrivit hur AI förändrar arkitektens uppdrag, hur fokus flyttas från systemdesign till förmågedesign, hur AI kan bli en medskapare i arkitekturarbetet och varför styrning, risk och tillit är centrala i offentlig sektor. Detta kapitel går in i den del av arkitekturen som ofta avgör om AI blir användbar eller riskabel: dataarkitekturen.

En IT-arkitekt som arbetar strategiskt med AI behöver därför kunna se dataarkitektur som mer än teknik. Dataarkitektur är en förutsättning för ansvarstagande AI. Den avgör vilka AI-förmågor som är möjliga, vilka som bör undvikas, vilka som kräver särskild styrning och vilka som riskerar att skapa felaktiga beslut, bristande tillit eller oönskade beroenden.

## Lärandemål

Efter kapitlet ska läsaren kunna:

- förklara varför dataarkitektur är en strategisk grundförutsättning för AI i offentlig sektor
- identifiera datakvalitet, metadata, informationsägarskap, informationsklassning och data lineage som arkitekturella nyckelfrågor
- resonera om vägval mellan centraliserade, federerade och domänorienterade dataarkitekturer
- bedöma när data är tillräckligt mogen för att användas i AI-förmågor
- formulera arkitektöverväganden för datatillgång, styrning, spårbarhet och livscykel

## Innan vi börjar

I kapitel 2 introducerades förmågedesign: tanken att arkitektur inte bara handlar om system utan om vad organisationen behöver kunna göra. I kapitel 4 och 5 diskuterades styrning, risk och ansvar. I kapitel 6 placerades dessa frågor i offentlig sektors kontext.

Dataarkitektur binder ihop dessa perspektiv. En AI-förmåga kan inte vara bättre än den data, de begrepp och de kontroller som ligger under den. Om data är otydligt definierad, saknar ägare, har okänd kvalitet eller inte kan spåras till källa, blir AI-resultatet svårt att lita på. Det gäller även om modellen i sig är tekniskt avancerad.

Detta kapitel introducerar tre huvudbegrepp:

- **Data product**: en paketerad och förvaltningsbar datatillgång med tydligt syfte, ansvar, kvalitet och användningsvillkor.
- **Metadata**: data om data, till exempel definitioner, ägare, klassning, ursprung, kvalitet och användningsregler.
- **Data lineage**: spårbarhet för var data kommer ifrån, hur den har förändrats och var den används.

Dessa begrepp är inte bara tekniska. De är verktyg för att skapa tillit, förvaltningsbarhet och ansvar i AI-arkitektur.

## Huvudförklaring

### AI flyttar datafrågan från stödjande funktion till strategisk kärna

I traditionell IT-arkitektur har data ofta behandlats som något som finns inuti system. Varje verksamhetssystem äger sina tabeller, sina begrepp och sina integrationer. När information behöver delas byggs integrationer, rapportlager eller analysmiljöer. Detta kan fungera när data används för rapportering eller operativt stöd.

AI förändrar situationen. AI-förmågor använder data på sätt som ofta går över systemgränser, organisationsgränser och processgränser. En AI-assistent kan behöva förstå styrdokument, ärendedata, användarfrågor, rättsliga villkor och historiska beslut. Ett beslutsstöd kan behöva kombinera verksamhetsdata, regelverk, sannolikhetsbedömningar och mänsklig granskning. En automatiserad klassificeringsfunktion kan behöva träningsdata, referensdata, feedbackdata och loggar.

Därmed blir dataarkitektur inte en sidofråga. Den blir en strategisk grund för vilka AI-förmågor organisationen kan ha. Arkitekten behöver kunna svara på frågor som:

- Vilka datamängder får användas för vilket syfte?
- Vem ansvarar för datans kvalitet och tolkning?
- Är data klassad, spårbar och begriplig?
- Kan data användas i AI utan att ändra sitt juridiska eller verksamhetsmässiga sammanhang?
- Finns metadata som gör det möjligt att förstå begränsningar och risker?
- Hur upptäcker vi om AI använder fel data, gammal data eller data utanför avsett sammanhang?

Det strategiska skiftet är att data inte bara ska vara tillgänglig. Den ska vara användbar, styrbar, förklarbar och ansvarsfullt förvaltad.

### Datakvalitet betyder inte bara korrekthet

När AI diskuteras talas det ofta om datakvalitet. Men datakvalitet är inte ett enda mått. För en AI-förmåga kan data vara korrekt men ändå olämplig. Den kan vara aktuell men sakna sammanhang. Den kan vara komplett i ett system men missvisande när den kombineras med annan data. Den kan vara lagligt insamlad för ett syfte men olämplig för ett annat.

För IT-arkitekten är det därför viktigt att bryta ned datakvalitet i flera dimensioner:

- **Korrekthet:** stämmer uppgifterna med verkligheten eller den auktoritativa källan?
- **Aktualitet:** är uppgifterna tillräckligt uppdaterade för det beslut eller stöd de används till?
- **Fullständighet:** saknas viktiga fält, populationer eller tidsperioder?
- **Konsekvens:** betyder samma begrepp samma sak i olika system?
- **Representativitet:** speglar data den grupp, process eller situation som AI-förmågan ska stödja?
- **Spårbarhet:** går det att förstå ursprung och transformationer?
- **Användningsrätt:** får data användas för det aktuella syftet?
- **Kontext:** förstår AI-förmågan vad data betyder i verksamheten?

Den sista punkten är ofta underskattad. AI kan hitta mönster i data utan att förstå den institutionella, juridiska eller organisatoriska kontexten. I offentlig sektor kan detta bli särskilt riskabelt, eftersom data ofta speglar beslut, bedömningar, rättsliga kategorier och historiska arbetssätt. En datamängd kan därför innehålla både fakta och spår av tidigare processer.

Arkitektens uppgift är inte att garantera perfekt data. Uppgiften är att se till att data används med kända begränsningar, rätt kontroller och tydligt ansvar.

### Metadata gör data styrbar

Metadata är ofta skillnaden mellan datatillgång och datakaos. Utan metadata vet organisationen kanske att en datamängd finns, men inte vad den betyder, vem som äger den, hur den får användas eller vilka begränsningar den har.

För AI blir metadata ännu viktigare. En AI-förmåga kan konsumera stora mängder information, kombinera källor och producera svar som verkar sammanhängande. Om metadata saknas blir det svårt att avgöra om resultatet bygger på rätt underlag.

Viktiga typer av metadata för AI-arkitektur är:

- **Begreppsmetadata:** definitioner, termer och relationer mellan begrepp.
- **Ägarskapsmetadata:** informationsägare, systemägare, datasteward och ansvarig verksamhet.
- **Kvalitetsmetadata:** kända brister, uppdateringsfrekvens, täckning och valideringsregler.
- **Klassningsmetadata:** informationsklassning, sekretess, känslighet och åtkomstnivå.
- **Användningsmetadata:** tillåtna användningsområden, begränsningar och rättslig grund.
- **Teknisk metadata:** format, schema, API:er, datatyper och beroenden.
- **Lineage-metadata:** ursprung, transformationer och vidare användning.
- **AI-relaterad metadata:** vilka modeller eller AI-förmågor som använder datan, för vilket syfte och med vilken kontroll.

Metadata behöver inte vara perfekt från början. Men för strategisk AI behöver organisationen ha en medveten miniminivå. Annars riskerar AI-förmågor att byggas på data som ingen fullt ut kan förklara.

### Data lineage som förutsättning för ansvar

Data lineage handlar om att kunna följa data från källa till användning. För AI innebär det att organisationen kan svara på frågor som:

- Vilka källor användes för ett visst AI-resultat?
- Har data transformerats, filtrerats eller berikats?
- Vilka antaganden byggdes in i transformationen?
- Vilken version av datamängden användes?
- Vilka modeller, tjänster eller beslut påverkades av datan?

I traditionell rapportering är lineage viktigt för felsökning och revision. I AI-arkitektur blir det också viktigt för ansvar. Om en AI-förmåga bidrar till felaktigt beslutsstöd måste organisationen kunna förstå om felet berodde på datakälla, transformation, modell, prompt, instruktion, åtkomstkontroll eller mänsklig användning.

Utan lineage blir ansvaret diffust. Då kan felaktigheter förklaras med att ”AI:n gjorde fel”, trots att orsaken kanske var en gammal datakälla, en otydlig definition eller en otillräcklig integrationsregel. En mogen dataarkitektur gör det möjligt att lokalisera fel och förbättra förmågan systematiskt.

### Data product som arkitekturellt arbetssätt

Begreppet data product innebär att data behandlas som en förvaltningsbar produkt snarare än en teknisk biprodukt. En datamängd paketeras med tydligt syfte, ägare, kvalitet, metadata, åtkomstregler, dokumentation och livscykel.

För offentlig sektor kan detta vara ett kraftfullt sätt att göra data användbar utan att släppa styrningen. Ett data product bör inte bara beskriva tekniskt format, utan också verksamhetsbetydelse och användningsvillkor.

Ett data product för AI bör minst kunna svara på:

- Vad representerar datan?
- Vem ansvarar för datans innehåll och kvalitet?
- För vilka syften får den användas?
- Vilka begränsningar eller osäkerheter finns?
- Vilken informationsklassning gäller?
- Hur ofta uppdateras datan?
- Hur spåras förändringar?
- Vilka AI-förmågor använder datan?
- Hur kan fel rapporteras och åtgärdas?

Data product-tänkandet hjälper arkitekten att undvika att AI-projekt skapar egna datakopior utan ansvar. Det flyttar fokus från ”kan vi få ut data?” till ”kan vi förvalta data som en gemensam förmåga?”

### Centraliserad, federerad eller domänorienterad dataarkitektur

Ett centralt vägval för AI är hur organisationen ska organisera dataansvar. Det finns ingen universell modell, men tre arkitekturella idealtyper är vanliga.

**Centraliserad dataarkitektur** innebär att data samlas, styrs och tillgängliggörs via en central funktion eller plattform. Fördelen är gemensamma standarder, bättre kontroll och tydligare säkerhetsmodell. Nackdelen är risk för flaskhalsar, svag verksamhetsförankring och att central funktion får ansvar för data den inte fullt ut förstår.

**Federerad dataarkitektur** innebär att flera verksamheter eller domäner behåller ansvar men samverkar genom gemensamma principer, standarder och styrning. Fördelen är närhet till verksamhetskunskap och skalbar ansvarsfördelning. Nackdelen är att styrningen kan bli ojämn om standarder och mandat är otydliga.

**Domänorienterad dataarkitektur**, ofta inspirerad av data mesh, innebär att data organiseras runt verksamhetsdomäner och tillhandahålls som data products. Fördelen är tydligt ägarskap och bättre koppling till verksamhetsbegrepp. Nackdelen är att det kräver hög mognad, gemensam plattform och stark governance för att inte skapa fragmentering.

I offentlig sektor behöver vägvalet dessutom påverkas av myndighetsgränser, juridiska ansvar, informationsklassning, samverkanskrav och offentlighetens behov av insyn. Arkitekten bör därför undvika både naiv centralisering och okontrollerad decentralisering. Det mest hållbara svaret är ofta en federerad modell med gemensamma principer, tydliga datadomäner och centrala kontrollmekanismer.

### AI kräver både analytisk och operativ dataarkitektur

Många organisationer har separerat operativa system från analysmiljöer. Operativa system stödjer handläggning, ärendehantering och verksamhetsprocesser. Analysmiljöer används för rapportering, statistik och uppföljning.

AI suddar delvis ut denna gräns. Generativ AI kan användas direkt i operativa arbetsflöden. Beslutsstöd kan behöva nära realtidsdata. Klassificering, sammanfattning och rekommendationer kan ske i användarens arbetsmiljö. Samtidigt behöver AI-förmågor ofta träningsdata, testdata, utvärderingsdata och loggdata i mer analytiska miljöer.

Detta skapar nya arkitekturfrågor:

- Vilken data får användas operativt av en AI-funktion?
- Vilken data får användas för träning, test eller utvärdering?
- Hur separeras produktionsdata från experimentmiljöer?
- Hur hanteras syntetisk data, anonymiserad data eller maskerad data?
- Hur loggas AI-användning utan att skapa nya integritetsrisker?
- Hur säkerställs att feedback från användning inte okontrollerat påverkar framtida resultat?

Arkitekturen behöver därför beskriva dataflöden genom hela AI-livscykeln, inte bara mellan system. Det räcker inte med en integrationsbild. Arkitekten behöver visa hur data rör sig från källa till AI-förmåga, vidare till användning, uppföljning, förbättring och eventuell avveckling.

### Kontext är en del av dataarkitekturen

AI kan behandla text, bilder, dokument, tabeller och loggar som indata. Men data utan kontext är lätt att misstolka. I offentlig sektor kan samma ord betyda olika saker i olika verksamheter. Ett ärende kan ha olika status beroende på process. En kategori kan vara juridisk, administrativ eller statistisk. Ett beslut kan vara preliminärt, slutligt, överklagat eller upphävt.

Därför behöver dataarkitektur för AI omfatta semantisk arkitektur: begrepp, relationer, regler och betydelser. Detta kan uttryckas genom informationsmodeller, begreppsmodeller, ontologier, masterdata, referensdata och gemensamma taxonomier.

För generativ AI blir detta särskilt relevant när organisationen använder retrieval-augmented generation, alltså lösningar där modellen hämtar underlag från dokument eller databaser för att ge svar. Då räcker det inte att dokumenten är sökbara. De behöver vara klassade, aktuella, auktoritativa och kontextuellt rätt. Annars kan AI-assistenten ge ett välformulerat men felaktigt eller ofullständigt svar.

Arkitektens fråga bör därför inte bara vara: ”Kan modellen hitta information?” Frågan bör vara: ”Kan modellen hitta rätt information, i rätt version, med rätt kontext, för rätt användare och rätt syfte?”

## Scenario eller beslutskontext

En myndighet vill införa en AI-assistent som ska stödja handläggare genom att sammanfatta ärenden, föreslå relevanta styrdokument och hjälpa till att hitta tidigare liknande ärenden. Initiativet drivs av behovet att korta handläggningstider och minska administrativ belastning.

Den första tekniska diskussionen handlar om modellval och användargränssnitt. Men arkitekten ser snabbt att de avgörande frågorna ligger i dataarkitekturen.

Ärendedata finns i flera system. Dokument lagras både i dokumenthanteringssystem, filytor och äldre verksamhetssystem. Vissa dokument är gallrade, andra är inaktuella men fortfarande sökbara. Begrepp används inte konsekvent mellan avdelningar. Det finns oklarheter kring vilka tidigare beslut som får användas som stöd i nya ärenden. Informationsklassning finns men är inte maskinläsbar. Metadata är ojämn och ibland manuell.

Om AI-assistenten byggs direkt ovanpå dessa källor kan resultatet bli farligt övertygande. Den kan hämta fel version av ett styrdokument, sammanfatta känslig information för fel användare, blanda ärenden från olika rättsliga kontexter eller föreslå historiska mönster som inte längre är giltiga.

Arkitektens slutsats blir att AI-assistenten inte främst kräver ett modellprojekt. Den kräver ett dataarkitekturprojekt. Organisationen behöver först definiera auktoritativa källor, metadata, åtkomstregler, versionshantering, klassning, loggning och ansvar för datakvalitet. AI-förmågan kan därefter införas stegvis, med tydliga begränsningar och kontroller.

Det strategiska vägvalet blir alltså inte ”AI-assistent eller inte”. Det blir: ”Vilken dataarkitektur krävs för att en AI-assistent ska kunna användas utan att underminera rättssäkerhet, sekretess och tillit?”

## Strategiska vägval och arkitektöverväganden

### Vägval 1: Börja med modell eller börja med dataförmåga?

Det vanligaste trycket i organisationen är att snabbt testa en AI-modell. Det kan vara värdefullt för lärande, men riskabelt om piloten börjar användas som faktisk lösning utan datagrund.

**Börja med modell** när syftet är avgränsat lärande, teknisk förståelse eller intern experimentering med låg risk. Se då till att datan är testdata, syntetisk data eller tydligt godkänd för experiment.

**Börja med dataförmåga** när AI ska användas i verkliga processer, nära beslut, med känslig information eller över organisationsgränser. Då behöver dataägarskap, metadata, klassning och lineage etableras före bred användning.

Arkitektens bedömning bör väga verksamhetsnytta mot riskexponering. En pilot utan datagrund kan vara acceptabel som lärande experiment, men inte som dold produktionssättning.

### Vägval 2: Central dataplattform eller domännära data products?

En central dataplattform kan ge gemensam säkerhet, katalogisering, åtkomststyrning och teknisk standardisering. Men den kan också skapa avstånd till verksamhetens begrepp och ansvar.

Domännära data products kan ge bättre kvalitet och förståelse, eftersom de förvaltas nära den verksamhet som skapar och använder datan. Men modellen kräver mognad, tydliga kontrakt och gemensamma spelregler.

För offentlig sektor är ett kombinerat mönster ofta mest realistiskt: central plattform och gemensam governance, men domännära ansvar för innehåll, kvalitet och begrepp. Arkitekten bör då tydligt skilja mellan plattformsansvar och informationsansvar.

### Vägval 3: Full datatillgång eller minimerad åtkomst?

AI-projekt efterfrågar ofta bred datatillgång med argumentet att mer data ger bättre resultat. I offentlig sektor måste detta vägas mot dataminimering, sekretess, integritet och ändamålsbegränsning.

Full datatillgång kan vara relevant för vissa analytiska eller forskningsnära användningar med stark kontroll, men är sällan lämplig som standard. Minimerad åtkomst innebär att AI-förmågan bara får den data som behövs för uppgiften, i rätt kontext och med rätt behörighet.

Arkitekten bör utgå från minsta nödvändiga datamängd och bygga upp åtkomst stegvis. Detta minskar risk och gör det lättare att förklara och granska lösningen.

### Vägval 4: Kopiera data till AI-miljö eller hämta data vid behov?

Att kopiera data till en AI-miljö kan ge prestanda, enklare experiment och mindre belastning på källsystem. Men kopior skapar risker: gammal data, otydligt ägarskap, dubbla säkerhetsmodeller och svår avveckling.

Att hämta data vid behov kan minska kopieringsrisker och behålla auktoritativa källor, men kräver robust integration, åtkomstkontroll och tillgänglighet.

Arkitektens fråga bör vara: vilken data behöver vara kopierad, vilken kan hämtas dynamiskt och vilken bör aldrig lämna sitt ursprungliga sammanhang? Svaret kan variera mellan träningsdata, referensdata, dokumentunderlag, loggar och operativa ärenden.

### Vägval 5: Mänsklig tolkning eller maskinläsbar styrning?

Många organisationer har informationsklassning, gallringsregler och användningsvillkor dokumenterade i policyer. Problemet är att AI-system inte kan följa dokument som inte är operationaliserade i arkitekturen.

Mänsklig tolkning räcker i små manuella processer, men blir otillräcklig när AI-förmågor integreras i arbetsflöden. Maskinläsbar styrning innebär att klassning, åtkomst, syfte, begränsningar och loggning uttrycks så att system kan tillämpa dem.

Arkitekten bör sträva efter att centrala styrningsregler inte bara finns i dokument utan också avspeglas i metadata, policy engines, åtkomstkontroller, kataloger och loggning.

### Vägval 6: Gemensamma begrepp eller lokal flexibilitet?

AI gynnas av gemensamma begrepp, eftersom modeller och dataflöden behöver konsekvent betydelse. Samtidigt har offentlig sektor många lokala variationer, juridiska skillnader och verksamhetsspecifika termer.

För hård standardisering kan skapa motstånd och förenkla bort viktiga skillnader. För stor lokal flexibilitet kan göra AI-resultat inkonsekventa och svåra att skala.

Arkitektens uppgift är att identifiera vilka begrepp som måste vara gemensamma och vilka som kan vara lokala. Ett praktiskt mönster är att definiera gemensamma kärnbegrepp och låta domänerna komplettera med lokala attribut, regler och förklaringar.

## Vanliga felsatsningar

- **Felsatsning:** AI-projektet startar med modellval och ignorerar datagrunden.
  - **Varför det händer:** Modeller är synliga, nya och lätta att demonstrera, medan dataarkitektur upplevs som långsam grundläggning.
  - **Hur arkitekten kan undvika det:** Kräv en data readiness-bedömning innan AI-förmågan går från experiment till användning.

- **Felsatsning:** Organisationen tror att tillgång till mer data automatiskt ger bättre AI.
  - **Varför det händer:** Det finns en förenklad föreställning om att AI förbättras linjärt med datamängd.
  - **Hur arkitekten kan undvika det:** Styr mot relevant, rätt klassad och kontextualiserad data snarare än maximal datamängd.

- **Felsatsning:** Metadata behandlas som dokumentation i efterhand.
  - **Varför det händer:** Projekt fokuserar på funktion och integration först, och skjuter beskrivning, ägarskap och klassning till senare.
  - **Hur arkitekten kan undvika det:** Gör metadata till ett leveranskrav för data som ska användas i AI-förmågor.

- **Felsatsning:** AI-lösningen skapar egna datakopior utan tydlig livscykel.
  - **Varför det händer:** Kopior är ofta tekniskt enklare än robust integration och styrd åtkomst.
  - **Hur arkitekten kan undvika det:** Dokumentera kopiors syfte, ägare, uppdatering, klassning, retention och avveckling.

- **Felsatsning:** Informationsägarskap förväxlas med systemägarskap.
  - **Varför det händer:** Många organisationer har starkare struktur för systemförvaltning än för informationsförvaltning.
  - **Hur arkitekten kan undvika det:** Skilj tydligt mellan systemägare, informationsägare, datasteward och teknisk plattformsägare.

- **Felsatsning:** AI används på data vars begrepp varierar mellan verksamheter.
  - **Varför det händer:** Tekniska format kan integreras även när semantiken inte är harmoniserad.
  - **Hur arkitekten kan undvika det:** Inför begreppsmodeller och semantisk granskning som del av AI-arkitekturen.

- **Felsatsning:** Loggar och feedback samlas in utan tydligt syfte.
  - **Varför det händer:** Organisationen vill ”spara för framtida förbättringar” utan att definiera användning, ansvar och risk.
  - **Hur arkitekten kan undvika det:** Behandla loggar och feedbackdata som egna datatillgångar med klassning, ändamål och retention.

## Arkitektens checklista

Använd checklistan när en AI-förmåga föreslås eller när en befintlig AI-lösning ska skalas.

### 1. Datans syfte och användning

- Är det tydligt vilket verksamhetssyfte datan ska användas för?
- Är syftet förenligt med hur datan samlades in eller skapades?
- Är det tydligt om datan används för träning, test, utvärdering, beslutsstöd, sökning, sammanfattning eller automatisering?
- Finns avgränsning för vad AI-förmågan inte får använda datan till?

### 2. Ägarskap och ansvar

- Finns informationsägare för centrala datamängder?
- Är ansvar för kvalitet, tolkning och åtkomst dokumenterat?
- Är systemägarskap och informationsägarskap separerade?
- Finns datasteward eller motsvarande roll för praktisk förvaltning?

### 3. Metadata och katalogisering

- Finns definitioner av centrala begrepp?
- Finns klassning, känslighet och åtkomstregler som metadata?
- Finns information om uppdateringsfrekvens och kända kvalitetsbrister?
- Är metadata tillräckligt maskinläsbar för att kunna användas i styrning?

### 4. Kvalitet och representativitet

- Är datan korrekt nog för det tänkta användningsområdet?
- Är datan aktuell nog?
- Saknas viktiga grupper, ärendetyper eller tidsperioder?
- Finns risk att historiska arbetssätt eller snedvridningar reproduceras?
- Är kvalitetsbrister synliga för användare och beslutsfattare?

### 5. Spårbarhet och revision

- Kan data följas från källa till AI-resultat?
- Loggas vilken data och vilken version som användes?
- Går det att rekonstruera underlag för ett AI-stött beslut?
- Finns rutiner för att utreda felaktiga AI-resultat?

### 6. Åtkomst och säkerhet

- Använder AI-förmågan minsta nödvändiga datamängd?
- Är åtkomst kopplad till användarens roll, syfte och kontext?
- Finns skydd mot att AI sammanställer information som användaren inte borde se samlat?
- Är känslig data maskerad, filtrerad eller skyddad där det behövs?

### 7. Livscykel och avveckling

- Finns plan för hur data uppdateras?
- Finns retention och gallring även för AI-relaterade kopior, loggar och feedback?
- Finns plan för vad som händer om datakälla, begrepp eller regelverk förändras?
- Kan AI-förmågan avvecklas utan att lämna oklara datakopior?

### 8. Arkitekturell skalbarhet

- Är datamodellen återanvändbar för fler AI-förmågor?
- Finns gemensamma mönster för metadata, katalog, åtkomst och lineage?
- Kan domäner publicera data products utan att skapa fragmentering?
- Finns gemensam governance som balanserar central kontroll och domänansvar?

## Snabb sammanfattning

- AI-förmågor är beroende av dataarkitektur, inte bara modellval.
- Datakvalitet handlar om korrekthet, aktualitet, fullständighet, konsekvens, representativitet, spårbarhet, användningsrätt och kontext.
- Metadata gör data begriplig, styrbar och möjlig att använda ansvarsfullt.
- Data lineage behövs för att förstå, granska och förbättra AI-resultat.
- Data products kan göra datatillgångar förvaltningsbara och återanvändbara.
- Offentlig sektor behöver särskilt beakta informationsklassning, rättsligt syfte, sekretess, integritet, förvaltningsbarhet och tillit.
- Ett hållbart mönster är ofta federerad dataarkitektur med gemensamma principer, central plattformskapacitet och domännära informationsansvar.

## Reflektionsfrågor

1. Vilka datamängder i din organisation skulle vara mest värdefulla för AI, och vilka är samtidigt mest riskfyllda?
2. Var finns det tydliga informationsägare, och var är ansvaret oklart?
3. Vilken metadata saknas i dag för att AI-förmågor ska kunna granskas och styras?
4. Är organisationens informationsklassning tillräckligt operationaliserad för AI, eller finns den mest som dokumentation?
5. Vilka datakopior, loggar eller feedbackflöden riskerar att uppstå när AI börjar användas bredare?
6. Vilka begrepp behöver harmoniseras innan AI kan ge tillförlitligt stöd över verksamhetsgränser?
7. Var bör organisationen centralisera datakapacitet, och var bör ansvar ligga nära verksamhetsdomänen?

## Nästa steg

Dataarkitektur svarar på frågan vilka datatillgångar AI kan använda och under vilka villkor. Nästa kapitel går vidare till integrationsarkitekturen: hur AI-förmågor kopplas till befintliga system, processer och användargränssnitt utan att skapa oöverskådliga beroenden eller dolda produktionsrisker.

Där dataarkitekturen skapar förutsättningar för tillit, skapar integrationsarkitekturen förutsättningar för kontrollerad användning i verkliga arbetsflöden.
