# Kapitel 8: Integrationsarkitektur för AI-förmågor

## Varför detta kapitel finns

AI blir sällan värdeskapande som isolerad teknik. En modell, en chattfunktion eller en analysmotor får verklig betydelse först när den kopplas till verksamhetens processer, data, system, användargränssnitt, behörighetsmodeller och beslutspunkter. Det är här integrationsarkitekturen blir avgörande.

I offentlig sektor finns ofta stora systemlandskap med lång livslängd, flera leverantörer, gemensamma nationella tjänster, lokala specialsystem, manuella arbetsmoment och omfattande krav på spårbarhet. AI-förmågor behöver därför införas utan att skapa oöverblickbara beroenden, kringgå etablerade säkerhetskontroller eller försvåra förvaltning. Integrationsfrågan är inte bara teknisk. Den påverkar ansvar, styrning, rättssäkerhet, informationshantering och möjligheten att förändra arkitekturen över tid.

I föregående kapitel etablerades dataarkitektur som grund för AI. Där låg fokus på data product, metadata, data readiness, semantisk arkitektur och informationsägarskap. Detta kapitel tar nästa steg: hur dessa datatillgångar och AI-förmågor kopplas ihop med befintliga system och processer på ett kontrollerat sätt.

För IT-arkitekten innebär detta ett skifte. Det räcker inte att fråga om en AI-tjänst kan integreras. Arkitekten behöver fråga var integrationen bör ske, vilka beroenden den skapar, vilken kontext AI-tjänsten får tillgång till, hur resultat används, vem som ansvarar när något går fel och hur lösningen kan avvecklas eller bytas ut utan att verksamheten låses fast.

## Lärandemål

Efter kapitlet ska läsaren kunna:

- beskriva vanliga integrationsmönster för AI-förmågor i komplexa offentliga IT-miljöer
- bedöma var i en process, ett systemlandskap eller en plattform en AI-förmåga bör kopplas in
- analysera beroenden mellan AI-tjänster, dataflöden, API:er, händelser, användargränssnitt och befintliga verksamhetssystem
- identifiera risker med punktintegrationer, otydliga ansvar, svag spårbarhet och otillräcklig kontextstyrning
- formulera arkitektöverväganden för integration av AI i offentlig sektor

## Innan vi börjar

Vi bygger vidare på tre tidigare insikter.

För det första är AI en förmåga, inte bara en komponent. Det betyder att integration inte bara handlar om teknisk anslutning, utan om att AI-förmågan blir en del av ett verksamhetsflöde med ansvar, styrning och uppföljning.

För det andra kräver AI fungerande dataarkitektur. Om data saknar tydlig ägare, kvalitet, klassning eller semantisk betydelse blir integrationen osäker även om tekniken fungerar.

För det tredje är offentlig sektor beroende av tillit och rättssäkerhet. En integration som gör det svårt att förstå hur information har använts, hur ett förslag har uppstått eller vem som fattat beslut kan skada både förvaltningsbarhet och förtroende.

## Huvudförklaring

### AI-integration skiljer sig från traditionell systemintegration

Traditionell systemintegration handlar ofta om att flytta, synkronisera eller exponera information mellan system. AI-integration gör detta, men lägger till ytterligare komplexitet. AI-förmågan kan tolka, sammanfatta, klassificera, generera, prioritera eller föreslå. Det innebär att integrationen inte bara transporterar data; den påverkar hur data förstås och används.

När ett verksamhetssystem anropar en AI-tjänst för att sammanfatta ett ärende, prioritera inkommande ansökningar eller föreslå handläggningssteg uppstår flera arkitekturfrågor:

- Vilken information skickas till AI-tjänsten?
- Hur begränsas informationen till det som är nödvändigt?
- Hur vet AI-tjänsten vilken kontext som gäller?
- Hur dokumenteras svaret?
- Är svaret ett beslutsunderlag, en rekommendation eller ett automatiserat beslut?
- Hur visas osäkerhet för användaren?
- Hur loggas interaktionen?
- Hur kan resultatet granskas i efterhand?
- Vad händer om modellen ändras?

