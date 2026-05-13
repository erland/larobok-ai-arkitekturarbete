# Kapitel 6: Offentlig sektor: styrning, juridik och tillit

## Varför detta kapitel finns

AI i offentlig sektor är inte bara en fråga om effektivisering. När AI används i myndigheter, regioner och kommuner påverkas relationen mellan invånare och det offentliga. Det gäller särskilt när AI används nära beslut, ärendehantering, tillsyn, vård, utbildning, socialtjänst, rättsväsende, samhällsplanering eller kritisk infrastruktur.

För IT-arkitekten innebär detta att arkitektur inte kan reduceras till tekniska komponenter, integrationer och plattformar. Arkitektur behöver också bära rättssäkerhet, transparens, informationssäkerhet, integritet, förvaltningsbarhet och demokratisk kontroll.

I tidigare kapitel har vi beskrivit AI som arbetsverktyg, systemkomponent och strategisk förändringskraft. Vi har också flyttat fokus från systemdesign till förmågedesign och diskuterat hur AI förändrar beslutsfattande, risk och ansvar. Detta kapitel placerar dessa frågor i offentlig sektors särskilda kontext.

Kapitlets kärnfråga är:

> Hur kan IT-arkitekten bidra till AI-lösningar som är användbara, lagliga, begripliga, styrbara och värda medborgarnas förtroende?

Det är en strategisk fråga. En AI-lösning som är tekniskt imponerande men svår att förklara, granska, upphandla, förvalta eller rätta kan bli en arkitekturell skuld. I offentlig sektor blir den skulden snabbt mer än teknisk. Den kan bli juridisk, organisatorisk och förtroendemässig.

## Lärandemål

Efter kapitlet ska läsaren kunna:

- förklara varför AI-arkitektur i offentlig sektor kräver särskild hänsyn till rättssäkerhet, transparens, integritet och tillit
- skilja mellan juridisk efterlevnad, arkitekturell styrbarhet och faktisk förtroendeskapande praktik
- identifiera centrala arkitekturfrågor kopplade till informationsklassning, personuppgifter, offentlighet, sekretess, upphandling och förvaltning
- resonera kring när AI bör centraliseras, decentraliseras eller begränsas inom en offentlig organisation
- formulera strategiska vägval för AI som balanserar innovation, kontroll, säkerhet och samhällsnytta

## Innan vi börjar

Detta kapitel bygger särskilt vidare på tre tidigare idéer:

- **AI-förmåga:** AI är inte bara en modell eller tjänst, utan en kombination av data, teknik, processer, ansvar, kontroller och uppföljning.
- **Förmågedesign:** AI bör bedömas utifrån vilken verksamhetsförmåga den ska stärka, inte bara vilket system den kan kopplas in i.
- **Ansvarskedja:** Det måste gå att förstå vem som ansvarar för syfte, data, beslutspåverkan, uppföljning och avveckling.

I offentlig sektor blir dessa tre idéer särskilt viktiga eftersom arkitekturbeslut ofta påverkar fler än den egna organisationen. Ett systemval kan påverka invånare, företag, andra myndigheter, leverantörer, kontrollorgan och framtida förvaltningsgenerationer.

Kapitlet är inte juridisk rådgivning. Regler och vägledningar förändras, särskilt inom AI-området. Vid publicering bör aktuella regler och myndighetsvägledningar verifieras mot officiella källor, exempelvis EU:s information om AI Act, Digg:s riktlinjer för generativ AI inom offentlig förvaltning och IMY:s vägledning om GDPR och AI.

## Huvudförklaring

### Offentlig sektor har ett annat uppdrag än marknaden

Privata organisationer kan ofta motivera AI genom konkurrenskraft, kostnadsreduktion, kundupplevelse eller intäktsökning. Offentlig sektor kan också behöva effektivisera, men uppdraget är bredare. Det offentliga ska leverera tjänster, fatta beslut och använda gemensamma resurser på ett sätt som är lagligt, sakligt, likvärdigt och förtroendeskapande.

