# Kapitel 12: Målarkitektur för AI i offentlig sektor

## Varför detta kapitel finns

När en offentlig organisation har genomfört några AI-initiativ uppstår ofta samma fråga: hur ska allt hänga ihop?

En AI-assistent tas fram i en verksamhetsgren. En analyslösning byggs i en annan. En upphandling innehåller krav på generativ AI. En utvecklingsplattform får AI-stöd. Någon verksamhet vill använda en extern molntjänst. Informationssäkerhetsfunktionen ställer krav på klassning och loggning. Juridiken efterfrågar spårbarhet. Arkitekturfunktionen förväntas ge vägledning, men lösningarna rör sig snabbare än traditionella målarkitekturer.

Det är här målarkitektur blir viktig.

En målarkitektur för AI är inte en bild av en enda framtida plattform. Den är inte heller en lista över godkända verktyg. Den är en sammanhållen beskrivning av hur organisationen vill att AI-förmågor ska kunna uppstå, styras, integreras, skyddas, följas upp och avvecklas över tid. Den ska hjälpa organisationen att göra många enskilda vägval utan att varje initiativ behöver uppfinna sin egen arkitektur.

För offentlig sektor är detta särskilt viktigt. Offentliga organisationer behöver kombinera innovation med rättssäkerhet, transparens, informationshantering, säkerhet, upphandlingsbarhet, långsiktig förvaltning och demokratisk legitimitet. AI kan skapa stor nytta, men bara om organisationen har kontroll över de byggblock och beroenden som gör AI användbar i praktiken.

Det här kapitlet samlar därför tidigare delar av boken till en målarkitektur för AI. Det handlar inte om att föreskriva en viss teknisk produkt. Det handlar om att visa vilka arkitekturförmågor, lager, kontrollpunkter och styrningsbeslut som bör ingå när offentlig sektor bygger sin långsiktiga AI-förmåga.

## Lärandemål

Efter kapitlet ska läsaren kunna:

- beskriva vad en målarkitektur för AI bör omfatta i offentlig sektor
- skilja mellan referensarkitektur, målarkitektur och lösningsarkitektur
- resonera om centrala byggblock som policy layer, control plane, AI-gateway, dataförmågor, modellförmågor och utvärderingsförmågor
- identifiera vilka beslut som bör standardiseras centralt och vilka som bör lämnas till lokala lösningsarkitekturer
- förstå hur målarkitektur kan användas för att minska fragmentering, risk och leverantörsberoenden
- formulera arkitektöverväganden för långsiktig AI-styrning, förvaltning och vidareutveckling

## Innan vi börjar

Tidigare kapitel har etablerat flera komponenter som nu behöver samlas.

Kapitel 7 visade att AI kräver en stark dataarkitektur: informationsägarskap, metadata, datakvalitet, data lineage och semantisk tydlighet. Kapitel 8 behandlade integrationsarkitektur: hur AI-förmågor kopplas till verksamhetssystem, API:er, händelseflöden och användargränssnitt. Kapitel 9 visade att plattformar, modeller och ekosystem skapar strategiska beroenden. Kapitel 10 behandlade säkerhetsarkitektur: kontextpolicy, prompt injection, modellmissbruk, guardrails och stegvis autonomi. Kapitel 11 beskrev hur AI måste bli en förvaltningsbar förmåga, inte bara ett projekt.

Målarkitekturen är den sammanhållande ramen för allt detta.

För arkitekten innebär kapitlet ett skifte från enskilda lösningsfrågor till en helhetsbild: vilka gemensamma byggblock, principer och kontrollpunkter behöver organisationen för att många AI-initiativ ska kunna växa utan att skapa oöverblickbar risk?

## Huvudförklaring

### Målarkitektur är inte en slutbild

I traditionellt arkitekturarbete kan målarkitektur ibland uppfattas som ett framtida tillstånd som organisationen ska nå. För AI är det ofta mer användbart att se målarkitekturen som en styrande utvecklingsriktning. Den behöver beskriva vad som ska vara gemensamt, vad som ska vara lokalt, vilka kontroller som måste finnas och hur arkitekturen kan utvecklas när teknik, regler och verksamhetsbehov förändras.

