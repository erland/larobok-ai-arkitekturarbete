# Kapitel 1: Varför AI förändrar IT-arkitektens uppdrag

## Varför detta kapitel finns

AI förändrar inte bara vilka tekniska lösningar en organisation kan bygga. AI förändrar också hur arkitektur förstås, beslutas, styrs och följs upp. För IT-arkitekter i offentlig sektor innebär detta ett skifte från att främst beskriva system, integrationer och tekniska målarkitekturer till att också forma förmågor där data, automatisering, mänskligt omdöme, juridik och tillit hänger samman.

Det här kapitlet etablerar bokens grundtes: AI är både ett verktyg för arkitekturarbetet, en komponent i IT-arkitekturen och en strategisk förändringskraft. Om arkitekten bara betraktar AI som ännu en teknisk komponent riskerar viktiga frågor att hamna utanför arkitekturarbetet: ansvar, spårbarhet, informationskvalitet, styrbarhet, verksamhetsförändring, upphandling, leverantörsberoenden och långsiktig förvaltningsbarhet.

Offentlig sektor har dessutom särskilda villkor. System ska inte bara vara effektiva. De ska vara rättssäkra, transparenta, robusta, tillgängliga, säkra och möjliga att granska. AI kan förstärka offentliga tjänster, men den kan också göra ansvarskedjor otydliga om arkitekturen inte utformas med dessa krav från början.

## Lärandemål

Efter kapitlet ska läsaren kunna:

- skilja mellan AI som arbetsverktyg, AI som systemkomponent och AI som strategisk förändringskraft
- beskriva varför AI flyttar arkitektens fokus från systemstruktur till förmågor, beslut, dataflöden och styrning
- identifiera vilka arkitekturfrågor som blir mer centrala när AI införs i offentlig sektor
- förklara varför arkitekten behöver kombinera teknisk förståelse med ansvar, risk och verksamhetsstyrning
- formulera de första frågorna som bör ställas innan en organisation går vidare med AI i sin målarkitektur

## Innan vi börjar

Boken utgår från att läsaren redan har praktisk erfarenhet av IT-arkitektur. Det betyder att grundläggande begrepp som målarkitektur, nuläge, förmåga, integration, informationsmodell, säkerhetskrav och styrning inte förklaras från noll. Däremot kommer boken att omtolka flera av dessa begrepp i ljuset av AI.

I traditionellt arkitekturarbete kan en arkitekt ofta beskriva en lösning genom relativt stabila komponenter: applikationer, integrationer, datalager, API:er, identitets- och behörighetslösningar, driftmiljöer och förvaltningsobjekt. Med AI tillkommer komponenter som inte alltid beter sig deterministiskt, som kan vara beroende av träningsdata eller externa modeller, och som kan påverka beslut på sätt som kräver ny typ av granskning.

Det betyder inte att tidigare arkitekturarbete blir irrelevant. Tvärtom blir det viktigare. AI förstärker behovet av tydlig informationsarkitektur, styrbar integrationsarkitektur, robust säkerhetsarkitektur och förvaltningsbar målarkitektur. Skillnaden är att arkitekten behöver se fler beroenden samtidigt.

## Huvudförklaring

### AI som tre olika saker

Ett vanligt misstag är att tala om AI som om det vore en enda typ av teknik. För arkitekten är det mer användbart att skilja mellan tre perspektiv.

Det första perspektivet är **AI som arbetsverktyg**. Här används AI för att stödja arkitektens eget arbete: sammanfatta dokumentation, jämföra lösningsalternativ, ta fram första utkast till modeller, analysera krav, skapa beslutsunderlag eller identifiera beroenden. I detta perspektiv är AI en förstärkning av arkitektens arbetsprocess. Nyckelfrågan blir inte bara “kan AI hjälpa oss?” utan “hur säkerställer vi kvalitet, sekretess, spårbarhet och mänskligt ansvar när AI används i arkitekturarbetet?”