Detta förändrar AI-arkitekturens utgångspunkt.

En AI-förmåga i offentlig sektor behöver bedömas utifrån frågor som:

- Stärker den rättssäkerheten eller riskerar den att göra beslut svårare att förstå?
- Bidrar den till likabehandling eller förstärker den skillnader mellan grupper?
- Gör den verksamheten mer transparent eller skapar den en ny svart låda?
- Kan den granskas i efterhand?
- Är ansvarsfördelningen begriplig för invånare, medarbetare, ledning och tillsyn?
- Kan lösningen förvaltas över tid utan att organisationen tappar kontroll?
- Är beroenden till leverantörer, molnplattformar och modellägare acceptabla?

Det betyder inte att offentlig sektor ska undvika AI. Det betyder att AI måste arkitektureras för offentlighetens villkor.

### Juridik är inte en separat fas

Ett vanligt misstag är att se juridik som en kontrollpunkt efter att lösningen redan är designad. I AI-sammanhang fungerar det dåligt. Juridiska förutsättningar påverkar själva arkitekturen.

Om en AI-förmåga behandlar personuppgifter påverkas datamodell, loggning, åtkomst, lagring, testdata, modellträning, förklarbarhet och radering. Om lösningen kan påverka myndighetsutövning påverkas beslutsflöde, dokumentation, mänsklig kontroll och spårbarhet. Om data omfattas av sekretess påverkas integrationsmönster, leverantörsval och driftmiljö. Om offentlighetsprincipen aktualiseras behöver organisationen förstå vilka handlingar, loggar och beslutsunderlag som uppstår.

IT-arkitektens uppgift är inte att ersätta juristen. Arkitektens uppgift är att göra juridiska krav arkitekturellt hanterbara.

Det kan innebära att:

- separera AI-stöd från formellt beslutsfattande
- dokumentera var mänsklig granskning sker
- designa för spårbarhet från input till rekommendation och beslut
- begränsa datatillgång enligt behovsprinciper
- möjliggöra radering, arkivering och gallring
- undvika att känslig information skickas till olämpliga tjänster
- bygga in kontrollpunkter där risknivån kräver det

Juridik blir därmed en designparameter, inte en efterhandsgranskning.

### Tillit byggs genom styrbarhet

Tillit till AI uppstår inte genom att organisationen säger att den använder AI ansvarsfullt. Tillit uppstår när system, processer och ansvar kan granskas, förstås och korrigeras.

För IT-arkitekten innebär detta att tillit behöver översättas till arkitekturförmågor:

- **Spårbarhet:** Det ska gå att följa hur data, modell, regler och mänskliga beslut samverkat.
- **Förklarbarhet:** Det ska gå att förklara resultat på en nivå som passar användare, beslutsfattare, granskare och berörda individer.
- **Kontrollerbarhet:** Det ska gå att stoppa, begränsa, justera eller avveckla en AI-förmåga.
- **Ansvarbarhet:** Det ska vara tydligt vem som äger syfte, data, modell, beslut, drift, uppföljning och risk.
- **Revisionsbarhet:** Det ska gå att granska både designbeslut och faktisk användning över tid.
- **Förvaltningsbarhet:** Lösningen ska kunna leva i organisationens verkliga styrning, budget, kompetens och leverantörsstruktur.

En lösning kan vara tekniskt korrekt men ändå skapa låg tillit om den är svår att förstå, svår att granska eller beroende av oklara leverantörsled.

### Informationsklassning måste komma före AI-experiment

AI-initierade projekt startar ofta med frågan: “Vad skulle vi kunna göra med den här modellen?” I offentlig sektor bör arkitekten ofta börja med en annan fråga: “Vilken information, vilket beslut och vilket ansvar rör vi oss med?”

Informationsklassning bör styra:

- vilken data som får användas
- var data får behandlas
- vilka AI-tjänster som får användas
- vilka leverantörer som kan vara aktuella
- vilka loggar som krävs
- vilka säkerhetskontroller som behövs
- om användningen över huvud taget är lämplig

För generativ AI blir detta särskilt viktigt eftersom användare kan klistra in text, dokument, ärenden, källkod, avtal eller personuppgifter i en tjänst utan att förstå konsekvenserna. Arkitekturen behöver därför omfatta både tekniska skydd och organisatoriska regler.

Det kan till exempel handla om:

- godkända AI-tjänster för olika informationsklasser
- tekniska spärrar mot vissa datatyper
- riktlinjer för vad som får matas in i externa tjänster
- utbildning och AI-literacy
- loggning av användning där det är proportionerligt
- uppföljning av avvikelser
- tydliga beslutsvägar för undantag

AI-användning utan informationsklassning riskerar att skapa en skuggarkitektur där dataflöden, ansvar och leverantörsberoenden blir osynliga.

### Offentlighet, sekretess och AI skapar nya arkitekturfrågor

Offentlig sektor hanterar information under flera samtidiga principer. Viss information ska kunna lämnas ut. Annan information ska skyddas. Vissa beslut ska dokumenteras. Vissa underlag ska bevaras eller gallras enligt regler. AI påverkar dessa frågor eftersom AI-lösningar kan skapa nya mellanprodukter: sammanfattningar, klassificeringar, promptar, svar, loggar, embeddings, beslutsförslag och analyskedjor.

Arkitekten behöver därför ställa frågor som:

- Är AI-genererat underlag en del av ärendeakten?
- Ska promptar och svar loggas?
- Hur länge ska AI-relaterade loggar sparas?
- Kan loggar innehålla sekretessbelagd information?
- Hur hanteras rättelse om AI-stöd har bidragit till felaktigt underlag?
- Vilka delar av en AI-process behöver kunna lämnas ut eller förklaras?
- Hur påverkas arkivering och gallring?

Detta är inte bara dokumenthantering. Det påverkar tekniska lösningar för loggning, datalagring, behörigheter, sökbarhet, export, åtkomstkontroll och livscykelhantering.

### Upphandling och sourcing är arkitekturfrågor

AI i offentlig sektor kommer ofta att införas genom kombinationer av egna plattformar, upphandlade tjänster, molnkomponenter, öppna modeller och leverantörsinbyggda funktioner. Därför blir sourcing en del av arkitekturen.

Arkitekten behöver bidra till krav som går bortom funktionalitet:

- dataplacering och databehandling
- underbiträden och leverantörskedjor
- möjlighet till revision
- transparens kring modell, träning, uppdateringar och begränsningar
- export av data, loggar och konfiguration
- incidentrapportering
- säkerhetskrav och åtkomstkontroller
- exit-strategi
- möjlighet att stänga av eller byta komponent
- konsekvenser när leverantören ändrar modellen eller tjänsten

Ett särskilt problem med AI-tjänster är att de kan förändras över tid utan att organisationen aktivt har beställt en förändring. En modell kan uppdateras, en funktion kan bete sig annorlunda, en prissättningsmodell kan ändras eller nya databehandlingsvillkor kan införas. För offentliga organisationer kan detta vara svårt att förena med krav på förutsebarhet, kontroll och dokumenterad ansvarsfördelning.

Arkitekturen behöver därför designas för föränderliga leverantörsberoenden. Det kan innebära abstraktionslager, tydliga kontrakt, begränsad koppling till enskilda modellfunktioner, testsviter, leverantörsoberoende logik och aktiv livscykelstyrning.

### AI kräver både central styrning och lokal förankring

En vanlig organisatorisk konflikt är om AI ska styras centralt eller användas fritt i verksamheten. Båda ytterligheterna är problematiska.

För stark centralisering kan göra AI långsamt, byråkratiskt och avskilt från verkliga verksamhetsbehov. För svag central styrning kan skapa okontrollerad användning, dubbla lösningar, säkerhetsrisker, juridiska avvikelser och fragmenterad förvaltning.