AI-området förändras snabbt. Modeller, verktyg, leverantörer, standarder och användningsmönster kommer att fortsätta förändras. En målarkitektur som försöker låsa alla detaljer riskerar därför att bli inaktuell. Samtidigt kan organisationen inte lämna allt öppet. Offentlig sektor behöver tydlighet kring ansvar, data, säkerhet, uppföljning och förvaltning.

En målarkitektur för AI bör därför vara stabil i sina principer och anpassningsbar i sina implementationer.

Det innebär att den bör svara på frågor som:

- vilka typer av AI-förmågor organisationen vill möjliggöra
- vilka data- och informationskrav som gäller
- hur modeller och AI-tjänster får användas
- hur åtkomst, kontext, loggning och policy ska styras
- hur AI-output ska kvalitetssäkras och följas upp
- hur integrationer till verksamhetssystem ska ske
- hur ansvar och förvaltning ska placeras
- hur lösningar ska kunna bytas, begränsas eller avvecklas

Målarkitekturen blir därmed ett beslutsstöd, inte bara ett dokument.

### Referensarkitektur, målarkitektur och lösningsarkitektur

Tre begrepp behöver hållas isär.

En referensarkitektur är en generell återanvändbar modell. Den visar rekommenderade byggblock, relationer och principer för en viss typ av lösning. En referensarkitektur för AI kan exempelvis visa hur datakällor, AI-gateway, modellval, policykontroller, loggning och användargränssnitt bör samverka.

En målarkitektur beskriver organisationens önskade riktning. Den tar hänsyn till organisationens uppdrag, styrning, riskaptit, tekniska landskap, dataförmåga, leverantörsstrategi och regulatoriska krav. Den kan använda en eller flera referensarkitekturer, men är mer verksamhetsspecifik.

En lösningsarkitektur beskriver en konkret lösning. Den visar hur ett visst initiativ ska realiseras inom ramarna för målarkitekturen. Exempelvis kan en AI-assistent för intern kunskapssökning ha en lösningsarkitektur som använder organisationens gemensamma AI-gateway, dokumentindex, åtkomstkontroll, loggning och utvärderingsprocess.

För arkitekten är relationen mellan dessa nivåer central. Om referensarkitekturen är för generell hjälper den inte konkreta projekt. Om målarkitekturen är för detaljerad blir den snabbt ett hinder. Om lösningsarkitekturer får växa utan koppling till målarkitekturen skapas fragmentering.

Målet är en styrande men användbar arkitekturkedja: principer och referensmönster centralt, lösningsfrihet inom tydliga ramar lokalt.

### Lager i en målarkitektur för AI

En praktisk målarkitektur kan beskrivas i lager. Lagren är inte alltid separata tekniska produkter, men de hjälper arkitekten att se vilka förmågor som behövs.

#### Verksamhets- och förmågelager

Det översta lagret beskriver vilka verksamhetsförmågor AI ska stödja. Här kopplas AI inte till tekniska lösningar i första hand, utan till uppdrag, värdeflöden, beslutspunkter och nytta.

Frågan är inte “vilken AI-lösning ska vi införa?” utan “vilken förmåga behöver stärkas, och vilken roll bör AI spela där?”.

För offentlig sektor kan detta handla om exempelvis service, tillsyn, ärendeberedning, analys, kunskapsstöd, intern effektivisering eller utvecklingsstöd. Varje område har olika risknivå, ansvarskrav och tolerans för fel. Målarkitekturen bör därför beskriva hur AI-användning klassificeras utifrån verksamhetskritikalitet och beslutspåverkan.

#### Policy layer

Ett policy layer är den del av arkitekturen som omsätter styrning till praktiska regler. Det kan omfatta regler för informationsklassning, användarbehörighet, tillåtna datakällor, modellklasser, loggning, retention, outputhantering och krav på mänsklig granskning.