Detta gör AI-integration till en arkitekturfråga på flera nivåer samtidigt: verksamhetsarkitektur, informationsarkitektur, applikationsarkitektur, säkerhetsarkitektur och teknisk arkitektur.

### Fyra huvudsakliga integrationslägen

Ett praktiskt sätt att strukturera vägvalet är att skilja mellan fyra integrationslägen.

Det första är **användarnära integration**. AI-förmågan placeras nära användargränssnittet, exempelvis som en assistent, sammanfattningsfunktion eller frågefunktion i ett befintligt verktyg. Fördelen är att nyttan kan bli tydlig och att människan ofta finns kvar i loopen. Nackdelen är risken för otydlig styrning om många användarnära funktioner införs utan gemensamma principer.

Det andra är **processnära integration**. AI-förmågan kopplas till ett definierat arbetsflöde, till exempel ärendeberedning, remisshantering, tillsynsplanering eller kunskapsstöd. Här blir arkitekturfrågan starkt kopplad till ansvar, processägarskap och beslutspunkter. AI blir en del av hur arbetet utförs.

Det tredje är **systemnära integration**. AI-förmågan byggs in i eller nära ett verksamhetssystem. Det kan ge hög effektivitet och sömlös användning, men skapar ofta starkare beroenden till systemets leverantör, datamodell, releasecykel och förvaltningsorganisation.

Det fjärde är **plattformnära integration**. AI-förmågor exponeras via gemensamma plattformstjänster, API:er, model gateways, integrationstjänster eller interna utvecklarplattformar. Detta kan ge bättre återanvändning, styrning och kontroll, men kräver större mognad och tydligare central arkitektur.

Inget av dessa lägen är generellt bäst. Arkitektens uppgift är att bedöma vilket integrationsläge som passar användningens risk, nytta, databehov, förändringstakt och ansvar.

### API:er, händelser och orkestrering

Många AI-förmågor kommer att exponeras via API:er. Ett API kan göra det möjligt för verksamhetssystem, digitala tjänster eller interna plattformar att anropa en AI-funktion. Men API:et är bara en del av arkitekturen.

För AI behöver API-design ofta hantera mer än tekniska parametrar. Det kan behöva beskriva vilken typ av information som får skickas, vilken klassning informationen får ha, vilken modell eller tjänst som används, hur svar ska tolkas, vilka loggar som skapas och vilka begränsningar som gäller. Ett AI-API bör därför ses som ett kontrakt för både teknik och ansvar.

Händelsedriven arkitektur kan också vara relevant. En AI-förmåga kan reagera på händelser, exempelvis att ett nytt ärende kommer in, att en handling registreras, att en riskindikator uppstår eller att en tidsfrist närmar sig. Händelser kan skapa lösare koppling mellan system, men de kräver tydliga händelsedefinitioner, informationsklassning, spårbarhet och kontroll över vilka prenumeranter som får agera på vilken information.

Orkestrering blir viktig när flera steg behöver kombineras. En AI-förmåga kanske först hämtar relevant information, sedan gör en klassificering, därefter skapar ett förslag och till sist skickar resultatet till ett ärendehanteringssystem. I en sådan kedja måste arkitekten kunna se hela flödet: var data hämtas, var den bearbetas, var beslutspunkter finns och var fel kan uppstå.

En vanlig risk är att AI-integrationer byggs som dolda kedjor av anrop utan tydligt processägarskap. Det kan ge snabb funktionalitet men svag förvaltningsbarhet. Arkitekten bör därför efterfråga explicita integrationsflöden, ansvarspunkter och loggstrategier.

### Kontext är en integrationsfråga

AI-förmågor behöver ofta kontext för att vara användbara. Kontext kan vara ärendedata, lagrum, interna riktlinjer, historik, verksamhetsbegrepp, användarens roll, behörigheter, språk, kanal eller aktuell processfas. Utan rätt kontext blir AI-svaret generiskt eller missvisande. Med för mycket kontext ökar risken för dataläckage, felaktig användning eller överexponering av känslig information.

Därför är kontextstyrning en central del av integrationsarkitekturen. Arkitekten behöver designa hur kontext väljs, begränsas, kvalitetssäkras och dokumenteras.