Offentlig sektor behöver ofta en federerad modell:

- centrala principer, riskramverk, godkända plattformar och gemensamma kontroller
- lokal förmåga att identifiera behov, designa användningsfall och följa upp nytta
- tydliga trösklar för när ett AI-initiativ kräver arkitekturgranskning, juridisk bedömning, informationssäkerhetsanalys eller ledningsbeslut
- gemensamma mönster som kan återanvändas mellan verksamheter

IT-arkitekten kan fungera som brygga mellan central styrning och lokal innovation. Det kräver förmåga att säga både “ja, men under dessa villkor” och “nej, inte i den här formen”.

### Tillit kräver även mänskliga processer

AI-arkitektur får inte enbart handla om systemkomponenter. I offentlig sektor är den mänskliga processen ofta avgörande.

Om AI används som beslutsstöd behöver det vara tydligt:

- vem som läser AI-stödet
- vad personen förväntas kontrollera
- vilka feltyper personen ska vara uppmärksam på
- när AI-stöd inte får användas
- hur avvikande bedömningar dokumenteras
- hur invånaren kan förstå eller ifrågasätta beslutet
- hur organisationen lär av fel

Utan detta kan “mänsklig kontroll” bli en formalitet. Arkitekten bör därför bedöma om människor i processen faktiskt har tid, kompetens, mandat och information för att utöva kontroll. Annars är kontrollen inte arkitekturellt verklig.

## Scenario eller beslutskontext

En offentlig organisation vill införa en generativ AI-assistent för handläggare. Assistenten ska sammanfatta inkomna handlingar, föreslå kompletteringsfrågor och hjälpa handläggaren att hitta relevanta interna riktlinjer.

Vid första anblick verkar detta vara ett lågriskinitiativ. AI:n fattar inga beslut. Handläggaren är fortfarande ansvarig. Lösningen kan spara tid och höja kvaliteten.

Men arkitekten ser flera frågor:

- Handlingarna kan innehålla personuppgifter, känsliga personuppgifter eller sekretessreglerad information.
- Sammanfattningar kan bli del av beslutsunderlaget.
- Felaktiga sammanfattningar kan påverka handläggarens bedömning.
- Promptar och svar kan behöva loggas för spårbarhet, men loggarna kan då också innehålla skyddsvärd information.
- Leverantörens modell kan uppdateras utan att organisationen kontrollerar exakt hur beteendet förändras.
- Handläggare kan börja använda assistenten på fler sätt än det ursprungliga syftet.
- Invånaren kan behöva få veta om AI har använts som stöd i processen.

Ett moget arkitekturbeslut skulle därför inte bara välja produkt. Det skulle definiera en styrd AI-förmåga:

- vilka ärendetyper som omfattas
- vilka informationsklasser som är tillåtna
- vilken data som får skickas till tjänsten
- om tjänsten får vara extern eller måste driftas i kontrollerad miljö
- hur svar ska presenteras som stöd, inte beslut
- vilka loggar som krävs och hur de skyddas
- hur handläggaren ska granska och dokumentera användning
- hur kvalitet mäts över tid
- hur fel rapporteras och leder till förbättring
- vem som får godkänna utökad användning

Beslutet handlar alltså inte om “AI-assistent eller inte”. Det handlar om vilken arkitektur för ansvar, information och kontroll som gör användningen möjlig.

## Strategiska vägval och arkitektöverväganden

### Vägval 1: AI som internt stöd eller del av myndighetsutövning

**Alternativ A: AI används som internt arbetsstöd.**  
Detta kan vara lämpligt för sammanfattning, sökning, språkstöd, intern analys och strukturering av information.

**Alternativ B: AI påverkar beslut, prioritering eller bedömning.**  
Detta kräver högre nivå av styrning, spårbarhet, riskanalys, juridisk bedömning och mänsklig kontroll.

**Arkitekten bör tänka på:**