Policy layer behöver vara mer än en uppsättning dokument. Det bör kopplas till tekniska och processuella kontroller. Om organisationen exempelvis har en regel om att känslig information inte får skickas till vissa modeller behöver det finnas tekniska spärrar, integrationsmönster, vägledning och uppföljning som gör regeln användbar i praktiken.

För arkitekten är policy layer en bro mellan governance och lösningsdesign. Det gör styrningen implementerbar.

#### Control plane

Control plane är den sammanhållande förmåga som gör att organisationen kan styra, övervaka och administrera AI-användning. Begreppet används här som ett arkitekturmönster, inte som en specifik produkt.

Ett AI-relaterat control plane kan omfatta:

- katalog över godkända AI-förmågor, modeller och tjänster
- policyhantering för olika användningsfall och modellklasser
- åtkomststyrning och rollbaserade rättigheter
- loggning och spårbarhet
- mätning av användning, kvalitet och risk
- incident- och avvikelsehantering
- stöd för utvärdering och omprövning
- koppling till arkitekturforum och portföljstyrning

Control plane blir särskilt viktigt när AI används brett i organisationen. Utan en sådan förmåga riskerar organisationen att få många oberoende AI-lösningar där ingen kan se helheten.

#### Data- och kunskapslager

AI-förmågor är beroende av data och kunskap. I en målarkitektur behöver detta lager beskriva hur strukturerad data, dokument, metadata, begreppsmodeller, informationsklassning och datakvalitet hanteras.

För generativ AI blir kunskapslager ofta särskilt viktigt. Organisationen behöver kunna styra vilka dokument, register, handböcker, beslut, riktlinjer och ärendedata som får användas som kontext. Det kräver tydliga kopplingar till åtkomstkontroll, metadata och data lineage.

Det räcker inte att “koppla AI till dokument”. Målarkitekturen behöver ange hur dokumentens aktualitet, ägarskap, klassning och giltighet hanteras. Annars riskerar AI-förmågor att förstärka gamla fel, sammanblanda styrande och informella dokument eller ge svar som saknar tydlig grund.

#### Modell- och tjänstelager

Modell- och tjänstelagret beskriver vilka typer av AI-modeller och AI-tjänster organisationen kan använda. Det kan omfatta egna modeller, öppna modeller, kommersiella modeller, molnbaserade AI-tjänster och specialiserade analysmodeller.

Målarkitekturen bör inte nödvändigtvis låsa organisationen till en enda modellstrategi. Däremot bör den ange hur modellval ska göras. En offentlig organisation kan behöva olika modellklasser för olika risknivåer. En generell språkmodell kan vara lämplig för lågklassad intern textbearbetning men olämplig för beslutsnära användning utan starkare kontroller. En specialiserad modell kan vara lämplig för avgränsad analys men kräva tydligare drift- och utvärderingsansvar.

Här blir modellabstraktion viktigt. Genom att låta verksamhetslösningar gå via ett mellanlager, exempelvis en AI-gateway eller plattformstjänst, kan organisationen minska direkt beroende till en viss modell och införa gemensamma kontroller.

#### Integrations- och exponeringslager

AI skapar sällan värde isolerat. Den behöver integreras med användargränssnitt, ärendehanteringssystem, dokumenthantering, dataplattformar, API:er, meddelandeflöden och ibland automatiserade arbetsflöden.

Målarkitekturen bör beskriva hur AI-förmågor får exponeras mot användare och system. Det är stor skillnad mellan en AI-funktion som sammanfattar information för en handläggare och en AI-funktion som initierar en åtgärd i ett verksamhetssystem. Ju närmare AI kommer faktisk åtgärd, desto viktigare blir auktorisation, stegvis autonomi, loggning, testbarhet och möjlighet till återställning.

Integrationslagret behöver därför kopplas till beslutspåverkan och risk. Alla AI-integrationer bör inte behandlas lika.

#### Utvärderings- och lärandelager

AI-förmågor behöver följas upp över tid. Det gäller kvalitet, användarbeteende, fel, risk, nytta, bias, säkerhet, kostnad och förändrade förutsättningar. Målarkitekturen bör därför innehålla en förmåga för continuous evaluation.