Ett exempel är en AI-assistent för handläggare. Den bör inte automatiskt få tillgång till allt i organisationens dokumentlager. Den bör få tillgång till relevant information baserat på ärendetyp, användarens behörighet, informationsklassning, syfte och processfas. Den bör också kunna skilja mellan styrande dokument, historiska exempel, arbetsmaterial och externa källor.

Här möts dataarkitektur och integrationsarkitektur. Metadata, semantisk arkitektur och data lineage gör det möjligt att ge AI-förmågan rätt kontext utan att öppna för bred och okontrollerad åtkomst.

### Integration av resultat är lika viktig som integration av indata

Många AI-diskussioner fokuserar på vad modellen ska få läsa. Minst lika viktigt är vad som händer med modellens output.

Ett AI-genererat svar kan visas för en användare, sparas i ett ärende, skickas vidare till ett annat system, ligga till grund för statistik, användas i beslutsstöd eller trigga nästa steg i ett flöde. Varje alternativ har olika arkitekturkonsekvenser.

Om output bara visas tillfälligt som stöd kan kraven på lagring vara annorlunda än om output blir del av en myndighetsakt. Om output påverkar prioritering eller beslut krävs ofta tydligare spårbarhet, förklaring, ansvar och möjlighet till granskning. Om output skickas vidare automatiskt kan AI-förmågan i praktiken få styrande effekt även om den formellt kallas rådgivande.

Arkitekten bör därför klassificera AI-output efter användning:

- informativ output, som hjälper användaren att förstå
- rådgivande output, som föreslår nästa steg
- strukturerande output, som kategoriserar eller sorterar
- styrande output, som påverkar ordning, prioritet eller process
- beslutsnära output, som används direkt i beslutsunderlag

Ju närmare output ligger styrning och beslut, desto högre krav bör ställas på dokumentation, kontroller och mänsklig granskning.

### AI-gateways och mellanlager

När AI-användningen växer blir det ofta ohållbart att varje system integrerar direkt mot varje modell eller leverantör. Ett alternativ är att införa någon form av AI-gateway, model gateway eller policy layer mellan verksamhetssystem och AI-tjänster.

Ett sådant mellanlager kan hantera autentisering, auktorisation, loggning, policykontroller, kostnadsuppföljning, modellval, spärrar mot otillåten information, versionshantering och standardiserade anropsmönster. Det kan också göra det lättare att byta modell eller leverantör utan att ändra alla verksamhetssystem.

Men ett mellanlager är inte gratis. Det kräver ägarskap, drift, kompetens, styrning och tydliga gränssnitt. Det kan också bli en flaskhals om organisationen centraliserar för mycket utan att skapa stöd för verksamhetsnära behov.

För offentlig sektor är frågan ofta inte om central kontroll eller lokal frihet är bäst, utan hur de balanseras. En gemensam AI-gateway kan vara lämplig för högriskfunktioner, känslig information och gemensamma kontroller. En mer federerad integrationsmodell kan vara lämplig för låg risk, experiment och verksamhetsnära stöd, så länge gemensamma principer följs.

### Legacy-system och lång livscykel

Offentlig sektor har ofta system som är verksamhetskritiska men tekniskt åldrade. AI kan då framstå som ett sätt att skapa nya förmågor utan att modernisera kärnsystemen. Det kan vara lockande men riskabelt.

Att lägga AI ovanpå legacy-system kan ge snabbare nytta. En AI-förmåga kan exempelvis hjälpa användare att söka, tolka eller sammanfatta information från äldre system. Men om integrationen döljer underliggande informationsbrister kan organisationen skjuta upp nödvändig modernisering. AI blir då ett lager som kompenserar för arkitekturella problem i stället för att lösa dem.

Arkitekten behöver därför skilja mellan AI som accelererar modernisering och AI som maskerar teknisk skuld. En AI-integration bör inte automatiskt legitimera ett dåligt datalandskap, svaga API:er eller otydligt informationsägarskap. I vissa fall är rätt beslut att först förbättra systemintegration, datakvalitet och informationsmodeller innan AI införs i större skala.

### Förvaltning och förändring

En integration är inte klar när den fungerar tekniskt. AI-förmågor förändras över tid. Modeller uppdateras, leverantörsvillkor ändras, datakällor får nya strukturer, användarbeteenden utvecklas och riskbedömningar behöver omprövas.

