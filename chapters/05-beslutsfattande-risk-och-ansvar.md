# Kapitel 5: Beslutsfattande, risk och ansvar

## Varför detta kapitel finns

AI förändrar inte bara vilka system som byggs. AI förändrar också hur beslut förbereds, fattas, motiveras, följs upp och ifrågasätts. För offentlig sektor är detta en kärnfråga. Ett arkitekturbeslut som rör AI är sällan enbart ett tekniskt beslut; det kan påverka rättssäkerhet, transparens, likabehandling, informationssäkerhet, upphandling, verksamhetsansvar och medborgarnas förtroende.

I traditionell IT-arkitektur kan risk ofta beskrivas i termer av tillgänglighet, konfidentialitet, riktighet, kostnad, integration, teknisk skuld och leverantörsberoende. Dessa risker finns kvar. Men AI tillför ytterligare lager: osäkerhet i utdata, svårförklarade modellbeteenden, beroenden till träningsdata, förändrade ansvarskedjor, risk för automatiseringsbias och en ny typ av glapp mellan teknisk funktion och faktisk verksamhetseffekt.

Det är därför inte tillräckligt att fråga om en AI-lösning fungerar. Arkitekten behöver också fråga: fungerar den på ett sätt som organisationen kan stå för?

Detta kapitel behandlar hur IT-arkitekten kan strukturera beslut, risk och ansvar när AI blir en del av arkitekturen. Fokus ligger inte på juridisk detaljtolkning, utan på arkitektens praktiska ansvar: att se till att beslut blir spårbara, att risker blir synliga, att ansvar inte försvinner mellan roller och att AI-förmågor kan granskas över tid.

## Lärandemål

Efter kapitlet ska läsaren kunna:

- skilja mellan teknisk risk, verksamhetsrisk, rättslig risk och förtroenderisk i AI-relaterade arkitekturbeslut
- beskriva varför ansvar inte kan flyttas från organisationen till modellen, leverantören eller verktyget
- använda riskklassning som beslutsstöd snarare än som administrativ efterhandskontroll
- formulera arkitekturbeslut så att syfte, antaganden, ansvar, kontroller och uppföljning blir spårbara
- identifiera när AI bör vara beslutsstöd, när AI kan automatisera delar av ett flöde och när AI inte bör användas

## Innan vi börjar

Tidigare kapitel har etablerat tre viktiga utgångspunkter.

För det första är AI inte bara en teknikkomponent. AI kan vara ett arbetsverktyg för arkitekten, en komponent i en lösning eller en strategisk förändringskraft som påverkar verksamhetsförmågor och styrning.

För det andra bör AI diskuteras utifrån förmågor, inte bara system. En AI-funktion får betydelse genom de beslut, processer och ansvarskedjor den kopplas till.

För det tredje kräver AI-augmented architecture att arkitekten använder AI med omdöme. AI kan hjälpa till att analysera, sammanfatta och föreslå, men kan inte bära ansvar för arkitekturens konsekvenser.

Detta kapitel bygger vidare på dessa idéer. Nu flyttas fokus från vad AI kan bidra med till vilka beslut organisationen måste kunna stå för.

## Huvudförklaring

### AI gör beslut mer beroende av antaganden

Alla arkitekturbeslut bygger på antaganden. Skillnaden med AI är att antagandena ofta är fler, mindre synliga och mer dynamiska.

När en organisation inför ett traditionellt ärendehanteringssystem kan arkitekten ofta beskriva systemets huvudsakliga logik, datamodell, integrationer och behörighetsstruktur. Det betyder inte att systemet är enkelt, men dess beteende är i regel mer deterministiskt. Samma indata, samma regel och samma tillstånd ger normalt samma resultat.

AI-förmågor fungerar ofta annorlunda. En modell kan ge sannolika, användbara eller övertygande svar utan att svaret är garanterat korrekt. En klassificeringsmodell kan prestera väl på testdata men sämre i en ny verksamhetskontext. En generativ AI-tjänst kan skapa text som ser rimlig ut men bygger på felaktiga antaganden. En rekommendationsfunktion kan förändra användares beteende och därmed förändra den miljö den var tänkt att stödja.