- Var i processen påverkar AI faktiskt utfallet?
- Är AI:s roll tydlig för användaren?
- Kan människor upptäcka och korrigera fel?
- Finns det risk att AI-stödet får större auktoritet än avsett?
- Behöver lösningen klassas som högre risk enligt tillämpliga regelverk?

### Vägval 2: Central AI-plattform eller verksamhetsnära lösningar

**Central AI-plattform** ger bättre kontroll, återanvändning, säkerhet och gemensam styrning, men kan bli långsam och för generell.

**Verksamhetsnära lösningar** kan ge snabbare nytta och bättre passform, men riskerar fragmentering och otydliga beroenden.

**Arkitekten bör tänka på:**

- Vilka komponenter bör vara gemensamma: identitet, loggning, modellåtkomst, guardrails, informationsklassning, uppföljning?
- Vilka delar behöver verksamheten kunna anpassa?
- Finns en tydlig modell för undantag?
- Hur undviks skugg-AI?
- Hur återanvänds lärdomar mellan myndigheter, regioner, kommuner eller förvaltningar?

### Vägval 3: Extern AI-tjänst, egen drift eller hybrid

**Extern AI-tjänst** kan ge snabb tillgång till kapacitet, men kräver tydlig kontroll över data, avtal, leverantörskedja och förändringar.

**Egen drift eller kontrollerad miljö** kan ge större kontroll, men kräver kompetens, kostnad, infrastruktur och livscykelansvar.

**Hybridmodell** kan ge balans, men ökar komplexitet och kräver tydliga principer för vad som placeras var.

**Arkitekten bör tänka på:**

- Vilken informationsklass är aktuell?
- Vilken grad av leverantörsinsyn krävs?
- Är modellens beteende tillräckligt stabilt för användningsområdet?
- Hur hanteras exit?
- Vad händer om tjänsten förändras, blir dyrare eller inte längre uppfyller krav?

### Vägval 4: Full transparens, praktisk förklarbarhet eller kontrollerad insyn

Alla AI-lösningar kan inte förklaras på samma sätt. Offentlig sektor behöver därför avgöra vilken typ av förklarbarhet som krävs.

**Full teknisk transparens** kan vara svår eller omöjlig, särskilt vid externa foundation models.

**Praktisk förklarbarhet** innebär att användare och granskare kan förstå hur systemet används, vilka data som påverkar och vilka begränsningar som finns.

**Kontrollerad insyn** kan innebära att viss information finns tillgänglig för revision, tillsyn eller intern granskning även om den inte exponeras brett.

**Arkitekten bör tänka på:**

- Vem behöver förstå vad?
- Behövs förklaringar för invånare, handläggare, systemägare, jurister, revisorer eller tillsyn?
- Vad behöver dokumenteras vid varje användning?
- Vilka begränsningar måste kommuniceras?
- Är det bättre att välja enklare teknik för att uppnå begriplighet?

### Vägval 5: Tillåta experiment brett eller införa kontrollerade sandlådor

AI-utveckling gynnas av experiment. Offentlig sektor kan dock inte låta experiment ske okontrollerat med skyddsvärd information eller nära skarpa beslut.

**Bred experimentering** kan öka lärande men kräver tydliga ramar.

**Kontrollerade sandlådor** ger säkrare utforskning men kan uppfattas som tröga.

**Arkitekten bör tänka på:**

- Vilken data får användas i experiment?
- Hur anonymiseras, syntetiseras eller avgränsas data?
- När övergår ett experiment till ett system som måste förvaltas?
- Vilka beslutspunkter finns mellan idé, pilot, produktion och avveckling?
- Hur dokumenteras lärdomar så att de inte försvinner?

## Vanliga felsatsningar

- **Felsatsning:** Juridik hanteras som en slutgranskning.
  - **Varför det händer:** Organisationen vill komma igång snabbt och antar att lösningen kan justeras senare.
  - **Hur arkitekten kan undvika det:** Gör juridiska, informationssäkerhetsmässiga och förvaltningsmässiga krav till arkitekturdrivare från början.