Integrationsarkitekturen måste därför stödja livscykelhantering. Det bör vara möjligt att se vilken modellversion som används, vilka system som anropar tjänsten, vilka datakällor som ingår, vilka policyer som gäller och vilka beroenden som påverkas vid ändring. För AI är detta särskilt viktigt eftersom en förändring i modellen kan ändra beteendet även om API:et tekniskt är oförändrat.

Ett klassiskt integrationskontrakt beskriver ofta syntax och tillgänglighet. Ett AI-relaterat integrationskontrakt behöver även beskriva semantik, tillåten användning, riskklass, kontrollpunkter, uppföljning och förändringshantering.

## Scenario eller beslutskontext

En offentlig organisation vill införa en AI-funktion som stödjer handläggare genom att sammanfatta inkomna handlingar, föreslå ärendekategori och lyfta fram möjliga kompletteringsbehov. Funktionen ska inte fatta beslut, men den kommer att påverka hur handläggaren förstår ärendet och vilka åtgärder som övervägs.

Organisationen har ett ärendehanteringssystem, ett dokumentlager, en integrationsplattform, en behörighetslösning och flera styrande dokument som beskriver rutiner och regelverk. Det finns också en pågående diskussion om att etablera en gemensam AI-plattform.

Tre integrationsalternativ diskuteras.

Det första alternativet är att bygga funktionen direkt i ärendehanteringssystemet via leverantörens AI-modul. Det kan ge snabb och användarnära nytta, men skapar beroende till leverantörens modellval, loggning, databehandling och förändringstakt.

Det andra alternativet är att bygga en separat AI-tjänst som anropas via organisationens integrationsplattform. Det ger mer kontroll och möjlighet att återanvända tjänsten, men kräver tydligare ansvar för drift, API-kontrakt, behörigheter och modellförvaltning.

Det tredje alternativet är att vänta in en gemensam AI-plattform med policy layer, loggning, modellval och centrala kontroller. Det kan ge bättre styrning på sikt, men fördröjer nyttorealisering och riskerar att verksamheten hittar egna informella lösningar under tiden.

Arkitekturfrågan är inte vilket alternativ som är mest modernt. Frågan är vilket alternativ som bäst balanserar nytta, kontroll, förvaltningsbarhet, risk, informationsklassning och långsiktig riktning.

## Strategiska vägval och arkitektöverväganden

### Vägval 1: Direktintegration eller gemensamt mellanlager

Direktintegration kan vara rimlig när användningen är smal, risken låg, datamängden begränsad och lösningen är tydligt avgränsad. Den kan också vara nödvändig när ett verksamhetssystem redan har en mogen och kontrollerad AI-funktion.

Ett gemensamt mellanlager är mer relevant när flera system behöver AI-förmågor, när informationsklassning varierar, när organisationen vill styra modellval centralt eller när loggning och policykontroller behöver standardiseras.

Arkitekten bör tänka på:

- Hur många framtida AI-integrationer förväntas?
- Finns gemensamma krav på loggning, åtkomst, kostnadskontroll och policy?
- Behöver organisationen kunna byta modell eller leverantör?
- Är central kontroll viktigare än snabb lokal anpassning?
- Finns kapacitet att förvalta ett mellanlager?

En vanlig slutsats är att börja med begränsade integrationer men samtidigt etablera principer som gör att de senare kan flyttas eller anslutas till ett gemensamt lager.

### Vägval 2: Användarnära stöd eller processintegration

Användarnära stöd är ofta enklare att införa och kan hålla människan i loopen. Det passar när AI ska hjälpa användare att förstå, sammanfatta, söka eller formulera. Processintegration är mer kraftfull men också mer riskfylld, eftersom AI då påverkar flöden, prioriteringar och arbetsfördelning.

Arkitekten bör tänka på:

- Påverkar AI-förmågan ett faktiskt beslut eller bara användarens förståelse?
- Kan användaren tydligt se vad som är AI-genererat?
- Finns risk att rekommendationer följs okritiskt?
- Behöver processen ändras, eller räcker ett stöd i befintligt gränssnitt?
- Hur dokumenteras användningen?