Det andra perspektivet är **AI som systemkomponent**. Här blir AI en del av själva lösningen. Det kan handla om klassificering, rekommendationer, textgenerering, bildanalys, automatiserad prioritering, prediktion, avvikelseupptäckt eller beslutsstöd. I detta perspektiv behöver arkitekten förstå hur AI-komponenten samspelar med data, processer, användargränssnitt, integrationer, säkerhetskontroller och loggning.

Det tredje perspektivet är **AI som strategisk förändringskraft**. Här påverkar AI hur organisationen ser på tjänsteutveckling, verksamhetsförmågor, sourcing, kompetens, styrning, risk och ansvar. Arkitekten behöver då delta i frågor som tidigare kanske låg tydligare hos strategi, juridik, verksamhetsutveckling eller säkerhet. AI blir en fråga om hur offentlig verksamhet ska organiseras och utvecklas, inte bara om vilken teknik som ska införas.

Dessa tre perspektiv blandas ofta samman. En organisation kan börja med AI som arbetsverktyg, snabbt gå vidare till AI som systemkomponent och därefter upptäcka att den saknar styrning, dataägarskap eller gemensamma principer. Arkitektens uppgift är att synliggöra sambanden innan lösningen blir svår att styra.

### Från lösningsbeskrivning till ansvarskedja

AI gör ansvarskedjan mer central. I många traditionella IT-system är det relativt tydligt vilken komponent som gör vad. En regelmotor tillämpar regler. Ett ärendehanteringssystem lagrar ärenden. En integration flyttar information mellan system. Även när systemlandskapet är komplext går det ofta att följa logiken genom kod, konfiguration, processbeskrivningar och informationsmodeller.

AI-baserade lösningar kan vara svårare att beskriva på samma sätt. En språkmodell kan generera olika svar vid olika tillfällen. En prediktionsmodell kan ge en sannolikhetsbedömning snarare än ett ja eller nej. En klassificeringsmodell kan fungera väl på historiska data men sämre när verksamhetens mönster förändras. En AI-assistent kan vara beroende av både modell, prompt, behörighet, hämtade dokument, användarens fråga och systeminstruktioner.

För arkitekten innebär det att målarkitekturen måste beskriva mer än komponenter. Den behöver också beskriva ansvarskedjor:

- Vem ansvarar för att AI-förmågan är lämplig för sitt syfte?
- Vem äger de data som används?
- Vem godkänner användningsfall?
- Vem följer upp kvalitet och fel?
- Vem beslutar när en modell, tjänst eller integration ska ändras eller stängas av?
- Hur kan beslut, rekommendationer och automatiserade åtgärder granskas i efterhand?
- Hur skiljer organisationen mellan beslutsstöd och automatiserat beslutsfattande?

Detta är särskilt viktigt i offentlig sektor, där transparens, likabehandling, integritet och rättssäkerhet inte är valfria kvalitetsattribut. De är en del av uppdraget.

### Från system till förmåga

AI passar sällan bra i en alltför snäv systemlogik. En AI-förmåga består normalt av flera samverkande delar: data, modeller, integrationer, användargränssnitt, arbetsprocesser, kontroller, loggning, behörigheter, uppföljning, juridiska bedömningar och organisatoriskt ansvar.

Därför behöver arkitekten ofta beskriva AI på förmågenivå. En AI-förmåga kan till exempel vara “stöd för informationssökning i interna styrdokument”, “prioriteringsstöd för inkommande ärenden”, “automatisk sammanfattning av beslutsunderlag” eller “avvikelseanalys i ekonomiska transaktioner”. Dessa förmågor kan realiseras med flera olika tekniska lösningar, men de behöver samma typ av arkitekturell omsorg.

När arkitekten arbetar på förmågenivå blir frågan bredare än “vilket system ska vi köpa?” Den blir snarare:

- Vilken verksamhetsförmåga ska stärkas?
- Vilka beslut eller arbetsmoment påverkas?
- Vilka data behövs och vilken kvalitet har de?
- Vilket ansvar får inte automatiseras bort?
- Vilka kontroller behöver finnas före, under och efter användning?
- Hur ska förmågan styras över tid?
- Vad händer om modellen, leverantören eller regelverket förändras?

Detta är ett strategiskt skifte. Arkitektens värde ligger inte bara i att välja teknisk lösning, utan i att strukturera vägval så att organisationen kan fatta informerade beslut.

### AI gör befintliga arkitekturbrister synliga

AI-projekt misslyckas ofta inte därför att AI-tekniken saknas, utan därför att grundförutsättningarna är svaga. Otydligt informationsägarskap, bristande datakvalitet, fragmenterade integrationer, svag identitetshantering, oklara processer och otydlig förvaltning blir mer problematiska när AI kopplas in.

En språkmodell som ska svara på frågor om interna riktlinjer behöver veta vilka dokument som är aktuella, vilka som gäller för vilken målgrupp, vilka som får läsas av vem och hur källor ska redovisas. Ett beslutsstöd behöver spårbara data, tydliga beslutspunkter och väl definierade ansvar. En automatiserad klassificering behöver övervakning, avvikelsehantering och rutiner för rättelse.

AI fungerar därför som ett slags arkitekturellt stresstest. Den avslöjar om organisationen faktiskt har kontroll över sin information, sina processer och sina styrmodeller. För arkitekten är detta en möjlighet. Genom att rama in AI som en förmåge- och arkitekturfråga kan organisationen använda AI-initiativ för att stärka sin digitala grund.

### Reglering och ramverk påverkar arkitekturarbetet

AI införs inte i ett tomrum. Inom EU påverkas offentlig sektor av EU:s AI Act, som trädde i kraft den 1 augusti 2024 och är uppbyggd kring en riskbaserad modell med successiv tillämpning av olika krav. Den exakta tillämpningen kan behöva följas löpande, men arkitekturellt är riktningen tydlig: AI-system behöver klassificeras, styras, dokumenteras och följas upp utifrån risk och användningsområde. Källa: EU-kommissionen, “AI Act”, https://digital-strategy.ec.europa.eu/en/policies/regulatory-framework-ai.

Även frivilliga och internationella ramverk påverkar hur organisationer arbetar med AI. NIST AI Risk Management Framework och NIST:s generativa AI-profil betonar styrning, kartläggning, mätning och hantering av AI-risker. För arkitekten är sådana ramverk inte bara compliance-stöd. De kan användas för att strukturera arkitekturbeslut, ansvar, kontroller och uppföljning. Källa: NIST, “AI Risk Management Framework”, https://www.nist.gov/itl/ai-risk-management-framework.

Poängen i detta kapitel är inte att gå igenom regelverk i detalj. Det kommer senare. Poängen är att arkitekturarbetet behöver utformas så att förändrade regler, standarder och förväntningar kan hanteras utan att varje AI-initiativ blir ett isolerat undantag.

### Arkitektens mandat förändras

När AI blir strategiskt viktigt behöver IT-arkitekten ta en tydligare roll i gränslandet mellan teknik, verksamhet, juridik, säkerhet och ledning. Det betyder inte att arkitekten ska ersätta jurister, dataskyddsombud, informationssäkerhetsansvariga, verksamhetsägare eller upphandlare. Det betyder att arkitekten behöver skapa strukturer där deras perspektiv kan omsättas till sammanhängande lösningar.

I praktiken innebär det att arkitekten behöver bidra med:

- principer för när AI får och inte får användas
- mönster för hur AI kopplas till data och befintliga system
- beslutsunderlag för sourcing och plattformsval
- målarkitektur som hanterar både innovation och kontroll
- krav på loggning, spårbarhet, behörighet och uppföljning
- modeller för livscykelhantering och avveckling
- frågor som hjälper ledningen förstå långsiktiga konsekvenser

Detta breddar arkitektrollen. Den blir mindre begränsad till teknisk design och mer inriktad på styrbar förändring.