Detta lager kan omfatta testdatamängder, granskningsprocesser, kvalitetsmått, användarfeedback, avvikelsehantering, red teaming, revision och beslut om omprövning. Det bör också kopplas till förvaltning: vem agerar när kvaliteten sjunker, när användare hittar riskmönster eller när leverantören ändrar en modell?

För offentlig sektor är detta viktigt eftersom AI-förmågor kan påverka tillit. En lösning som var acceptabel vid införandet kan bli olämplig när data, lagstiftning, verksamhetsprocesser eller modellbeteende förändras.

### Målarkitektur som styrinstrument

En bra målarkitektur används inte bara av arkitekter. Den ska stödja portföljstyrning, upphandling, informationssäkerhet, juridik, verksamhetsledning, utveckling och förvaltning.

Den kan användas för att:

- bedöma om ett AI-initiativ passar organisationens riktning
- identifiera vilka gemensamma byggblock som bör återanvändas
- avgöra vilka kontroller som krävs för ett visst användningsfall
- minska duplicerade plattformar och otydliga leverantörsberoenden
- ställa konsekventa krav i upphandling
- vägleda lösningsarkitekter i konkreta projekt
- skapa en gemensam vokabulär mellan teknik, juridik, säkerhet och verksamhet

Målarkitekturen behöver därför vara begriplig. Om den bara är en teknisk ritning blir den svår att använda strategiskt. Om den bara är principer blir den svår att omsätta i lösningar. Den behöver hålla ihop båda nivåerna.

## Scenario eller beslutskontext

En myndighet har under två år genomfört flera AI-initiativ. En verksamhetsavdelning använder en extern AI-tjänst för textbearbetning. IT-avdelningen testar AI-stöd för utvecklare. En annan avdelning vill införa en AI-assistent som söker i interna styrdokument. Samtidigt pågår ett projekt för automatiserad ärendeklassificering.

Varje initiativ har rimliga argument. Problemet är att de har olika leverantörer, olika loggningsnivåer, olika tolkningar av informationsklassning och olika sätt att hantera ansvar. Några lösningar har tydlig förvaltning. Andra drivs fortfarande som experiment.

Arkitekturfunktionen får i uppdrag att ta fram en målarkitektur för AI. Den bör inte stoppa all lokal innovation, men den måste skapa gemensamma ramar.

En möjlig slutsats är att organisationen behöver:

- gemensam klassning av AI-användningsfall
- ett policy layer som omsätter styrning till tekniska regler
- en AI-gateway för vissa typer av modellanrop
- gemensam loggning och uppföljning för AI-förmågor
- en modellkatalog med godkända modellklasser
- tydliga krav för när lokala lösningar får avvika
- en förvaltningsmodell med förmågeägare
- återkommande arkitekturgranskning av beslutsnära AI

Poängen är inte att allt måste centraliseras. Poängen är att organisationen behöver veta vad som måste vara gemensamt för att lokal utveckling ska vara säker, spårbar och förvaltningsbar.

## Strategiska vägval och arkitektöverväganden

### Central plattform eller federerad förmåga

Ett av de viktigaste vägvalen är hur centraliserad AI-arkitekturen ska vara.

En central plattform kan ge bättre kontroll, gemensamma säkerhetsmönster, tydligare kostnadsstyrning och enklare uppföljning. Den kan också göra det lättare att införa policy layer, loggning, modellabstraktion och gemensamma integrationer.

Samtidigt kan en alltför central lösning bli långsam, generisk och dåligt anpassad till olika verksamheters behov. Lokala verksamheter kan då hitta egna vägar vid sidan av arkitekturen.

En federerad modell kan ge större flexibilitet och närhet till verksamheten. Men den kräver starka gemensamma principer, standarder och kontrollpunkter. Annars blir resultatet fragmentering.

Arkitekten bör därför inte fråga “centraliserat eller decentraliserat?” utan “vad måste vara gemensamt, och vad kan variera?”. I offentlig sektor bör vanligtvis policy, informationsklassning, säkerhetskrav, loggning, modellklasser och uppföljningskrav vara gemensamma. Däremot kan användargränssnitt, verksamhetsflöden och vissa lösningsmönster variera.

