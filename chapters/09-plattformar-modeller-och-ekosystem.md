# Kapitel 9: Plattformar, modeller och ekosystem

## Varför detta kapitel finns

När AI börjar användas strategiskt i offentlig sektor uppstår snabbt en ny typ av arkitekturfråga: ska organisationen själv bygga, köpa, dela, samverka eller konsumera AI-förmågor från externa plattformar?

Det är frestande att se frågan som ett vanligt teknikval. Vilken modell är bäst? Vilken molntjänst är billigast? Vilken leverantör har flest funktioner? Men för IT-arkitekten är frågan större än så. Valet av AI-plattform, modellstrategi och ekosystem påverkar organisationens handlingsfrihet, säkerhetsnivå, kostnadsstruktur, kompetensbehov, integrationsmönster, datastyrning och långsiktiga suveränitet.

I traditionell IT-arkitektur har plattformsval ofta handlat om driftmiljö, integrationsförmåga, livscykel, licenser och leverantörsberoenden. I AI-eran tillkommer ytterligare dimensioner. En AI-modell är inte bara en körbar komponent. Den har träningsdata, beteendemönster, begränsningar, hallucinationsrisker, versionsförändringar, policyfilter, användningsvillkor, regulatoriska konsekvenser och beroenden till både data och verksamhetsprocesser.

Det här kapitlet hjälper arkitekten att resonera strategiskt om plattformar, modeller och ekosystem. Fokus ligger inte på att välja en specifik produkt, utan på att förstå vilka vägval som måste göras, vilka konsekvenser de får och hur offentlig sektor kan undvika att låsa in sig i lösningar som är svåra att styra, granska eller lämna.

## Lärandemål

Efter kapitlet ska läsaren kunna:

- skilja mellan modell, AI-tjänst, AI-plattform och AI-ekosystem som arkitekturella nivåer
- resonera om strategiska vägval mellan egna modeller, köpta tjänster, öppna modeller och gemensamma plattformar
- identifiera risker kopplade till vendor lock-in, suveränitet, kostnad, livscykel och ansvar
- formulera arkitektöverväganden för modellval och plattformsstrategi i offentlig sektor
- bedöma när centralisering, federering eller lokal autonomi är lämpligast för AI-förmågor

## Innan vi börjar

Tidigare kapitel har etablerat att AI-förmågor inte bör betraktas som isolerade funktioner. Kapitel 7 betonade dataarkitekturens betydelse: utan styrda data, metadata, informationsägarskap och datakvalitet blir AI-förmågor svåra att lita på. Kapitel 8 visade hur AI måste integreras i användargränssnitt, processer, system och plattformar på ett kontrollerat sätt.

Det här kapitlet bygger vidare på dessa två perspektiv. Plattformar och modeller kan inte väljas oberoende av data och integration. En modellstrategi som kräver data organisationen inte får använda är inte genomförbar. En plattform som inte kan integreras med befintliga system skapar manuella sidoflöden. En AI-tjänst som inte kan loggas, kontrolleras eller avgränsas kan bli omöjlig att använda i känsliga processer.

Med andra ord: modellval är inte bara modellval. Det är ett arkitekturbeslut om styrning, ansvar och framtida rörelsefrihet.

## Huvudförklaring

### Fyra nivåer som ofta blandas ihop

I samtal om AI används orden modell, tjänst och plattform ofta som om de betydde samma sak. För arkitekturarbete behöver de separeras.

En **modell** är den beräknande komponent som kan generera, klassificera, sammanfatta, tolka eller förutsäga något. Det kan vara en foundation model, en mindre specialiserad modell, en språkmodell, en bildmodell eller en modell för prediktion.

En **AI-tjänst** är en paketerad funktion där modellen görs användbar genom API:er, gränssnitt, säkerhetsfunktioner, loggning, administrationsfunktioner och ibland inbyggda policyer. Tjänsten kan vara extern, intern, molnbaserad eller lokalt driftad.