Arkitektens uppgift blir därför att synliggöra antagandena.

Exempel på antaganden som bör dokumenteras:

- Vilket beslut eller vilken arbetsuppgift ska AI-förmågan påverka?
- Vilka data används, och vilka begränsningar har dessa data?
- Vilken typ av fel är acceptabla respektive oacceptabla?
- Vilka grupper eller situationer riskerar att påverkas oproportionerligt?
- Vilken mänsklig granskning krävs?
- Hur upptäcks försämrad kvalitet över tid?
- Vem äger risken när AI-förmågan används i verksamheten?

Ett bra arkitekturbeslut beskriver alltså inte bara vald lösning. Det beskriver även varför lösningen bedöms vara försvarbar under vissa antaganden.

### Risk är inte bara sannolikhet gånger konsekvens

Många organisationer använder riskmatriser där risk bedöms genom sannolikhet och konsekvens. Det kan vara användbart, men AI kräver ofta fler dimensioner.

En låg sannolikhet kan ändå vara oacceptabel om konsekvensen påverkar rättigheter, integritet eller förtroende. En risk kan vara svår att kvantifiera men ändå arkitekturellt avgörande. En modell kan fungera statistiskt väl men skapa problem i enskilda fall där den används som underlag för myndighetsutövning. En AI-assistent kan vara effektiv men samtidigt skapa informationsläckage om användare matar in känslig information.

För offentlig sektor bör arkitekten därför komplettera traditionell riskanalys med frågor om:

- **Rättssäkerhet:** Kan berörda förstå, ifrågasätta eller få beslut omprövade?
- **Likabehandling:** Riskerar lösningen att förstärka historiska skevheter?
- **Transparens:** Går det att förklara hur AI påverkar processen?
- **Informationssäkerhet:** Kan data exponeras, återanvändas eller lagras på oönskade sätt?
- **Förvaltningsbarhet:** Kan lösningen övervakas, uppdateras, avvecklas och granskas?
- **Demokratisk legitimitet:** Kan organisationen motivera användningen för medborgare, tillsynsorgan och politisk ledning?
- **Beroenden:** Skapas ett beroende till en modell, plattform eller leverantör som begränsar framtida handlingsfrihet?

Risk ska alltså inte ses som en bilaga efter lösningsvalet. Riskanalysen är en del av arkitekturdesignen.

### Ansvar måste designas

Ett vanligt misstag är att ansvar betraktas som en organisationsfråga som kan lösas efter den tekniska designen. I AI-arkitektur är ansvar en del av designen.

Om en AI-förmåga påverkar ett verksamhetsbeslut behöver arkitekturen kunna visa vem som ansvarar för olika delar av kedjan:

- vem som har godkänt syftet
- vem som ansvarar för data
- vem som ansvarar för modellens eller tjänstens användning
- vem som ansvarar för instruktioner, begränsningar och kontroller
- vem som ansvarar för mänsklig granskning
- vem som följer upp kvalitet, avvikelser och incidenter
- vem som kan pausa eller avveckla lösningen
- vem som svarar när beslut ifrågasätts

Detta är en vidareutveckling av begreppet ansvarskedja från kapitel 1. I praktiken behöver ansvarskedjan kopplas till både arkitekturdokumentation, förvaltningsmodell, informationssäkerhetsarbete, upphandling och verksamhetsprocesser.

Ansvar får inte stanna vid formuleringen "verksamheten ansvarar". Det är för vagt. För AI-förmågor behöver ansvar vara tillräckligt konkret för att kunna användas vid incidenter, revision, förändringar och förvaltningsbeslut.

### AI Act, NIST AI RMF och ISO/IEC 42001 som arkitekturstöd

Arkitekten bör inte förvandla varje AI-diskussion till en juridisk granskning, men behöver känna till centrala ramverk eftersom de påverkar arkitekturens styrning och dokumentationskrav.

EU:s AI Act bygger på en riskbaserad ansats och började gälla den 1 augusti 2024, med stegvis tillämpning. Förbjudna AI-praktiker och krav på AI-kunnighet började tillämpas från den 2 februari 2025. Regler för general-purpose AI-modeller började tillämpas från den 2 augusti 2025, medan stora delar av regelverket blir fullt tillämpliga den 2 augusti 2026, med vissa undantag och övergångsregler. Dessa datum och detaljer bör alltid verifieras mot officiella EU-källor vid publicering, eftersom vägledning och tillämpning utvecklas.