- **Felsatsning:** AI beskrivs som “bara ett stöd” utan att faktisk påverkan analyseras.
  - **Varför det händer:** Formellt fattar människan beslutet, men i praktiken kan AI-stödet forma bedömningen.
  - **Hur arkitekten kan undvika det:** Kartlägg beslutspunkter, påverkan, beroenden och mänsklig kontroll som del av processarkitekturen.

- **Felsatsning:** Organisationen inför generativ AI utan informationsklassning.
  - **Varför det händer:** Verktygen är lättillgängliga och nyttan upplevs omedelbar.
  - **Hur arkitekten kan undvika det:** Koppla AI-användning till informationsklass, godkända verktyg, användningsregler och tekniska skydd.

- **Felsatsning:** Upphandling fokuserar på funktioner men inte på kontroll.
  - **Varför det händer:** AI-marknaden säljs ofta genom demonstrationer och produktivitetslöften.
  - **Hur arkitekten kan undvika det:** Ställ arkitekturkrav på data, loggar, revision, modellförändringar, export, incidenter och exit.

- **Felsatsning:** Central styrning kväver all lokal innovation.
  - **Varför det händer:** Riskerna är verkliga och organisationen svarar med hård kontroll.
  - **Hur arkitekten kan undvika det:** Skapa federerade modeller där centrala skydd kombineras med verksamhetsnära utforskning.

- **Felsatsning:** Tillit behandlas som kommunikation i stället för arkitektur.
  - **Varför det händer:** Organisationen antar att förtroende kan skapas med riktlinjer och budskap.
  - **Hur arkitekten kan undvika det:** Bygg in spårbarhet, förklarbarhet, ansvar, revision och korrigerbarhet i lösningen.

## Arkitektens checklista

Använd checklistan när en offentlig organisation överväger, upphandlar eller inför AI.

### 1. Syfte och samhällsnytta

- Är syftet tydligt formulerat?
- Vilken offentlig nytta ska AI-förmågan skapa?
- Finns ett faktiskt problem eller används AI för att tekniken är tillgänglig?
- Är nyttan proportionerlig i förhållande till risk, kostnad och komplexitet?
- Finns alternativ utan AI som bör prövas först?

### 2. Rättslig och organisatorisk grund

- Vilka lagar, regler, interna styrdokument och myndighetsvägledningar påverkar användningen?
- Är ansvarig verksamhetsägare utsedd?
- Är personuppgiftsansvar, informationsägarskap och systemägarskap tydliga?
- Finns behov av konsekvensbedömning, riskklassning eller särskilt beslut?
- Har jurist, informationssäkerhet, dataskydd och arkitektur involverats tidigt?

### 3. Information och data

- Vilken informationsklass har data som används?
- Förekommer personuppgifter, känsliga personuppgifter eller sekretess?
- Var behandlas data?
- Används data för träning, förbättring eller endast inferens?
- Finns data lineage och spårbarhet?
- Är loggning förenlig med sekretess, integritet, arkivering och gallring?

### 4. Beslut och mänsklig kontroll

- Påverkar AI prioritering, bedömning, rekommendation eller beslut?
- Är AI:s roll tydlig för användaren?
- Har människan faktisk möjlighet att granska och avvika från AI-stödet?
- Dokumenteras avvikelser och fel?
- Finns utbildning för användare?
- Finns rutiner för när AI inte får användas?

### 5. Transparens och förklarbarhet

- Vem behöver förstå AI-förmågan och på vilken nivå?
- Kan organisationen förklara syfte, datakällor, begränsningar och ansvar?
- Finns dokumentation för intern granskning och extern tillsyn?
- Kan invånare eller berörda parter få begriplig information?
- Är lösningen för komplex för den beslutskontext där den ska användas?

### 6. Leverantör och sourcing