En **AI-plattform** är den miljö där flera AI-tjänster, modeller, datakopplingar, utvecklarverktyg, policyer, utvärderingsfunktioner och driftförmågor hanteras samlat. Plattformen kan vara en kommersiell molnplattform, en intern plattform, en nationell eller sektorsgemensam plattform, eller en kombination.

Ett **AI-ekosystem** är den bredare miljö av leverantörer, standarder, öppna modeller, myndighetssamverkan, kompetensnätverk, regelverk, integrationsmönster och verktyg som organisationen blir beroende av.

Arkitekten behöver kunna röra sig mellan dessa nivåer. Ett beslut om modell kan låta litet men skapa plattformsberoende. Ett beslut om plattform kan påverka hela ekosystemet av leverantörer och kompetenser. Ett beslut om AI-ekosystem kan påverka organisationens förmåga att byta leverantör, dela lösningar eller samverka med andra offentliga aktörer.

### Foundation models och specialiserade modeller

En central fråga är om organisationen ska använda breda foundation models eller mer specialiserade modeller. En foundation model är tränad för att hantera många typer av uppgifter och kan anpassas till olika användningsfall genom promptning, kompletterande data, verktygsanrop eller finjustering. Den stora fördelen är flexibilitet. Samma grundmodell kan stödja sammanfattning, sökning, textgenerering, analysstöd och dialog.

Men flexibiliteten har ett pris. Bredare modeller är ofta svårare att förklara, dyrare att köra, mer beroende av leverantörens utveckling och mindre förutsägbara i specifika domäner. De kan vara kraftfulla men samtidigt överdimensionerade för enkla uppgifter.

Specialiserade modeller är smalare. De kan vara tränade eller konfigurerade för ett tydligt syfte, till exempel klassificering av ärenden, extraktion av information ur dokument eller prognoser inom en specifik verksamhetsprocess. De kan vara lättare att testa, avgränsa, kostnadsstyra och förvalta. Samtidigt kan de kräva mer förarbete, tydligare dataunderlag och separat livscykelhantering.

För offentlig sektor är frågan sällan om det ena är rätt och det andra fel. Det strategiska valet handlar snarare om vilka typer av förmågor som bör bygga på generella modeller och vilka som kräver smalare, mer kontrollerade lösningar.

### Köpa, bygga, använda öppet eller dela

Ett annat vägval gäller anskaffnings- och ägandemodell. Organisationen kan köpa en färdig AI-tjänst, använda en öppen modell, bygga egen AI-förmåga ovanpå en modell, eller samverka med andra aktörer kring gemensamma komponenter.

Att **köpa en färdig tjänst** kan ge snabb nytta och minska behovet av egen teknisk kompetens. Det passar ofta för standardiserade användningsfall, särskilt där informationsklassen är låg, integrationerna är enkla och kraven på specialanpassning begränsade. Nackdelen är beroende av leverantörens funktioner, prisförändringar, användningsvillkor, databehandling och utvecklingsplan.

Att **använda en öppen modell** kan ge större kontroll, bättre möjlighet till lokal drift och minskat beroende av en enskild leverantör. Det kan också stärka transparens och möjliggöra gemensam utveckling. Samtidigt innebär det inte automatiskt låg risk. Öppna modeller kräver drift, säkerhetsgranskning, utvärdering, kompetens, livscykelansvar och tydliga processer för uppdatering.

Att **bygga egen AI-förmåga** kan vara motiverat när verksamhetskraven är unika, informationsklassen hög, integrationerna komplexa eller behovet av kontroll mycket stort. Men egen utveckling bör inte romantiseras. Det kräver långsiktig finansiering, kompetens, testmiljöer, driftförmåga, modellutvärdering och förvaltning.