NIST AI Risk Management Framework är ett frivilligt ramverk som ofta används för att strukturera AI-risker. Ramverket betonar funktioner som govern, map, measure och manage. NIST har även publicerat en profil för generativ AI som hjälper organisationer identifiera särskilda risker med generativa AI-system.

ISO/IEC 42001:2023 är en standard för ledningssystem för AI. Den är relevant för arkitekter eftersom den ger ett språk för hur organisationer kan etablera, införa, underhålla och förbättra ett AI management system. För offentlig sektor kan den fungera som stöd för att koppla AI-styrning till befintliga ledningssystem för informationssäkerhet, kvalitet och risk.

Arkitektens poäng är inte att memorera regelverken. Poängen är att använda dem för att skapa bättre arkitekturfrågor:

- Vilken riskklass har användningen?
- Vilka skyldigheter kan följa av rollen som provider, deployer eller användande organisation?
- Vilken dokumentation krävs för att lösningen ska vara granskningsbar?
- Hur säkerställs AI literacy hos de roller som använder eller förvaltar systemet?
- Hur ska mänsklig kontroll utformas?
- Vilka kontroller krävs för generativ AI?
- Hur hanteras incidenter, avvikelser och förändringar över tid?

Källor att verifiera mot vid publicering:
- EU-kommissionens översikt över AI Act: https://digital-strategy.ec.europa.eu/en/policies/regulatory-framework-ai
- EU-kommissionens frågor och svar om AI literacy: https://digital-strategy.ec.europa.eu/en/faqs/ai-literacy-questions-answers
- NIST AI Risk Management Framework: https://www.nist.gov/itl/ai-risk-management-framework
- ISO/IEC 42001:2023: https://www.iso.org/standard/42001

### Beslutsnivåer: från princip till användningsfall

AI-beslut behöver fattas på flera nivåer. Om alla beslut hamnar i samma forum blir styrningen antingen för tung eller för svag.

En användbar uppdelning är:

1. **Principbeslut**
2. **Portföljbeslut**
3. **Arkitekturbeslut**
4. **Användningsfallsbeslut**
5. **Drift- och förändringsbeslut**

Principbeslut handlar om organisationens grundhållning. Exempel: AI får inte användas för självständigt beslutsfattande i vissa typer av ärenden. Eller: generativ AI får användas för sammanfattningar men inte som enda källa till beslutsskäl.

Portföljbeslut handlar om prioritering. Vilka AI-förmågor är värda att utveckla? Vilka ska stoppas? Vilka kräver gemensam plattform? Vilka bör ligga nära verksamheten?

Arkitekturbeslut handlar om lösningsmönster, integrationsprinciper, dataåtkomst, loggning, kontrollpunkter, modellval och förvaltningsansvar.

Användningsfallsbeslut handlar om den konkreta användningen: vilka användare, vilka data, vilken process, vilken risk, vilken mänsklig kontroll och vilken uppföljning.

Drift- och förändringsbeslut handlar om hur lösningen övervakas, ändras, uppdateras, pausas eller avvecklas.

IT-arkitekten behöver ofta bygga broar mellan dessa nivåer. Ett användningsfall som verkar lokalt kan skapa ett principiellt behov. Ett plattformsval kan förändra portföljens möjligheter. Ett driftproblem kan visa att målarkitekturen saknar tillräckliga kontroller.

### Beslut bör dokumenteras som spårbara arkitekturresonemang

För traditionell IT används ofta Architecture Decision Records, beslutsloggar eller motsvarande. För AI bör beslutsdokumentationen utökas.

Ett AI-relaterat arkitekturbeslut bör minst beskriva:

- beslutets syfte
- berörd verksamhetsförmåga
- vilken typ av AI-användning beslutet gäller
- vilka alternativ som övervägts
- varför valt alternativ bedöms lämpligt
- vilka risker som accepterats
- vilka risker som måste reduceras
- vilken data som används
- vilken informationsklassning som gäller
- vilken mänsklig kontroll som krävs
- hur lösningen ska följas upp
- vem som äger beslutet
- när beslutet ska omprövas