## Scenario eller beslutskontext

Föreställ dig en myndighet som vill införa en AI-assistent för att hjälpa handläggare hitta relevant information i styrdokument, tidigare beslut, interna vägledningar och offentliga föreskrifter. Vid första anblick verkar initiativet okomplicerat. Det handlar inte om att automatisera beslut, utan om att hjälpa medarbetare hitta information snabbare.

Men redan i ett tidigt arkitekturforum uppstår frågor:

- Får alla handläggare söka i allt material?
- Hur säkerställs att assistenten använder aktuell och beslutad information?
- Ska assistenten alltid ange källor?
- Hur hanteras sekretessbelagda uppgifter?
- Vad händer om assistenten ger ett felaktigt svar?
- Är svaret ett arbetsstöd eller ett beslutsunderlag?
- Ska interaktioner loggas, och vem får läsa loggarna?
- Vilken leverantör får behandla vilka data?
- Hur ska lösningen avvecklas om regelverk, avtal eller riskbedömning förändras?

Detta scenario visar varför AI snabbt blir en arkitekturfråga. Det räcker inte att välja en modell eller ett verktyg. Organisationen behöver en arkitektur som hanterar dataåtkomst, informationsklassning, källhantering, användarupplevelse, ansvar, säkerhet, uppföljning och förvaltning.

Arkitektens roll blir att flytta diskussionen från “kan vi bygga en AI-assistent?” till “vilken styrbar AI-förmåga behöver vi, och vilka villkor måste vara uppfyllda för att den ska vara lämplig i offentlig verksamhet?”

## Strategiska vägval och arkitektöverväganden

### Vägval 1: AI som lokal produktivitet eller gemensam organisatorisk förmåga

En organisation kan tillåta enskilda team att använda AI-verktyg lokalt, eller bygga gemensamma förmågor med tydlig styrning. Lokal användning ger snabb innovation och lärande, men kan skapa spretighet, dubbelarbete, informationsrisker och otydliga leverantörsberoenden. En gemensam förmåga ger kontroll och återanvändbarhet, men kan bli långsam om styrningen är för tung.

Arkitekten bör särskilt bedöma:

- vilka användningsfall som kan tillåtas som lokal experimentering
- vilka användningsfall som kräver central styrning
- vilka datakategorier som aldrig får användas i öppna eller okontrollerade verktyg
- vilka gemensamma komponenter som bör etableras tidigt
- hur lärdomar från lokala initiativ fångas upp i målarkitekturen

För offentlig sektor är detta vägval centralt eftersom okontrollerad användning kan påverka sekretess, integritet, informationssäkerhet och tillit.

### Vägval 2: Snabb nytta eller långsiktig förvaltningsbarhet

AI-lösningar kan ofta demonstreras snabbt. En prototyp kan imponera på några dagar eller veckor. Men skillnaden mellan prototyp och förvaltningsbar förmåga är stor. En prototyp behöver sällan hantera fullständig behörighetsmodell, loggning, övervakning, incidenthantering, juridisk dokumentation, upphandling, modelluppdateringar eller avvecklingsplan.

Arkitekten bör inte stoppa experiment i onödan, men behöver tydliggöra gränsen mellan experiment och produktion. Ett användningsfall som går från test till faktisk verksamhetsanvändning bör passera en arkitekturell kontrollpunkt.

Centrala frågor är:

- Vad krävs för att lösningen ska kunna driftsättas ansvarsfullt?
- Vilka krav kan vänta under experimentfasen, och vilka kan inte vänta?
- Vem äger lösningen efter piloten?
- Hur mäts om lösningen fortsätter vara lämplig?
- Hur avvecklas den om den inte uppfyller kraven?

### Vägval 3: AI som beslutsstöd eller automatiserat beslut

Det är stor skillnad mellan en AI-lösning som hjälper en människa att hitta information och en lösning som automatiskt påverkar ett beslut. Skillnaden är inte bara teknisk utan juridisk, etisk och organisatorisk.