### En modellstrategi eller flera modellklasser

En annan fråga är om organisationen ska standardisera på en modell eller använda flera modellklasser.

En begränsad modellflora kan förenkla styrning och kompetensuppbyggnad. Men den kan också skapa onödigt beroende och göra att samma modell används för för många syften. Flera modellklasser ger bättre anpassning till risk och behov, men kräver mer sofistikerad styrning.

Målarkitekturen bör därför beskriva modellklasser snarare än enbart modellnamn. Den kan ange vilka kontroller som krävs för exempelvis generella språkmodeller, specialiserade analysmodeller, beslutsstödsmodeller och modeller som används i utvecklingsarbete.

Det gör arkitekturen mindre sårbar för leverantörsbyten och teknikutveckling.

### AI-gateway eller direktintegration

Direktintegration till en modell eller AI-tjänst kan vara snabb och enkel. Men när många lösningar gör detta uppstår svårigheter med loggning, policy, åtkomst, kostnadsstyrning, modellbyte och incidenthantering.

En AI-gateway eller liknande mellanlager kan ge gemensam kontroll. Den kan hantera policy, modellval, filtrering, loggning, nyckelhantering, rate limits, kostnadsspårning och ibland utvärdering. Den kan också minska beroendet mellan verksamhetslösningar och enskilda modeller.

Nackdelen är att ett mellanlager kräver investering, kompetens och förvaltning. Det kan också bli en flaskhals om det utformas för tungt.

Arkitektövervägandet bör därför vara riskbaserat. Direktintegration kan vara rimlig för avgränsade lågriskfall. För bred, beslutsnära eller informationskänslig AI bör organisationen överväga gemensamma kontrollpunkter.

### Dokumenterad kontroll eller informell tillit

AI-lösningar kan upplevas användbara även när de saknar dokumenterad kontroll. Det är en risk. I offentlig sektor räcker det inte att användare tycker att en lösning “fungerar bra”. Organisationen behöver kunna visa varför den får användas, med vilken data, under vilka begränsningar, med vilken ansvarsfördelning och hur resultat följs upp.

Målarkitekturen bör därför skapa miniminivåer för dokumentation. Det kan handla om syfte, användargrupp, informationsklassning, modellklass, datakällor, kontroller, loggning, ansvar, utvärderingsmetod och avvecklingskriterier.

Detta är inte administration för sin egen skull. Det är en förutsättning för tillit och förvaltning.

### Stabilitet eller snabb innovation

Målarkitekturen måste balansera stabilitet och innovation. Om alla AI-initiativ måste vänta på fullständig målarkitektur riskerar organisationen att tappa tempo. Om allt får växa fram fritt riskerar organisationen att skapa teknisk och styrningsmässig skuld.

Ett praktiskt vägval är att låta målarkitekturen utvecklas iterativt. Börja med principer, klassning, minsta kontrollnivå och några gemensamma byggblock. Låt sedan verkliga initiativ pröva arkitekturen och ge återkoppling. På så sätt blir målarkitekturen ett levande styrinstrument snarare än ett stort dokument som ingen följer.

## Vanliga felsatsningar

- **Felsatsning:** Målarkitekturen blir en produktkarta.
  - **Varför det händer:** Organisationen vill snabbt veta vilka verktyg som är tillåtna.
  - **Hur arkitekten kan undvika det:** Beskriv först förmågor, principer, riskklasser och kontrollpunkter. Låt produktval vara en del av implementationen, inte hela arkitekturen.

- **Felsatsning:** All AI centraliseras för att skapa kontroll.
  - **Varför det händer:** Riskbilden upplevs som ny och svårhanterlig.
  - **Hur arkitekten kan undvika det:** Skilj mellan gemensam styrning och centraliserad leverans. Vissa kontroller bör vara gemensamma, men alla lösningar behöver inte byggas av samma team.