Det sista är särskilt viktigt. AI-beslut bör inte betraktas som permanenta. En modell kan förändras, ett regelverk kan förtydligas, användarbeteende kan ändras och organisationens riskaptit kan omprövas. Därför behöver arkitekturbeslut ha omprövningspunkter.

## Scenario eller beslutskontext

En myndighet vill införa en AI-baserad funktion som hjälper handläggare att sammanfatta inkomna handlingar och föreslå vilka delar som kan vara relevanta för fortsatt handläggning. Funktionen ska inte fatta beslut, men den kommer att påverka vad handläggaren ser först och hur snabbt ärendet kan beredas.

Vid första anblick kan detta beskrivas som ett produktivitetsverktyg. Men arkitekten bör se flera risk- och ansvarsfrågor.

Vilka handlingar skickas till AI-tjänsten? Innehåller de känsliga personuppgifter eller sekretessbelagd information? Sparas texten hos leverantören? Kan modellen hitta på innehåll som inte finns i handlingarna? Hur markeras osäkerhet? Kan handläggaren se källhänvisningar? Loggas vilka sammanfattningar som använts? Finns rutiner för att upptäcka systematiska fel? Vad händer om sammanfattningen missar något avgörande? Blir handläggaren mer benägen att lita på sammanfattningen än på originalhandlingarna?

Arkitektens rekommendation bör därför inte bara handla om vilken AI-tjänst som är bäst. Den bör handla om vilka kontroller som krävs för att tjänsten ska vara lämplig.

Ett möjligt arkitekturbeslut kan vara:

- AI-funktionen får användas som beredningsstöd, inte som beslutsstöd för slutligt myndighetsbeslut.
- Originalhandlingar ska alltid vara åtkomliga och vara den auktoritativa källan.
- Sammanfattningar ska tydligt märkas som AI-genererade.
- Sammanfattningen ska länka till källavsnitt där det är tekniskt möjligt.
- Användaren ska få instruktion om att kontrollera sakuppgifter mot originalhandling.
- Handlingar med viss informationsklassning får inte behandlas i den aktuella tjänsten.
- Loggning ska visa när AI-stöd använts och av vem.
- Kvalitet och avvikelser ska följas upp i förvaltning.
- Beslutet ska omprövas efter pilotperiod och vid större modell- eller leverantörsförändring.

Detta är arkitektur som ansvarstagande. Arkitekten formar inte bara teknisk integration, utan även gränserna för vad lösningen får göra.

## Strategiska vägval och arkitektöverväganden

### Vägval 1: AI som beslutsstöd eller automatiserat beslut

Det första vägvalet gäller AI-förmågans roll i beslutsprocessen.

AI som beslutsstöd innebär att AI hjälper människor att analysera, sammanfatta, prioritera, klassificera eller föreslå. Människan ansvarar fortfarande för beslutet och behöver ha faktisk möjlighet att förstå och avvika från AI:s förslag.

Automatiserat beslut innebär att systemet helt eller delvis avgör utfallet. I offentlig sektor är detta betydligt mer känsligt, särskilt när beslut påverkar enskildas rättigheter, skyldigheter, tillgång till service eller möjlighet till omprövning.

Arkitekten bör fråga:

- Är mänsklig granskning verklig eller bara formell?
- Kan användaren enkelt se varför AI föreslår något?
- Finns risk att AI-förslaget i praktiken blir normerande?
- Går det att mäta hur ofta människor avviker från AI?
- Finns processer för överklagande, omprövning eller rättelse?
- Är användningsfallet över huvud taget lämpligt för automatisering?

Ett vanligt fel är att kalla något beslutsstöd men designa det så att användaren i praktiken följer systemets förslag utan reflektion.

### Vägval 2: Central riskstyrning eller lokal innovationsfrihet

Organisationer behöver både gemensamma skyddsräcken och möjlighet till lokal utveckling. För mycket central kontroll kan stoppa nyttiga förbättringar. För lite central styrning kan skapa fragmenterad AI-användning, dolda risker och svåra leverantörsberoenden.