Att **dela eller samverka** kan vara särskilt relevant i offentlig sektor. Flera myndigheter, regioner eller kommuner kan ha liknande behov, liknande regelverk och liknande krav på tillit. Gemensamma komponenter, referensarkitekturer, ramavtal, utvärderingsmetoder eller plattformstjänster kan minska dubbelarbete. Samtidigt kräver samverkan tydlig styrning, ansvarsfördelning och beslutsförmåga.

### Plattformar som styrningsmekanism

En AI-plattform är inte bara ett tekniskt lager. Den är också en styrningsmekanism. Genom plattformen kan organisationen bestämma vilka modeller som får användas, vilka data som får kopplas in, hur användning loggas, vilka roller som får göra vad, vilka kostnader som uppstår och vilka riskkontroller som måste passeras.

Det innebär att plattformen blir en plats där arkitekturprinciper kan omsättas i praktiken. Om organisationen har en princip om dataminimering behöver plattformen stödja begränsning av kontext. Om organisationen har krav på revisionsbarhet behöver plattformen stödja loggning och spårbarhet. Om organisationen vill kunna byta modeller behöver plattformen stödja modellabstraktion och tydliga API-gränssnitt.

En svag plattform gör att AI-användning växer fram vid sidan av arkitekturen. Då uppstår lokala verktyg, manuella lösningar, okända datakopplingar och otydligt ansvar. En alltför centraliserad plattform kan däremot skapa köer, bromsa innovation och göra det svårt för verksamheten att lösa lokala problem.

Arkitektens uppgift är därför inte bara att förespråka centralisering eller decentralisering. Uppgiften är att designa balansen mellan gemensam kontroll och verksamhetsnära handlingsutrymme.

### Modellabstraktion och möjlighet till byte

Ett viktigt arkitekturmönster i AI-eran är att inte låta verksamhetsprocesser bli direkt beroende av en specifik modell eller leverantör. Om ett ärendeflöde, ett beslutsstöd eller en användarassistent byggs hårt mot en modell kan framtida modellbyte bli dyrt, riskfyllt och organisatoriskt svårt.

Modellabstraktion innebär att organisationen inför ett lager mellan verksamhetslösningen och modellen. Det kan vara en AI-gateway, ett internt API, en orkestreringstjänst eller ett policy layer. Syftet är att göra det möjligt att styra modellval, logga användning, lägga till kontroller och byta modell utan att skriva om hela verksamhetslösningen.

Det betyder inte att alla modeller kan bytas utan konsekvens. Olika modeller har olika beteende, kostnad, svarskvalitet, kontextfönster, säkerhetsfunktioner och begränsningar. Men utan abstrahering blir bytet ännu svårare. Arkitekten bör därför se modellbyte som en planerad livscykelförmåga, inte som en extraordinär migrationshändelse.

### Ekosystemberoenden och digital suveränitet

Offentlig sektor behöver ofta väga innovationshastighet mot kontroll. Stora kommersiella AI-ekosystem kan ge snabb tillgång till kraftfulla modeller, verktyg och utvecklingsmiljöer. De kan också erbjuda säkerhetsfunktioner, administrationsgränssnitt och integrationer som vore dyra att bygga själv.

Samtidigt kan beroendet bli omfattande. Det kan handla om dataplacering, supportkedjor, avtalsvillkor, modelluppdateringar, licensmodeller, API-förändringar, kompetensmarknad och möjlighet att granska hur tjänsten fungerar. För offentlig sektor blir detta kopplat till digital suveränitet: förmågan att fatta självständiga beslut om sina digitala förmågor, sin information och sin framtida arkitektur.

Digital suveränitet betyder inte nödvändigtvis att allt ska byggas och drivas själv. Det betyder att beroenden ska vara medvetna, styrda, dokumenterade och möjliga att ompröva. En organisation kan använda externa plattformar och ändå ha en suverän arkitektur om den har tydliga exit-strategier, öppna gränssnitt, datakontroll, avtalsmässiga skydd, kompetens och alternativa vägval.

## Scenario eller beslutskontext

