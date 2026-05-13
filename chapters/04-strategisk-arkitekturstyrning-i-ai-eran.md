# Kapitel 4: Strategisk arkitekturstyrning i AI-eran

## Varför detta kapitel finns

AI gör arkitekturstyrning både viktigare och svårare. Viktigare, eftersom AI kan påverka hur beslut fattas, hur information används, hur tjänster utformas och hur ansvar fördelas mellan människa, organisation och teknik. Svårare, eftersom AI-förmågor ofta växer fram i gränslandet mellan verksamhetsutveckling, datahantering, informationssäkerhet, juridik, upphandling och teknisk plattformsutveckling.

Traditionell arkitekturstyrning har ofta utgått från relativt stabila system, tydliga livscykler och beslut som går att dokumentera i målarkitekturer, principer, standarder och referensarkitekturer. AI förändrar detta. Modeller uppdateras, dataförutsättningar förändras, leverantörers funktioner utvecklas löpande och användningen kan skifta från ett begränsat pilotfall till bred verksamhetskritisk användning på kort tid.

För IT-arkitekten innebär det att styrningen behöver flytta från att enbart godkänna lösningar till att etablera spelregler för hur AI får utforskas, införas, skalas, övervakas och avvecklas. Arkitekturstyrning blir mindre av en kontrollpunkt i slutet av ett projekt och mer av ett kontinuerligt system av principer, beslutsforum, riskbedömningar, mätetal och återkoppling.

I offentlig sektor är detta särskilt centralt. AI-förmågor behöver inte bara vara tekniskt fungerande. De behöver vara rättssäkra, spårbara, förvaltningsbara, säkra, begripliga och förenliga med offentlighetens krav på insyn och ansvar. En lösning som ger god intern effektivitet men samtidigt skapar otydligt ansvar, bristande insyn eller beroenden som inte kan kontrolleras är inte nödvändigtvis en bra arkitektur.

Detta kapitel behandlar hur strategisk arkitekturstyrning behöver utvecklas i AI-eran. Fokus ligger på principer, målarkitektur, styrmodell och de vägval IT-arkitekten behöver lyfta innan AI blir en osynlig del av organisationens digitala infrastruktur.

## Lärandemål

Efter kapitlet ska läsaren kunna:

- beskriva varför AI kräver en mer kontinuerlig och principbaserad arkitekturstyrning
- formulera arkitekturprinciper som stödjer ansvarsfull och förvaltningsbar AI-användning
- skilja mellan central styrning, federerad styrning och lokal frihet i AI-relaterade initiativ
- identifiera vilka beslut som bör tas på strategisk, taktisk och lösningsnära nivå
- bedöma hur målarkitektur, referensarkitektur och styrforum behöver anpassas för AI
- resonera om hur offentlig sektor kan balansera innovation, kontroll, rättssäkerhet och långsiktig handlingsfrihet

## Innan vi börjar

De tidigare kapitlen har etablerat tre viktiga utgångspunkter.

För det första förändrar AI IT-arkitektens uppdrag. Arkitekten behöver förstå AI som arbetsverktyg, systemkomponent och strategisk förändringskraft. Det innebär att AI inte kan hanteras som en isolerad teknikfråga.

För det andra behöver arkitekturarbetet röra sig från systemdesign till förmågedesign. Det räcker inte att fråga vilket system som ska byggas eller köpas. Arkitekten behöver fråga vilken verksamhetsförmåga som ska stärkas, vilka beslut som påverkas, vilka dataflöden som krävs och hur ansvar ska fördelas.

För det tredje blir AI en medskapare i arkitektens eget arbete. Det gör styrning nödvändig även för arkitekturprocessen, inte bara för de lösningar som processen producerar.

I detta kapitel tar vi nästa steg: hur organisationen bör styra AI-arkitektur på strategisk nivå.

## Huvudförklaring

### Arkitekturstyrning som spelregler för förändring

Arkitekturstyrning missförstås ibland som en broms. I praktiken bör den fungera som ett sätt att skapa tydliga spelregler för förändring. När spelreglerna är otydliga uppstår två vanliga problem.

Det första problemet är överkontroll. Varje AI-initiativ måste passera tunga forum, vilket gör att verksamheten söker informella vägar runt styrningen. Resultatet blir skugg-AI, lokala experiment utan dokumentation och en växande portfölj av lösningar som ingen har helhetsansvar för.