I offentlig sektor bör processintegration behandlas som ett styrningsbeslut, inte bara som teknisk förbättring.

### Vägval 3: Synkrona anrop eller händelsedriven integration

Synkrona anrop passar när användaren väntar på ett svar, exempelvis sammanfattning eller förslag i ett gränssnitt. Händelsedriven integration passar när AI ska reagera på förändringar, exempelvis inkommande ärenden eller avvikande mönster.

Arkitekten bör tänka på:

- Kräver användningsfallet omedelbart svar?
- Kan resultatet beräknas i bakgrunden?
- Hur hanteras fel, timeout och osäkerhet?
- Vilka händelser är tillräckligt väldefinierade?
- Hur undviks att händelser leder till dolda automatiska beslut?

Händelsedriven AI kan ge effektivitet, men den måste göras begriplig och spårbar.

### Vägval 4: Centraliserad AI-plattform eller federerade AI-tjänster

En centraliserad plattform kan ge gemensam styrning, återanvändning och säkerhetskontroller. Federerade tjänster kan ge snabbare innovation och bättre verksamhetsanpassning. För många offentliga organisationer blir den långsiktigt hållbara modellen en kombination: centrala ramar och kontroller, men decentraliserad användning inom godkända mönster.

Arkitekten bör tänka på:

- Vilka AI-förmågor är gemensamma för hela organisationen?
- Vilka kräver lokal verksamhetskunskap?
- Var finns kompetens att förvalta AI-integrationer?
- Hur undviks både skugg-AI och övercentralisering?
- Vilka delar måste standardiseras: identitet, loggning, klassning, API, modellval, utvärdering?

Det viktiga är att federering inte blir ett annat ord för oordning. Federerad arkitektur kräver tydliga principer och gemensamma kontroller.

### Vägval 5: Integrera med befintlig arkitektur eller skapa ny parallell struktur

AI-initiativ skapar ibland parallella strukturer: nya datalager, nya behörighetslösningar, nya integrationsvägar och nya gränssnitt. Det kan vara nödvändigt i experiment, men riskerar att skapa långsiktig komplexitet.

Arkitekten bör tänka på:

- Återanvänder lösningen befintlig identitets- och behörighetsstyrning?
- Följer den etablerade integrationsstrategier?
- Bygger den vidare på organisationens dataarkitektur?
- Skapar den nya informationskopior utan tydligt ägarskap?
- Finns plan för övergång från pilot till förvaltning?

AI bör inte bli ett undantagsspår som kringgår arkitekturen. Samtidigt måste arkitekturen utvecklas så att den inte blockerar rimlig innovation.

## Vanliga felsatsningar

- **Felsatsning:** AI-förmågan direktintegreras i ett verksamhetssystem utan tydligt ansvar för modell, data och loggning.
  - **Varför det händer:** Leverantörens funktion är lätt att aktivera och nyttan verkar omedelbar.
  - **Hur arkitekten kan undvika det:** Kräv integrationsbeskrivning, informationsklassning, ansvarsfördelning, loggstrategi och förändringshantering innan införande.

- **Felsatsning:** Organisationen bygger många små AI-integrationer utan gemensamma principer.
  - **Varför det händer:** Verksamheter vill snabbt testa AI och centrala riktlinjer saknas.
  - **Hur arkitekten kan undvika det:** Etablera miniminivåer för API, identitet, loggning, dataminimering, modellval och dokumentation även för pilotprojekt.

- **Felsatsning:** AI får för bred åtkomst till dokument och system.
  - **Varför det händer:** Man vill maximera träffsäkerhet och användbarhet genom att ge modellen mer kontext.
  - **Hur arkitekten kan undvika det:** Designa kontextstyrning baserad på roll, syfte, ärendetyp, informationsklassning och metadata.

- **Felsatsning:** AI-output sparas eller används vidare utan klassificering.
  - **Varför det händer:** Output ses som text eller tekniskt svar snarare än som del av ett beslutsflöde.
  - **Hur arkitekten kan undvika det:** Definiera om output är informativ, rådgivande, strukturerande, styrande eller beslutsnära och koppla kontroller till respektive nivå.