En större offentlig organisation vill etablera en gemensam AI-förmåga för kunskapsstöd, dokumentanalys och intern effektivisering. Flera verksamhetsområden har redan börjat testa externa AI-tjänster. Några vill köpa färdiga assistenter från befintliga leverantörer. En central IT-funktion vill skapa en gemensam AI-plattform. Informationssäkerhetsfunktionen är orolig för dataläckage och otydlig loggning. Juridikfunktionen vill förstå hur personuppgifter och sekretessbelagd information hanteras. Verksamheten vill inte vänta i flera år på en perfekt plattform.

Arkitektens uppgift är att strukturera vägvalen. Det räcker inte att säga ja eller nej till AI. Organisationen behöver avgöra vilka användningsfall som kan använda standardtjänster, vilka som kräver intern plattform, vilka data som får användas, vilka modeller som är godkända, hur kostnader följs upp och hur framtida modellbyte ska hanteras.

Ett moget arkitektursvar kan vara att dela upp landskapet i flera zoner. En låg-risk-zon för allmän produktivitetsanvändning med tydliga användarregler. En kontrollerad zon för verksamhetsnära AI-förmågor med godkända datakällor, loggning och AI-gateway. En högkontrollzon för känsliga processer där modeller, drift, åtkomst och utvärdering styrs hårdare. På så sätt undviks både total blockering och okontrollerad spridning.

## Strategiska vägval och arkitektöverväganden

### Vägval 1: Central AI-plattform eller federerad AI-förmåga

En central AI-plattform kan ge enhetlig styrning, gemensamma kontroller, bättre kostnadsuppföljning och tydligare integrationsmönster. Den kan också minska dubbelarbete och skapa en gemensam bas för loggning, modellhantering och säkerhet.

Men centralisering kan bli en flaskhals. Om alla initiativ måste passera samma centrala funktion kan verksamheten uppleva att plattformen bromsar utveckling. Risken är då att lokala initiativ uppstår utanför styrningen.

En federerad modell innebär att organisationen har gemensamma principer, kontroller och plattformskomponenter, men låter verksamhetsnära team utveckla och använda AI inom ramarna. Detta passar ofta offentlig sektor där verksamheter har olika processer, informationsklasser och lokala behov men ändå behöver gemensam styrning.

Arkitekten bör fråga:
- Vilka AI-förmågor måste styras centralt?
- Vilka kan utvecklas lokalt inom gemensamma ramar?
- Vilka plattformskomponenter ska vara obligatoriska?
- Var går gränsen mellan innovation och oacceptabel variation?
- Hur upptäcks och hanteras AI-användning som sker utanför plattformen?

### Vägval 2: En modellstrategi eller flera modellklasser

Det kan verka effektivt att välja en standardmodell för allt. Det förenklar avtal, kompetens och integration. Men AI-användning kommer sannolikt att skilja sig mellan enkla interna assistenter, verksamhetskritiska beslutsstöd, dokumentanalys, klassificering och automation.

En mer robust strategi är att definiera modellklasser. Exempelvis:
- godkända generella modeller för låg-risk-användning
- kontrollerade modeller för verksamhetsnära stöd
- specialiserade modeller för definierade processer
- lokalt driftade eller särskilt granskade modeller för känsliga informationsmängder

Det gör arkitekturen mer komplex, men också mer realistisk. Olika risknivåer bör ha olika krav på kontroll, testning och livscykel.

Arkitekten bör tänka på att modellstrategin måste kopplas till informationsklassning, användningsfall, ansvar och processpåverkan. En modell som är acceptabel för intern textsammanfattning är inte automatiskt acceptabel för beslutsnära handläggningsstöd.

### Vägval 3: Proprietärt ekosystem eller öppnare arkitektur

Proprietära ekosystem kan ge snabb produktivitet, stark integration och tydlig leverantörsansvarighet. För många organisationer är det en realistisk väg, särskilt när AI-funktioner integreras i redan använda kontors-, samarbets- och verksamhetssystem.