- Vilka leverantörer och underleverantörer behandlar data?
- Kan organisationen granska leverantörens kontroller?
- Finns krav på modellförändringar, versionshantering och incidentrapportering?
- Kan data, loggar och konfiguration exporteras?
- Finns exit-strategi?
- Hur påverkas lösningen av ändrade villkor, priser eller modellbeteende?

### 7. Förvaltning och livscykel

- Vem följer upp kvalitet, fel, bias, kostnad och användning?
- Hur ofta ska lösningen omprövas?
- Finns process för avveckling?
- Finns budget och kompetens för långsiktig förvaltning?
- Är AI-förmågan integrerad i organisationens ordinarie arkitekturstyrning?
- Finns indikatorer för när användningen ska pausas eller begränsas?

## Snabb sammanfattning

- Offentlig sektor behöver AI-arkitektur som balanserar nytta, rättssäkerhet, transparens, integritet och tillit.
- Juridik, informationssäkerhet och förvaltning är inte efterhandsfrågor utan arkitekturdrivare.
- Tillit skapas genom styrbarhet: spårbarhet, förklarbarhet, kontrollerbarhet, ansvarbarhet, revisionsbarhet och förvaltningsbarhet.
- Informationsklassning bör styra vilka AI-tjänster, dataflöden och leverantörsmodeller som är möjliga.
- AI kan skapa nya informationsobjekt som promptar, svar, sammanfattningar, embeddings och loggar. Dessa behöver hanteras i arkitekturen.
- Upphandling av AI är ett arkitekturbeslut eftersom leverantörsberoenden, modellförändringar och datahantering påverkar långsiktig kontroll.
- Offentlig sektor behöver ofta federerad AI-styrning: centrala principer och kontroller kombinerat med verksamhetsnära användning.
- Mänsklig kontroll måste vara verklig, inte bara formell.

## Reflektionsfrågor

1. Vilka AI-användningar i din organisation skulle kräva striktare styrning än de först verkar göra?
2. Var finns störst risk för skugg-AI: i handläggning, analys, dokumentation, utveckling eller ledningsstöd?
3. Vilka informationsklasser bör aldrig hanteras i externa AI-tjänster utan särskilt beslut?
4. Finns det processer där AI-stöd formellt är rådgivande men i praktiken sannolikt styr utfallet?
5. Vilka krav saknas ofta i upphandlingar för att säkerställa långsiktig arkitekturell kontroll?
6. Vilken typ av förklarbarhet behöver invånare, handläggare, chefer, revisorer och tillsynsmyndigheter?
7. Hur kan organisationen möjliggöra experiment utan att skapa okontrollerade dataflöden eller ansvarsglapp?

## Nästa steg

Detta kapitel har placerat AI-arkitektur i offentlig sektors styrnings-, juridik- och tillitskontext. Nästa kapitel går in i en av de mest avgörande byggstenarna för all AI: dataarkitektur.

Där flyttas fokus från styrningsvillkor till informationsförutsättningar. Frågan blir hur data behöver organiseras, ägas, kvalitetssäkras, beskrivas och göras tillgänglig för att AI-förmågor ska bli möjliga utan att skapa okontrollerad risk.

## Källor och verifieringspunkter

Följande källor bör verifieras mot aktuella versioner vid publicering:

- EU-kommissionens information om AI Act och dess riskbaserade struktur samt införande i etapper: https://digital-strategy.ec.europa.eu/en/policies/regulatory-framework-ai
- Digg:s riktlinjer för generativ AI inom offentlig förvaltning, framtagna tillsammans med IMY: https://www.digg.se/ai-for-offentlig-forvaltning/riktlinjer-for-generativ-ai
- IMY:s vägledning om GDPR och AI: https://www.imy.se/verksamhet/dataskydd/innovationsportalen/vagledning-om-gdpr-och-ai/
- IMY:s information om tillsyn och vägledning 2026, inklusive användning av AI i offentlig sektor: https://www.imy.se/om-oss/vart-uppdrag/vagledning-och-tillsyn-2026/