Arkitekten bör skilja mellan vad som måste styras centralt och vad som kan decentraliseras.

Centralt bör organisationen normalt styra:

- arkitekturprinciper
- informationsklassning
- godkända plattformar och integrationsmönster
- miniminivå för loggning och spårbarhet
- krav på riskbedömning
- krav på AI literacy
- upphandlingskrav och leverantörsvillkor
- process för incidenter och avvikelser

Lokalt kan organisationen ofta hantera:

- konkreta verksamhetsbehov
- prioritering av användningsfall inom givna ramar
- utformning av arbetsrutiner
- lokala effektmål
- förbättringsförslag och återkoppling

Vägvalet handlar alltså inte om centralisering eller decentralisering i allmänhet, utan om rätt ansvar på rätt nivå.

### Vägval 3: Riskacceptans eller riskreducering

Alla risker kan inte elimineras. Men risker måste vara synliga, ägda och motiverade.

Arkitekten bör skilja mellan:

- risker som kan accepteras
- risker som måste reduceras
- risker som måste överföras eller hanteras genom avtal
- risker som gör användningsfallet olämpligt
- risker som kräver politisk, juridisk eller ledningsmässig förankring

Riskacceptans är inte samma sak som att någon informellt säger "det där är nog okej". Riskacceptans bör dokumenteras, kopplas till rätt beslutsnivå och omprövas när förutsättningar förändras.

För offentlig sektor är det särskilt viktigt att riskacceptans inte bara baseras på intern effektivitet. En lösning kan vara effektiv och ändå olämplig om den minskar transparens, försvårar ansvarsutkrävande eller skapar oacceptabel påverkan på enskilda.

### Vägval 4: Förklarbarhet, transparens och praktisk begriplighet

Explainability används ofta som ett brett begrepp, men arkitekten behöver konkretisera vem som behöver förstå vad.

En utvecklare kan behöva teknisk insyn. En handläggare kan behöva förstå tillräckligt för att använda AI-förslaget kritiskt. En chef kan behöva förstå risk och ansvar. En medborgare kan behöva veta att AI har använts och hur det påverkat processen. En revisor kan behöva spårbar dokumentation.

Arkitekten bör därför inte nöja sig med frågan "är modellen förklarbar?". Bättre frågor är:

- För vem behöver lösningen vara begriplig?
- I vilket beslutsskede behövs begriplighet?
- Vilken information behöver sparas?
- Vilken information får inte exponeras?
- Vilken förklaring är tillräcklig för användaren?
- Vilken dokumentation krävs för revision?
- Hur hanteras fall där modellen inte kan förklaras på ett meningsfullt sätt?

Förklarbarhet är ett arkitekturellt krav, inte bara en modellfunktion.

## Vanliga felsatsningar

### Felsatsning: Riskanalys görs efter lösningsvalet

**Varför det händer:** Organisationen vill snabbt komma igång och betraktar risk som ett granskningsmoment i slutet.

**Hur arkitekten kan undvika det:** Gör riskanalysen till en del av designen. Kräv att risk, ansvar och kontroller beskrivs innan lösningsmönster låses.

### Felsatsning: Ansvar läggs på leverantören

**Varför det händer:** AI-tjänsten köps som en produkt och upplevs därför som leverantörens ansvar.

**Hur arkitekten kan undvika det:** Skilj mellan leverantörens ansvar för tjänsten och organisationens ansvar för användningen. Offentlig sektor kan inte outsourca sitt verksamhetsansvar.

### Felsatsning: Mänsklig kontroll blir symbolisk

**Varför det händer:** Processen säger att en människa granskar, men gränssnitt, tidsbrist eller organisatoriska incitament gör att AI-förslag sällan ifrågasätts.

**Hur arkitekten kan undvika det:** Designa för faktisk kontroll. Säkerställ att användaren ser källor, osäkerhet, alternativ och kan avvika utan onödigt motstånd.

### Felsatsning: Alla AI-användningar behandlas lika

**Varför det händer:** Organisationen inför en generell policy men saknar riskbaserad differentiering.