- **Felsatsning:** En central AI-plattform införs utan tydliga användningsmönster.
  - **Varför det händer:** Organisationen vill skapa kontroll och undvika splittring.
  - **Hur arkitekten kan undvika det:** Beskriv konkreta referensmönster, onboardingprocesser, ansvar, API-kontrakt och stöd för verksamhetsnära behov.

- **Felsatsning:** AI används för att dölja problem i legacy-arkitekturen.
  - **Varför det händer:** AI kan snabbt ge bättre sökbarhet, sammanfattningar eller användarstöd ovanpå gamla system.
  - **Hur arkitekten kan undvika det:** Skilj mellan taktisk avlastning och strategisk modernisering. Dokumentera teknisk skuld och gör AI-integrationens livslängd tydlig.

## Arkitektens checklista

- Är det tydligt vilket verksamhetsflöde AI-förmågan ska stödja?
- Är AI-förmågan användarnära, processnära, systemnära eller plattformnära?
- Är syftet med integrationen dokumenterat?
- Är informationsklassning genomförd för indata, kontext och output?
- Är dataminimering tillämpad?
- Är det tydligt vilka datakällor som används?
- Finns metadata och data lineage för centrala datakällor?
- Är behörigheter kopplade till användarens roll och syfte?
- Finns loggning av anrop, kontext, modellversion och output?
- Är AI-output klassificerad efter hur den används?
- Är det tydligt om output är stöd, rekommendation, prioritering eller beslutsunderlag?
- Finns mänsklig kontroll där AI påverkar beslut eller prioritering?
- Finns API-kontrakt som beskriver både teknik och ansvar?
- Finns plan för felhantering, timeout och degradering?
- Finns ändringshantering när modell, prompt, datakälla eller policy ändras?
- Kan lösningen byta modell eller leverantör utan orimligt stor påverkan?
- Är integrationen förenlig med organisationens målarkitektur?
- Finns en exit-strategi?
- Är förvaltningsansvaret tydligt?
- Är integrationen dokumenterad så att den kan granskas i efterhand?

## Snabb sammanfattning

- AI skapar värde först när den integreras i processer, system, dataflöden och beslutspunkter.
- AI-integration skiljer sig från traditionell integration eftersom AI inte bara flyttar data utan tolkar, genererar och påverkar användning av information.
- Arkitekten behöver bedöma om integrationen ska vara användarnära, processnära, systemnära eller plattformnära.
- API:er, händelser och orkestrering behöver kompletteras med ansvar, loggning, informationsklassning och förändringshantering.
- Kontextstyrning är en central integrationsfråga: AI behöver rätt kontext, inte maximal åtkomst.
- AI-output måste klassificeras efter hur den används och vilken påverkan den får.
- Gemensamma mellanlager som AI-gateways kan ge kontroll och flexibilitet, men kräver ägarskap och mognad.
- Offentlig sektor behöver särskilt säkerställa spårbarhet, rättssäkerhet, förvaltningsbarhet och långsiktig kontroll över beroenden.

## Reflektionsfrågor

1. Vilka AI-förmågor i din organisation riskerar att växa fram som punktintegrationer utan gemensam styrning?
2. Var i era viktigaste verksamhetsflöden skulle AI skapa störst nytta: nära användaren, i processen, i systemen eller på plattformsnivå?
3. Vilka typer av AI-output skulle i praktiken kunna påverka beslut även om de formellt beskrivs som stöd?
4. Har organisationen tillräckliga integrationsprinciper för att hantera modellbyte, leverantörsbyte och förändrad informationsklassning?
5. Vilka legacy-problem riskerar att döljas snarare än lösas om AI läggs ovanpå befintliga system?

## Nästa steg

Detta kapitel har behandlat hur AI-förmågor integreras i befintliga systemlandskap och verksamhetsflöden. Nästa kapitel fördjupar de strategiska vägvalen kring plattformar, modeller och ekosystem: om organisationen bör köpa AI-tjänster, använda öppna modeller, bygga egna förmågor eller kombinera flera angreppssätt.

Där blir frågan inte bara hur AI kopplas in, utan vilka tekniska och organisatoriska beroenden organisationen accepterar när den väljer modell, plattform och leverantör.