Arkitekten bör kräva att varje AI-förmåga klassificeras utifrån vilken påverkan den har på beslut:

- Informerar den användaren?
- Rekommenderar den ett alternativ?
- Prioriterar den ärenden?
- Initierar den en åtgärd?
- Fattar den beslut utan mänsklig prövning?
- Påverkar den individers rättigheter, skyldigheter eller tillgång till service?

Ju närmare lösningen kommer faktisk beslutspåverkan, desto starkare krav bör ställas på spårbarhet, förklarbarhet, mänsklig kontroll, dokumentation och uppföljning.

### Vägval 4: Centraliserad eller federerad AI-styrning

Offentliga organisationer behöver ofta balansera central kontroll med verksamhetsnära ansvar. En central modell kan ge tydliga principer, gemensam plattform, enhetliga kontroller och bättre upphandlingskraft. En federerad modell kan ge snabbare anpassning till verksamhetens behov och minska flaskhalsar.

Arkitektens fråga är inte bara vilken modell som är bäst, utan vilka beslut som ska ligga var. Exempelvis kan arkitekturprinciper, informationsklassning, godkända plattformar och säkerhetskrav vara centrala, medan prioritering av verksamhetsnära användningsfall kan ligga närmare verksamheten.

Ett rimligt mål är ofta en styrd federering: gemensamma ramar, men decentraliserad tillämpning inom tydliga gränser.

### Vägval 5: Teknikdriven AI-strategi eller verksamhetsdriven AI-strategi

AI-initiativ kan börja i teknikmöjligheter, men långsiktig nytta kräver koppling till verksamhetsförmågor. En teknikdriven strategi riskerar att skapa många verktyg utan tydlig effekt. En verksamhetsdriven strategi kan å andra sidan bli för försiktig om organisationen saknar förståelse för vad tekniken faktiskt möjliggör.

Arkitekten behöver översätta mellan dessa perspektiv. Det innebär att beskriva AI både som teknisk möjlighet och som förändring av verksamhetsförmåga.

## Vanliga felsatsningar

- **Felsatsning:** AI behandlas som ett fristående teknikspår.
  - **Varför det händer:** Organisationen vill snabbt testa nya verktyg och placerar AI utanför ordinarie arkitektur- och styrprocesser.
  - **Hur arkitekten kan undvika det:** Koppla AI-initiativ till målarkitektur, informationsstyrning, säkerhetsarkitektur och verksamhetsförmågor redan från början.

- **Felsatsning:** Piloter startas utan förvaltningsidé.
  - **Varför det händer:** Prototyper är enkla att demonstrera, men svårare att ta ansvar för över tid.
  - **Hur arkitekten kan undvika det:** Kräv tidig beskrivning av ägarskap, livscykel, uppföljning, avveckling och ansvar innan piloten får bli produktionsnära.

- **Felsatsning:** Organisationen fokuserar på modellval före data- och ansvarskedja.
  - **Varför det händer:** Modeller och verktyg är synliga och marknadsförs aktivt, medan datakvalitet och styrning är mindre glamoröst.
  - **Hur arkitekten kan undvika det:** Inled varje AI-diskussion med användningsfall, data, beslutspåverkan, ansvar och risk, innan modell eller leverantör väljs.

- **Felsatsning:** AI används i arkitekturarbetet utan kvalitetssäkring.
  - **Varför det händer:** AI kan snabbt skapa texter, modeller och sammanfattningar som ser professionella ut.
  - **Hur arkitekten kan undvika det:** Inför principer för hur AI-genererat material granskas, källbeläggs, sekretessbedöms och dokumenteras.

- **Felsatsning:** Offentlig sektors särskilda krav behandlas som sena compliance-frågor.
  - **Varför det händer:** Projekt vill visa nytta snabbt och antar att juridik, informationssäkerhet och upphandling kan lösas senare.
  - **Hur arkitekten kan undvika det:** Gör rättssäkerhet, transparens, informationsklassning, integritet och revisionsbarhet till arkitekturella krav, inte efterhandskontroller.