- **Felsatsning:** Lokala initiativ får växa utan koppling till målarkitekturen.
  - **Varför det händer:** Innovation sker snabbare än governance.
  - **Hur arkitekten kan undvika det:** Inför enkla arkitekturgrindar: klassning, datakrav, modellklass, loggning, ansvar och förvaltning innan pilot går vidare.

- **Felsatsning:** Målarkitekturen saknar förvaltningsperspektiv.
  - **Varför det händer:** Fokus ligger på införande, inte livscykel.
  - **Hur arkitekten kan undvika det:** Kräv att varje AI-förmåga har ägare, uppföljning, incidenthantering, ändringsprocess och avvecklingsstrategi.

- **Felsatsning:** Arkitekturen beskriver teknik men inte ansvar.
  - **Varför det händer:** AI behandlas som plattformsfråga.
  - **Hur arkitekten kan undvika det:** Koppla varje byggblock till ansvar: vem äger policy, data, modellval, kvalitet, risk, användning och beslut om fortsatt drift?

## Arkitektens checklista

- Finns en tydlig skillnad mellan referensarkitektur, målarkitektur och lösningsarkitektur?
- Beskriver målarkitekturen vilka AI-användningsfall organisationen vill möjliggöra?
- Finns en gemensam klassning av AI-förmågor utifrån risk, informationsklassning och beslutspåverkan?
- Finns ett policy layer som kan omsätta styrning till praktiska och tekniska regler?
- Finns ett control plane eller motsvarande för överblick, policy, loggning, åtkomst och uppföljning?
- Är data- och kunskapslager beskrivna med ägarskap, metadata, aktualitet, kvalitet och åtkomst?
- Finns modellklasser och principer för modellval snarare än bara en lista över verktyg?
- Finns mönster för AI-gateway, modellabstraktion eller annan gemensam kontrollpunkt där det behövs?
- Beskriver arkitekturen hur AI integreras med verksamhetssystem och hur autonomi begränsas?
- Finns krav på continuous evaluation och återkommande omprövning?
- Är förvaltningsansvar, förmågeägarskap och avvecklingsstrategi tydligt kopplade till målarkitekturen?
- Kan målarkitekturen användas i upphandling, portföljstyrning och arkitekturgranskning?

## Snabb sammanfattning

- En målarkitektur för AI är en styrande utvecklingsriktning, inte en statisk slutbild.
- Offentlig sektor behöver målarkitektur för att kombinera innovation med kontroll, rättssäkerhet, säkerhet och förvaltning.
- Målarkitekturen bör beskriva verksamhetsförmågor, policy layer, control plane, data- och kunskapslager, modell- och tjänstelager, integrationslager och utvärderingslager.
- Referensarkitektur, målarkitektur och lösningsarkitektur behöver hänga ihop men fylla olika funktioner.
- Centrala vägval handlar om centralisering, modellstrategi, AI-gateway, dokumenterad kontroll och balans mellan stabilitet och innovation.
- En användbar målarkitektur hjälper organisationen att fatta många enskilda AI-beslut konsekvent över tid.

## Reflektionsfrågor

1. Vilka AI-relaterade beslut i din organisation bör vara gemensamma, och vilka bör kunna fattas lokalt?
2. Finns det i dag en tydlig kedja från AI-principer till konkret lösningsarkitektur?
3. Vilka byggblock saknas för att organisationen ska kunna följa upp AI-användning över tid?
4. Var finns störst risk för fragmentering: data, modeller, integrationer, policy, leverantörer eller förvaltning?
5. Hur skulle en målarkitektur behöva formuleras för att vara användbar både för ledning, juridik, säkerhet och lösningsarkitekter?

## Nästa steg

Nästa kapitel flyttar fokus från organisationens målarkitektur till arkitektens egen kompetensprofil. När AI blir en del av verksamhetsförmågor, målarkitektur, säkerhet, data, upphandling och styrning förändras också vad det innebär att vara IT-arkitekt. Arkitekten behöver inte bli AI-forskare, men behöver utveckla förmågan att översätta mellan teknik, juridik, etik, risk, verksamhetsnytta och långsiktig arkitektur.