Det andra problemet är understyrning. Organisationen uppmuntrar innovation men saknar principer för dataanvändning, säkerhet, leverantörsval, uppföljning, transparens och ansvar. Resultatet blir pilotprojekt som är snabba att starta men svåra att skala eller förvalta.

Strategisk arkitekturstyrning i AI-eran behöver därför skapa en balans. Den ska göra det lätt att göra rätt och svårt att oavsiktligt bygga in risker. Den ska ge verksamheten utrymme att utforska, men inom tydliga ramar.

### Från projektgrindar till kontinuerlig styrning

Många organisationer styr arkitektur genom projektgrindar: beslut före upphandling, beslut före utveckling, beslut före produktionssättning. Den modellen kan fortfarande behövas, men den är otillräcklig för AI.

AI-lösningar förändras över tid. En språkmodell kan få nya funktioner. Ett API kan ändra beteende. Datamängder kan uppdateras. En lokal användning kan spridas till fler verksamhetsområden. En lösning som först bara sammanfattar text kan senare börja föreslå beslut, prioritera ärenden eller generera underlag som används i myndighetsutövning.

Det innebär att arkitekturbeslut inte är färdiga vid införandet. De behöver följas upp under hela livscykeln. Arkitekten behöver därför bidra till styrning som omfattar:

- idé och utforskning
- risk- och nyttobedömning
- data- och informationsklassning
- lösningsdesign
- upphandling eller val av plattform
- införande
- användning och uppföljning
- förändring av modell, data eller process
- avveckling eller ersättning

Detta är en förskjutning från arkitektur som godkännande till arkitektur som kontinuerlig kontroll och lärande.

### Arkitekturprinciper för AI

Arkitekturprinciper är inte slogans. De är beslutsregler. En bra princip hjälper organisationen att välja mellan alternativ när mål står i konflikt med varandra.

I AI-eran behöver principerna ofta täcka fler dimensioner än traditionell teknisk arkitektur. De behöver omfatta verksamhetsnytta, rättssäkerhet, data, säkerhet, transparens, mänskligt ansvar, leverantörsberoenden och förvaltningsbarhet.

Exempel på principer kan vara:

1. **AI ska förstärka ansvariga verksamhetsprocesser, inte ersätta odefinierat ansvar.**  
   Innan AI används i en process ska det vara tydligt vem som ansvarar för beslut, felhantering, uppföljning och ändring.

2. **AI-förmågor ska bygga på klassad och ändamålsenligt hanterad information.**  
   Ingen AI-lösning ska införas utan att informationsklassning, åtkomst, datakvalitet och dataägarskap är bedömda.

3. **AI-beslut ska vara spårbara i proportion till konsekvensen för individ, verksamhet och samhälle.**  
   Ju större påverkan, desto högre krav på dokumentation, förklaring, loggning och möjlighet till granskning.

4. **AI-plattformar ska väljas med exit-strategi och långsiktig handlingsfrihet.**  
   Leverantörsval ska bedömas utifrån beroenden, dataflyttbarhet, avtalsvillkor, kostnadsutveckling och möjlighet att byta komponenter.

5. **AI ska införas som förvaltningsbar förmåga, inte som engångspilot.**  
   Varje lösning som går mot verklig användning ska ha tydligt ägarskap, finansiering, uppföljning och livscykelhantering.

6. **Mänsklig användning av AI ska vara kompetent, synlig och styrd.**  
   Det ska framgå när AI används, vad användaren får göra med resultatet och vilken granskning som krävs.

Sådana principer bör inte vara för många. Om organisationen har tjugo AI-principer finns risken att ingen används i verkliga beslut. Ett mindre antal skarpa principer, kopplade till beslutspunkter och ansvar, är ofta mer verkningsfullt.

### Målarkitektur som riktning, inte ritning

En målarkitektur för AI bör inte försöka beskriva varje framtida lösning i detalj. AI-området förändras för snabbt för en sådan statisk ritning. Däremot behöver målarkitekturen beskriva vilka förmågor, kontrollpunkter och byggblock organisationen vill etablera.

En strategisk målarkitektur kan till exempel beskriva:

- gemensamma principer för AI-användning
- klassificering av AI-användningsfall efter risk och påverkan
- godkända plattformar och integrationsmönster
- krav på datahantering, metadata och spårbarhet
- säkerhetskontroller och åtkomstmodeller
- loggning, övervakning och incidenthantering
- ansvarsfördelning mellan verksamhet, IT, informationssäkerhet, juridik och dataskydd
- modell för upphandling och leverantörsstyrning
- krav på dokumentation, uppföljning och avveckling

Målarkitekturen bör ge tillräcklig riktning för att undvika spretig utveckling, men inte låsa organisationen vid en specifik leverantör eller teknisk lösning för tidigt.

### Referensarkitektur som återanvändbart beslutsstöd

Där målarkitekturen beskriver riktning kan referensarkitekturen ge återanvändbara mönster. En referensarkitektur för AI i offentlig sektor kan till exempel visa hur en AI-förmåga bör kopplas till identitetshantering, informationsklassning, loggning, datakällor, integrationsplattform, användargränssnitt och förvaltningsprocesser.

Värdet med en referensarkitektur är inte att alla lösningar blir identiska. Värdet är att viktiga frågor inte glöms bort varje gång. Den gör det möjligt att fråga:

- Var finns mänsklig granskning?
- Var sker informationsklassning?
- Var loggas användning?
- Vilka datakällor används?
- Var hanteras promptar, instruktioner eller modellkonfiguration?
- Hur isoleras känslig information?
- Hur kan lösningen stängas av?
- Hur hanteras avvikelser och fel?
- Vilka beroenden finns till externa leverantörer?

Referensarkitekturen blir därmed ett verktyg för både kvalitet, styrning och hastighet.

### Styrmodell: central, federerad eller lokal?

En av de viktigaste frågorna är hur AI-styrning ska organiseras. Det finns sällan ett enkelt svar. Tre grundmönster återkommer.

**Central styrning** innebär att en central funktion sätter standarder, godkänner plattformar, bedömer risker och kontrollerar användning. Fördelen är konsekvens, samordning och bättre kontroll över risker. Nackdelen är att central styrning kan bli långsam och uppfattas som långt från verksamhetens behov.

**Lokal styrning** innebär att enskilda verksamhetsområden får stort eget handlingsutrymme. Fördelen är snabbhet och närhet till verkliga behov. Nackdelen är risk för duplicering, varierande kvalitet, svag dokumentation och svårigheter att hantera gemensamma beroenden.

**Federerad styrning** innebär att centrala principer, plattformar och kontrollpunkter kombineras med lokalt ansvar för användningsfall och nyttorealisering. För offentlig sektor är detta ofta det mest realistiska mönstret. Det gör det möjligt att hålla ihop risk, säkerhet, juridik och teknik, samtidigt som verksamheterna kan arbeta med sina egna behov.

Arkitektens uppgift är att hjälpa organisationen att se vilka beslut som behöver vara gemensamma och vilka som bör ligga nära verksamheten.

Gemensamma beslut kan vara:

- vilka AI-plattformar som är godkända
- vilka informationsklasser som får hanteras i vilka miljöer
- vilka loggnings- och spårbarhetskrav som gäller
- vilka minimikrav som gäller vid upphandling
- hur riskklassning av AI-användning ska göras
- vilka arkitekturprinciper som är obligatoriska

Lokala beslut kan vara:

- vilka verksamhetsproblem som ska prioriteras
- hur arbetsprocesser förändras
- vilka användargrupper som behöver utbildas
- hur nyttan ska mätas
- vilka manuella kontroller som behövs i den specifika processen

Federerad styrning kräver tydliga gränssnitt mellan centralt och lokalt ansvar. Utan sådana gränssnitt blir modellen antingen centraliserad i praktiken eller otydlig i praktiken.

### Arkitekturforumens förändrade roll

I AI-eran behöver arkitekturforum hantera fler typer av beslut än tidigare. Det räcker inte att granska integrationsmönster, systemplacering och tekniska standarder. Forumet behöver också kunna bedöma informationsanvändning, risknivå, ansvar, förvaltningsmodell och långsiktiga beroenden.

Det betyder inte att arkitekturforumet ska ersätta juridik, informationssäkerhet eller verksamhetsledning. Däremot behöver forumet skapa en gemensam beslutsyta där dessa perspektiv möts.

Ett AI-relaterat arkitekturbeslut bör normalt innehålla:

- syfte och verksamhetsnytta
- typ av AI-förmåga
- berörda processer och användargrupper
- data och informationsklasser
- tekniska beroenden
- leverantörsberoenden
- risknivå och konsekvensbedömning
- krav på mänsklig granskning
- krav på loggning och uppföljning
- förvaltningsansvar
- avvecklings- eller exitstrategi

Arkitekturforumets värde ligger i att synliggöra konsekvenser innan de blir dyra, svåra eller politiskt känsliga.

### Styrning av experiment

Offentlig sektor behöver kunna experimentera med AI. Utan experiment blir organisationen beroende av leverantörers berättelser, allmänna trender och abstrakta strategier. Men experiment får inte förväxlas med fri användning utan ansvar.

Ett bra experiment har tydliga ramar:

- vilket problem som undersöks
- vilken information som får användas
- vilka användare som deltar
- vad som inte får göras
- hur resultatet ska bedömas
- när experimentet avslutas
- vilka beslut som krävs för att gå vidare

Ett vanligt problem är att pilotprojekt startas utan väg till förvaltning. De visar potential men saknar arkitektonisk väg framåt. När piloten sedan ska skalas upptäcks frågor om informationssäkerhet, integration, juridik, drift, kostnad, support och ägarskap. Strategisk arkitekturstyrning bör därför kräva att varje experiment redan från början beskriver vilken typ av beslut det ska möjliggöra.

Ett experiment kan till exempel syfta till att avgöra om organisationen ska:

- etablera en gemensam AI-plattform
- tillåta en viss typ av AI-stöd i handläggningsprocesser
- upphandla en tjänst
- bygga egen kompetens
- avstå från ett användningsområde
- gå vidare till kontrollerad produktionssättning

Experimentet är då inte ett sidospår utan en del av arkitekturlärandet.

### Styrning genom portfölj, inte bara lösning

AI-initiativ bör inte bara bedömas var för sig. De behöver också ses som en portfölj. Annars riskerar organisationen att många små initiativ tillsammans skapar stor komplexitet.

En portföljvy kan visa:

- vilka AI-förmågor som finns eller planeras
- vilka verksamhetsområden som påverkas
- vilka datakällor som återanvänds
- vilka leverantörer som används
- vilka risknivåer initiativen har
- vilka initiativ som kräver gemensam infrastruktur
- vilka initiativ som överlappar
- vilka lösningar som bör konsolideras

För IT-arkitekten är portföljperspektivet viktigt eftersom AI ofta börjar som en lokal förbättring men snabbt blir en gemensam förmåga. En chattassistent, ett dokumentanalysstöd eller en beslutstödskomponent kan först verka begränsad, men om flera delar av organisationen börjar använda liknande lösningar uppstår behov av gemensamma mönster.

Portföljstyrning hjälper också organisationen att undvika att den strategiska AI-agendan domineras av de initiativ som råkar vara mest synliga, snarare än de som har störst långsiktig betydelse.

### Externa ramverk som stöd, inte ersättning för arkitektur

Offentlig sektor behöver förhålla sig till regler, standarder och ramverk för AI. EU:s AI Act, NIST AI Risk Management Framework och ISO/IEC 42001 är exempel på källor som kan påverka styrning och ledningssystem. Dessa bör användas som stöd, men de ersätter inte arkitekturarbetet.

Ett regelverk kan säga att vissa risker behöver hanteras. Ett ledningssystem kan ange krav på processer och ansvar. Men arkitekten behöver fortfarande översätta detta till praktiska arkitekturval:

- Var ska kontrollerna ligga?
- Vilka komponenter behöver logga vad?
- Hur kopplas riskklassning till lösningsdesign?
- Hur hanteras förändringar över tid?
- Vilka beroenden skapas av vald plattform?
- Hur påverkas målarkitekturen?
- Vilka krav måste in i upphandling?

Regelverk och standarder bör därför integreras i arkitekturstyrningen, inte behandlas som separata checklistor vid sidan av.

Eftersom regelverk och vägledningar förändras bör bokens läsare alltid verifiera aktuella krav mot officiella källor vid faktisk tillämpning.

## Scenario eller beslutskontext

Föreställ dig en offentlig organisation där flera verksamhetsområden samtidigt börjar använda generativ AI. Kommunikationsavdelningen vill använda AI för att skriva utkast till texter. En handläggningsenhet vill sammanfatta inkomna handlingar. IT-avdelningen vill använda AI för kodgranskning och dokumentation. Ledningen vill etablera en intern AI-assistent för frågor om styrande dokument.