## Arkitektens checklista

Använd checklistan när ett AI-initiativ förs in i arkitekturforum, portföljstyrning eller målarkitekturdiskussion.

### 1. Syfte och förmåga

- Vilken verksamhetsförmåga ska AI stärka?
- Är nyttan formulerad som effekt, inte bara som teknikinförande?
- Är användningsfallet kopplat till offentligt värde, kvalitet, effektivitet eller tillgänglighet?
- Finns en tydlig gräns mellan experiment, pilot och produktionssatt förmåga?

### 2. Beslutspåverkan

- Ger AI information, rekommendationer, prioriteringar eller beslut?
- Kan lösningen påverka enskilda individers rättigheter, skyldigheter eller service?
- Finns mänsklig kontroll där det behövs?
- Är ansvarsfördelningen tydlig om AI ger felaktigt eller missvisande stöd?

### 3. Data och information

- Vilka data används?
- Vem äger informationen?
- Är informationen aktuell, korrekt och relevant?
- Finns metadata, källspårning och behörighetsstyrning?
- Är sekretess, integritet och informationsklassning hanterade?

### 4. Styrning och ansvar

- Vem godkänner användningsfallet?
- Vem ansvarar för livscykeln?
- Vem följer upp kvalitet, risk och effekt?
- Finns beslutslogg för viktiga arkitekturval?
- Är AI-förmågan införd i ordinarie styrning och förvaltning?

### 5. Teknik och integration

- Är AI-komponenten isolerad eller integrerad i kritiska processer?
- Vilka system och dataflöden påverkas?
- Finns krav på loggning, övervakning och incidenthantering?
- Kan lösningen byta modell eller leverantör utan orimlig ombyggnad?
- Finns en exit-strategi?

### 6. Tillit och transparens

- Kan användaren förstå när AI används?
- Kan källor, antaganden och begränsningar redovisas?
- Finns möjlighet att ifrågasätta eller korrigera resultat?
- Kan organisationen förklara lösningen för internrevision, tillsyn, media eller medborgare?

## Snabb sammanfattning

- AI förändrar IT-arkitektens uppdrag eftersom AI påverkar både arbetssätt, systemkomponenter och strategiska verksamhetsförmågor.
- Arkitekten behöver skilja mellan AI som arbetsverktyg, AI som del av lösningen och AI som förändringskraft.
- I offentlig sektor måste AI-arkitektur hantera rättssäkerhet, transparens, informationsklassning, ansvar, upphandling, säkerhet och långsiktig förvaltning.
- AI gör befintliga arkitekturbrister synliga, särskilt inom data, integration, identitet, styrning och ansvar.
- Arkitektens roll breddas från teknisk design till att strukturera vägval, ansvarskedjor och styrbar transformation.
- Det viktigaste första steget är inte att välja modell, utan att förstå användningsfall, beslutspåverkan, dataförutsättningar och ansvar.

## Reflektionsfrågor

1. Vilka AI-initiativ i din organisation behandlas i dag som teknikprojekt men borde behandlas som arkitektur- eller styrningsfrågor?
2. Var går gränsen mellan tillåten lokal AI-användning och användning som kräver central styrning?
3. Vilka befintliga arkitekturbrister skulle bli synliga om organisationen försökte produktionssätta en AI-förmåga i morgon?
4. Vilka beslutspunkter i era processer är olämpliga att automatisera, även om tekniken skulle kunna göra det?
5. Vilka arkitekturprinciper saknas för att AI ska kunna införas ansvarsfullt?

## Nästa steg

Nästa kapitel fördjupar skiftet från systemdesign till förmågedesign. Där behandlas hur AI gör det nödvändigt att beskriva arkitektur utifrån verksamhetsförmågor, dataflöden, beslutspunkter och värdeströmmar snarare än enbart applikationer och tekniska komponenter.