**Hur arkitekten kan undvika det:** Inför nivåer för AI-användning. Ett internt sammanfattningsstöd kräver andra kontroller än AI i myndighetsutövning, tillsyn eller resursfördelning.

### Felsatsning: Beslut saknar omprövningspunkt

**Varför det händer:** Arkitekturbeslut behandlas som engångsbeslut.

**Hur arkitekten kan undvika det:** Dokumentera när beslutet ska omprövas: efter pilot, vid ny datakälla, vid modellbyte, vid incident, vid ny lagtolkning eller vid ändrad användning.

## Arkitektens checklista

Använd checklistan när ett AI-relaterat arkitekturbeslut ska förberedas eller granskas.

### Syfte och användning

- Är syftet tydligt beskrivet?
- Är det tydligt vilken verksamhetsförmåga som påverkas?
- Är det tydligt om AI är arbetsverktyg, systemkomponent eller strategisk förmåga?
- Är det tydligt om AI stödjer, rekommenderar eller automatiserar beslut?
- Finns en gräns för vad AI inte får användas till?

### Risk och påverkan

- Är risk bedömd utifrån mer än teknisk funktion?
- Har rättssäkerhet, integritet, likabehandling och tillit bedömts?
- Har informationsklassning gjorts?
- Finns risk för automatiseringsbias?
- Finns risk för felaktiga, vilseledande eller ofullständiga AI-resultat?
- Finns risk för leverantörsberoende eller förlorad handlingsfrihet?

### Ansvar och styrning

- Finns en dokumenterad ansvarskedja?
- Är beslutets ägare tydlig?
- Är dataägarskap tydligt?
- Är förvaltningsansvar tydligt?
- Finns någon som kan stoppa eller pausa användningen?
- Är riskacceptans dokumenterad på rätt beslutsnivå?

### Transparens och spårbarhet

- Kan användare se när AI används?
- Kan berörda förstå hur AI påverkar processen?
- Finns loggning av användning och viktiga beslutspunkter?
- Finns dokumentation för revision och uppföljning?
- Är begränsningar och osäkerheter dokumenterade?

### Livscykel och uppföljning

- Finns mätetal för kvalitet och risk?
- Finns process för incidenter och avvikelser?
- Finns omprövningspunkt för beslutet?
- Finns plan för modell-, tjänste- eller leverantörsförändringar?
- Finns avvecklingsplan om lösningen inte längre är lämplig?

## Snabb sammanfattning

- AI-relaterade arkitekturbeslut måste beskriva inte bara vald lösning, utan även antaganden, risker, ansvar och kontroller.
- Risk i AI handlar inte bara om sannolikhet och konsekvens, utan även om rättssäkerhet, transparens, likabehandling, informationssäkerhet och förtroende.
- Ansvar måste designas in i arkitekturen. Det får inte lämnas som en oklar organisatorisk restfråga.
- AI Act, NIST AI RMF och ISO/IEC 42001 kan användas som stöd för bättre frågor, även när den juridiska detaljtolkningen görs av andra roller.
- Mänsklig kontroll behöver vara faktisk, inte symbolisk.
- AI-beslut bör ha omprövningspunkter eftersom modeller, regler, användning och riskbild förändras över tid.

## Reflektionsfrågor

1. Vilka AI-relaterade beslut i din organisation riskerar att betraktas som tekniska trots att de egentligen påverkar verksamhetsansvar?
2. Var i organisationen finns störst risk att mänsklig kontroll blir symbolisk snarare än verklig?
3. Vilka AI-användningar bör kräva central granskning, och vilka kan hanteras lokalt inom gemensamma ramar?
4. Hur dokumenteras riskacceptans i dag, och räcker det för AI-förmågor?
5. Vilka arkitekturbeslut borde redan nu få en tydlig omprövningspunkt?

## Nästa steg

Nästa kapitel fördjupar offentlig sektors särskilda kontext: styrning, juridik och tillit. Där flyttas perspektivet från det enskilda arkitekturbeslutet till den institutionella miljö där beslutet ska fungera. Det handlar om myndighetsutövning, offentlighet, sekretess, upphandling, informationsklassning, samverkan, demokratiskt ansvar och medborgarnas förtroende.