Varje initiativ kan verka rimligt var för sig. Men tillsammans väcker de strategiska arkitekturfrågor:

- Ska alla använda samma AI-plattform?
- Vilken information får skickas till externa tjänster?
- Hur ska användningen loggas?
- Vem ansvarar för felaktiga sammanfattningar?
- Hur hanteras upphovsrätt, sekretess och personuppgifter?
- Vilka krav ska ställas på leverantörer?
- Ska promptar och instruktioner betraktas som styrande konfiguration?
- När blir ett stöd så verksamhetskritiskt att det kräver formell förvaltning?
- Hur säkerställs att AI inte används för beslut som kräver särskild rättssäkerhet?

Utan strategisk arkitekturstyrning kommer varje initiativ att skapa sina egna svar. Med styrning kan organisationen skapa gemensamma principer, tydliga ramar och återanvändbara arkitekturmönster.

Arkitektens uppgift är inte att säga ja eller nej till AI i allmänhet. Uppgiften är att göra vägvalen synliga och hjälpa organisationen att fatta beslut på rätt nivå.

## Strategiska vägval och arkitektöverväganden

### Vägval 1: Ska AI styras som teknik, verksamhetsförändring eller riskområde?

Ett vanligt första vägval är vilket perspektiv som ska dominera styrningen.

Om AI styrs som teknik hamnar fokus på plattformar, integrationer, säkerhet och leverantörer. Det är nödvändigt men otillräckligt. Risken är att organisationen får teknisk kontroll men svag koppling till verksamhetsnytta och ansvar.

Om AI styrs som verksamhetsförändring hamnar fokus på processer, nytta, arbetssätt och kompetens. Det är också nödvändigt men kan bli riskabelt om tekniska och säkerhetsmässiga beroenden underskattas.

Om AI styrs som riskområde hamnar fokus på juridik, etik, säkerhet och efterlevnad. Det är särskilt relevant i offentlig sektor men kan leda till att AI främst ses som något som ska begränsas.

Ett moget synsätt kombinerar alla tre. AI bör styras som en socioteknisk förändring: teknik, verksamhet och risk i samma beslutsstruktur.

**Arkitektens fråga:** Vilken del av organisationen äger helheten när AI påverkar både process, teknik, data och ansvar?

### Vägval 2: Central plattform eller flera kontrollerade alternativ?

En central AI-plattform kan ge starkare kontroll, gemensam säkerhet, bättre kostnadsuppföljning och enklare kompetensuppbyggnad. Den kan också minska risken för att varje verksamhetsområde upphandlar egna lösningar.

Samtidigt kan en alltför central plattform bli trög, begränsande och svår att anpassa till olika behov. Alla AI-användningar har inte samma risk, datakrav eller integrationsbehov.

Flera kontrollerade alternativ kan ge flexibilitet, men kräver starkare styrning av standarder, informationsklassning, upphandling och portföljöverblick.

**Arkitektens fråga:** Vilka delar måste vara gemensamma för att ge kontroll, och vilka delar kan variera utan att skapa oacceptabel komplexitet?

### Vägval 3: Principstyrning eller detaljstyrning?

Principstyrning ger riktning och möjliggör lokala tolkningar. Det passar när tekniken förändras snabbt och användningsfallen varierar. Nackdelen är att principer kan bli för abstrakta om de inte kopplas till beslutspunkter.

Detaljstyrning ger tydliga regler och minskar tolkningsutrymme. Det kan vara nödvändigt för känsliga informationsklasser, högriskanvändning och gemensamma plattformar. Nackdelen är att regler snabbt kan bli föråldrade.

En praktisk modell är att använda principstyrning som grund och detaljstyrning där konsekvensen är hög.

**Arkitektens fråga:** Var behöver organisationen fasta regler, och var räcker det med tydliga beslutsprinciper?

### Vägval 4: Innovation först eller kontroll först?

Organisationer pendlar ofta mellan två ytterligheter. Antingen vill man snabbt testa AI för att inte halka efter, eller så vill man vänta tills alla risker är utredda. Båda hållningarna kan vara problematiska.