Men proprietära lösningar kan också skapa lock-in. Dataformat, API:er, säkerhetsmodeller, promptverktyg, agenter, kunskapsbaser och arbetsflöden kan bli svåra att flytta. Kostnadsmodellen kan förändras när användningen ökar. Leverantörens modellbeteende kan ändras utan att organisationen fullt ut kontrollerar förändringen.

En öppnare arkitektur innebär att organisationen strävar efter standardiserade gränssnitt, separerade datalager, modellabstraktion och möjlighet att kombinera flera leverantörer eller öppna modeller. Det ger större handlingsfrihet men kräver mer egen arkitekturkapacitet.

Arkitekten bör inte föra en ideologisk diskussion om öppet eller proprietärt. Den viktiga frågan är vilka beroenden som är acceptabla, vilka som måste begränsas och vilka som måste vara reversibla.

### Vägval 4: Snabb nytta eller långsiktig förvaltningsbarhet

AI-tjänster kan ofta införas snabbt. Det är en styrka. Men snabbhet kan dölja framtida förvaltningsproblem. En pilot som saknar modelluppföljning, ägarskap, kostnadsstyrning, datakontroll och exit-strategi kan bli dyr när den skalas upp.

Långsiktig förvaltningsbarhet kräver att organisationen redan tidigt bestämmer:
- vem som äger AI-förmågan
- vem som godkänner modellbyte
- hur kvalitet och risk följs upp
- hur användare utbildas
- hur incidenter hanteras
- hur kostnader allokeras
- hur lösningen avvecklas eller ersätts

Arkitekten bör behandla AI-förmågor som levande komponenter. De behöver inte bara införas. De behöver övervakas, utvärderas, förbättras och ibland stängas ned.

### Vägval 5: Lokal autonomi eller sektorsgemensam samverkan

Många offentliga organisationer står inför liknande AI-frågor. Det talar för gemensamma lösningar, gemensamma principer och delade erfarenheter. Sektorsgemensam samverkan kan minska kostnad, skapa likformighet och stärka förhandlingsposition gentemot leverantörer.

Samtidigt kan gemensamma initiativ bli långsamma. Olika organisationer har olika mandat, data, juridiska förutsättningar och teknisk mognad. En gemensam lösning kan bli för generell eller för tung för lokala behov.

Arkitekten bör därför skilja mellan vad som bör vara gemensamt och vad som bör vara lokalt. Referensarkitekturer, kravmallar, riskmodeller, upphandlingsstöd, utvärderingsmetoder och standardiserade integrationsmönster lämpar sig ofta för samverkan. Specifika verksamhetsflöden och lokala prioriteringar kan behöva vara organisationens eget ansvar.

## Vanliga felsatsningar

- **Felsatsning:** Att välja AI-plattform utifrån demonstrationsvärde.
  - **Varför det händer:** Leverantörsdemonstrationer visar ofta imponerande funktioner i kontrollerade miljöer.
  - **Hur man undviker det:** Utvärdera plattformen mot informationsklassning, integration, loggning, livscykel, kostnadsstyrning, exit och revisionsbarhet.

- **Felsatsning:** Att blanda ihop modellprestanda med arkitekturlämplighet.
  - **Varför det händer:** Den modell som ger bäst svar i ett test kan uppfattas som det självklara valet.
  - **Hur man undviker det:** Bedöm även databehandling, avtal, förvaltningsförmåga, ansvar, säkerhet, driftsmodell och möjlighet till modellbyte.

- **Felsatsning:** Att skapa en central plattform utan verksamhetsförankring.
  - **Varför det händer:** Organisationen vill snabbt få kontroll över AI-användningen.
  - **Hur man undviker det:** Kombinera centrala kontroller med tydliga vägar för verksamhetsnära utveckling.