Innovation utan kontroll skapar oöverblickbara risker. Kontroll utan lärande skapar stagnation och beroende av andra aktörer.

Strategisk styrning bör därför möjliggöra kontrollerad innovation. Det betyder att experiment tillåts, men inom tydliga ramar för information, användning, dokumentation och beslut om nästa steg.

**Arkitektens fråga:** Hur kan organisationen lära sig snabbt utan att normalisera ogenomtänkt användning?

### Vägval 5: Tillfällig policy eller permanent styrmodell?

Många organisationer börjar med en tillfällig AI-policy. Det är ofta rimligt. Men en policy räcker inte om AI blir en del av organisationens långsiktiga digitala förmåga.

En permanent styrmodell behöver beskriva forum, roller, processer, principer, dokumentation, uppföljning och portföljstyrning. Den behöver också kopplas till befintliga styrmodeller för arkitektur, informationssäkerhet, dataskydd, upphandling och verksamhetsutveckling.

**Arkitektens fråga:** Är AI-styrningen en separat temporär aktivitet, eller är den integrerad i organisationens ordinarie styrning?

## Vanliga felsatsningar

### Felsatsning: AI-strategi utan arkitekturkonsekvenser

**Varför det händer:** Strategier formuleras ofta på hög nivå: organisationen ska bli mer datadriven, effektivare eller mer innovativ med AI. Men strategin översätts inte till målarkitektur, plattformar, dataförmågor, ansvar eller styrning.

**Hur arkitekten kan undvika det:** Kräv att varje strategiskt AI-mål kopplas till arkitekturkonsekvenser: vilka förmågor behöver etableras, vilka principer ska gälla, vilka beroenden accepteras och vilka investeringar krävs?

### Felsatsning: Pilotprojekt utan väg till förvaltning

**Varför det händer:** Pilotprojekt startas för att visa potential. Fokus ligger på demonstration, inte på långsiktig drift, ansvar och skalning.

**Hur arkitekten kan undvika det:** Skapa en tydlig övergång från experiment till förvaltad förmåga. Definiera vilka beslut som krävs för att gå vidare och vilka krav som måste vara uppfyllda före produktionssättning.

### Felsatsning: Policy som inte påverkar beslut

**Varför det händer:** Organisationen tar fram en AI-policy men kopplar den inte till arkitekturforum, upphandling, informationsklassning, systemutveckling eller verksamhetsbeslut.

**Hur arkitekten kan undvika det:** Översätt policyn till konkreta arkitekturprinciper, checklistor, beslutspunkter och kravmallar.

### Felsatsning: Centralisering utan tjänsteförmåga

**Varför det händer:** Ledningen vill ha kontroll och beslutar om central AI-styrning eller central plattform. Men den centrala funktionen får inte mandat, kompetens eller kapacitet att stödja verksamheten.

**Hur arkitekten kan undvika det:** Bedöm central styrning som en tjänst till organisationen. Den behöver tydliga erbjudanden, beslutsvägar, support, vägledning och förmåga att hantera verksamhetens behov.

### Felsatsning: Lokal frihet utan portföljöverblick

**Varför det händer:** Verksamhetsområden får testa AI fritt för att skapa innovation. Ingen samlar helhetsbilden.

**Hur arkitekten kan undvika det:** Inför enkel portföljrapportering för AI-initiativ. Synliggör användningsfall, data, leverantörer, risknivå och status.

### Felsatsning: Efterlevnad som separat spår

**Varför det händer:** Juridik, dataskydd och informationssäkerhet hanteras som separata granskningar efter att lösningen redan designats.

**Hur arkitekten kan undvika det:** Bygg in juridik, dataskydd och säkerhet i arkitekturprocessen från början. Gör dem till designförutsättningar, inte efterhandskontroller.

## Arkitektens checklista

Använd checklistan när organisationen etablerar eller uppdaterar strategisk arkitekturstyrning för AI.

### Styrning och ansvar

- Finns en tydlig ägare för AI-styrning på strategisk nivå?
- Är ansvarsfördelningen mellan verksamhet, IT, arkitektur, juridik, dataskydd och informationssäkerhet dokumenterad?
- Finns forum där AI-relaterade arkitekturbeslut kan hanteras tvärfunktionellt?
- Är det tydligt vilka beslut som tas centralt och vilka som tas lokalt?
- Finns en modell för att eskalera AI-initiativ med hög risk eller hög verksamhetspåverkan?

### Principer och målarkitektur

- Finns ett begränsat antal tydliga arkitekturprinciper för AI?
- Är principerna kopplade till faktiska beslutspunkter?
- Finns en målarkitektur som beskriver önskade AI-förmågor, inte bara teknikprodukter?
- Finns referensarkitekturer eller mönster för återkommande AI-användning?
- Är målarkitekturen tillräckligt flexibel för förändrad teknik och förändrade regelverk?

### Data och information

- Är informationsklassning en obligatorisk del av AI-beslut?
- Är dataägarskap och datakvalitet bedömda innan AI-lösningar införs?
- Finns krav på metadata, spårbarhet och loggning?
- Är det tydligt vilken information som får användas i externa respektive interna AI-tjänster?
- Finns kontroller för att undvika oavsiktlig exponering av känslig information?

### Plattform och leverantörer

- Finns godkända plattformar eller tydliga kriterier för plattformsval?
- Bedöms leverantörsberoenden, avtalsvillkor och exitmöjligheter?
- Finns krav på revision, loggning, databehandling och transparens i upphandling?
- Är kostnadsmodellen förstådd även vid skalad användning?
- Finns möjlighet att byta eller komplettera komponenter över tid?

### Livscykel och uppföljning

- Finns process för att gå från experiment till förvaltad förmåga?
- Finns krav på uppföljning av nytta, risk, kvalitet och användning?
- Är det tydligt när en AI-lösning ska omprövas?
- Finns incident- och avvikelsehantering för AI-relaterade fel?
- Finns avvecklingsplan för AI-förmågor som inte längre är lämpliga?

### Offentlig sektors särskilda hänsyn

- Är rättssäkerhet, transparens och medborgarförtroende uttryckliga designkriterier?
- Har offentlighet, sekretess, personuppgifter och informationssäkerhet beaktats tidigt?
- Finns möjlighet till granskning och ansvarsutkrävande?
- Är beroenden till externa plattformar förenliga med organisationens krav på långsiktig handlingsfrihet?
- Är styrningen begriplig för både tekniska och icke-tekniska beslutsfattare?

## Snabb sammanfattning

- AI kräver strategisk arkitekturstyrning eftersom det påverkar teknik, verksamhet, data, ansvar och risk samtidigt.
- Styrningen bör göra det lätt att experimentera kontrollerat och svårt att oavsiktligt bygga in ohanterade risker.
- Arkitekturprinciper för AI ska fungera som beslutsregler, inte som allmänna ambitioner.
- Målarkitektur för AI bör beskriva förmågor, kontrollpunkter och byggblock snarare än låsa organisationen vid en detaljerad framtidsritning.
- Referensarkitekturer kan hjälpa organisationen att återanvända säkra och förvaltningsbara mönster.
- Federerad styrning är ofta lämplig i offentlig sektor eftersom den kombinerar central kontroll med verksamhetsnära ansvar.
- AI-initiativ bör styras som en portfölj, inte bara som enskilda projekt.
- Externa regelverk och standarder bör integreras i arkitekturstyrningen, men de ersätter inte arkitektens översättning till praktiska vägval.

## Reflektionsfrågor

1. Vilka AI-relaterade beslut i din organisation tas i dag lokalt trots att de borde ha gemensamma principer?
2. Vilka delar av AI-styrningen bör vara centrala, och vilka bör ligga nära verksamheten?
3. Har organisationen arkitekturprinciper som faktiskt hjälper vid AI-relaterade vägval?
4. Var finns störst risk för skugg-AI: i verksamhetsprocesser, dokumenthantering, utvecklingsarbete eller analysarbete?
5. Vilka AI-initiativ skulle bli svåra att förvalta om de gick från pilot till bred användning i morgon?
6. Vilka leverantörsberoenden håller på att byggas in utan att vara synliga som strategiska beslut?
7. Hur skulle ett arkitekturforum behöva förändras för att kunna hantera AI-förmågor på ett moget sätt?

## Nästa steg

Strategisk styrning ger ramarna, men ramarna behöver fyllas med konkreta beslut om risk, ansvar och spårbarhet. Nästa kapitel fördjupar därför hur IT-arkitekten bör hantera beslutsfattande, risk och ansvar när AI blir en del av offentliga verksamheters digitala förmågor.