- **Felsatsning:** Att anta att öppen modell betyder låg risk.
  - **Varför det händer:** Öppenhet förväxlas med transparens, kvalitet och säkerhet.
  - **Hur man undviker det:** Granska modellens ursprung, licensvillkor, beteende, driftkrav, säkerhetsrisker och uppdateringsprocess.

- **Felsatsning:** Att sakna exit-strategi.
  - **Varför det händer:** Fokus ligger på införande, inte på framtida omprövning.
  - **Hur man undviker det:** Dokumentera hur data, promptar, konfigurationer, integrationer, utvärderingar och användningsmönster kan flyttas eller avvecklas.

## Checklista för arkitekter

Använd följande frågor när organisationen står inför val av AI-plattform, modell eller ekosystem:

1. Vilket användningsfall ska lösningen stödja, och vilken risknivå har det?
2. Vilken information behöver modellen få tillgång till?
3. Vilken informationsklass gäller för indata, kontext och output?
4. Är modellen eller tjänsten tänkt att vara rådgivande, styrande eller beslutsnära?
5. Vem ansvarar för modellens användning i verksamhetsprocessen?
6. Hur loggas användning, promptar, datakällor, svar och beslut?
7. Kan organisationen byta modell utan att bygga om hela lösningen?
8. Vilka leverantörsberoenden uppstår?
9. Hur påverkas kostnaden när användningen skalar upp?
10. Vilka delar av lösningen måste kunna granskas i efterhand?
11. Vilka kompetenser krävs för drift och förvaltning?
12. Finns en tydlig avvecklings- eller exit-plan?
13. Är plattformen förenlig med organisationens arkitekturprinciper?
14. Vilka delar bör vara gemensamma, och vilka bör vara lokala?
15. Har juridik, informationssäkerhet, verksamhet och arkitektur en gemensam bild av ansvaret?

## Snabb sammanfattning

- Plattformar, modeller och ekosystem är olika arkitekturnivåer och bör inte blandas ihop.
- Modellval påverkar styrning, integration, kostnad, ansvar och framtida handlingsfrihet.
- Offentlig sektor behöver väga snabb nytta mot kontroll, förvaltningsbarhet, suveränitet och revisionsbarhet.
- En AI-plattform bör ses som en styrningsmekanism, inte bara som teknik.
- Modellabstraktion och AI-gateways kan minska beroendet av enskilda modeller och leverantörer.
- Öppna modeller minskar inte automatiskt risk; de flyttar ofta ansvar till organisationen.
- En federerad plattformsstrategi kan kombinera gemensam styrning med verksamhetsnära utveckling.
- Exit-strategi, livscykelansvar och kostnadsstyrning bör finnas med från början.

## Reflektionsfrågor

1. Vilka AI-förmågor i din organisation bör styras centralt, och vilka kan utvecklas mer lokalt?
2. Vilka leverantörsberoenden är ni redan på väg att skapa genom pilotprojekt eller produktivitetsverktyg?
3. Har ni en tydlig modell för vilka typer av data som får användas i olika AI-plattformar?
4. Skulle ni kunna byta modell i en viktig AI-lösning utan att ändra verksamhetsprocessen?
5. Vilka frågor bör ställas i upphandling för att säkra långsiktig förvaltningsbarhet och exit?
6. Vilken del av AI-ekosystemet bör offentlig sektor äga, dela eller samverka kring?

## Nästa steg

Nästa kapitel går vidare till säkerhetsarkitektur för AI. Där flyttas fokus från plattforms- och modellval till de hot, kontroller och säkerhetsmönster som krävs när AI-förmågor blir en del av verksamhetskritiska miljöer.

Frågorna från detta kapitel följer med: vilken modell används, var körs den, vilka data får den tillgång till, hur styrs den och vem ansvarar när något går fel? Säkerhetsarkitektur för AI börjar inte med en separat kontrollista. Den börjar i de plattforms- och ekosystembeslut som organisationen redan har fattat.
