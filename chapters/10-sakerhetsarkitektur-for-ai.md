# Kapitel 10: Säkerhetsarkitektur för AI

## Varför detta kapitel finns

AI förändrar inte bara vilka system organisationen bygger. AI förändrar också vad som behöver skyddas, var gränserna går och hur säkerhet måste styras.

I traditionell IT-säkerhet har arkitekter ofta utgått från relativt stabila komponenter: system, databaser, integrationer, identiteter, nätverk, klienter och driftmiljöer. Även när systemen är komplexa är många säkerhetsfrågor välkända: vem får logga in, vilka data får användaren se, hur skyddas överföring, hur loggas händelser, hur hanteras sårbarheter och hur återställs tjänsten vid incident?

AI tillför en annan typ av osäkerhet. En AI-förmåga kan sammanfatta, generera, klassificera, rekommendera, tolka, söka, agera via verktyg och skapa nytt innehåll. Den kan påverkas av användarens instruktioner, av dokument som hämtas in som kontext, av modellens träningsdata, av systempromptar, av integrationer och av de verktyg den får använda. Det innebär att säkerhetsarkitekturen inte bara måste skydda data och system. Den måste också skydda sammanhang, instruktioner, användning, utdata, beslutsflöden och organisationens förtroende.

För offentlig sektor är detta särskilt viktigt. AI-förmågor kan komma nära ärendehantering, tillsyn, rådgivning, analys, informationssökning, beslutsstöd och intern effektivisering. Det betyder att säkerhetsarkitekturen måste hantera informationsklassning, sekretess, integritet, rättssäkerhet, spårbarhet, leverantörsberoenden och medborgarnas tillit. En AI-lösning som är tekniskt imponerande men svår att avgränsa, logga, granska eller förklara kan bli arkitekturellt olämplig även om den fungerar i en pilot.

Det här kapitlet behandlar säkerhetsarkitektur för AI som en strategisk arkitekturfråga. Fokus ligger inte på enskilda säkerhetsprodukter, utan på vilka säkerhetsförmågor, kontrollpunkter och vägval arkitekten behöver beakta när AI införs i en offentlig organisation.

## Lärandemål

Efter kapitlet ska läsaren kunna:

- identifiera nya säkerhetsrisker som uppstår när AI används som arbetsverktyg, systemkomponent eller strategisk förmåga
- skilja mellan traditionella säkerhetskontroller och AI-specifika kontroller
- resonera om hot som prompt injection, dataläckage, felaktig auktorisation, otillåten kontextanvändning och modellmissbruk
- beskriva hur AI-gateway, guardrails, loggning, kontextstyrning och modellklassning kan användas som delar av säkerhetsarkitekturen
- formulera strategiska vägval för säker AI-användning i offentlig sektor
- bedöma när en AI-förmåga kräver särskild säkerhetsgranskning, begränsad användning eller starkare governance

## Innan vi börjar

De föregående kapitlen har etablerat flera byggstenar som är viktiga för säkerhetsarkitekturen.

Kapitel 7 visade att dataarkitektur är grunden för AI. Utan tydligt informationsägarskap, datakvalitet, metadata, data lineage och informationsklassning blir det svårt att veta vilka data en AI-förmåga får använda och vilka risker som uppstår när data kombineras.

Kapitel 8 behandlade integrationsarkitektur. Där introducerades bland annat AI-gateway, kontextstyrning och AI-outputklassificering. Dessa begrepp är centrala i säkerhetsarkitekturen eftersom de hjälper organisationen att styra vilka anrop som görs, vilken information som skickas, hur resultat får användas och hur händelser kan följas upp.

Kapitel 9 betonade att plattformar och modeller skapar långsiktiga beroenden. Säkerhetsarkitektur för AI måste därför kopplas till modellstrategi, plattformsval, leverantörsstyrning, exit-strategi och digital suveränitet. En säkerhetskontroll som bara fungerar i en viss leverantörs miljö kan vara användbar på kort sikt men skapa strategisk inlåsning på lång sikt.

Det här kapitlet binder samman dessa perspektiv. Säker AI handlar inte bara om att lägga till kontroller i slutet av ett projekt. Det handlar om att arkitekturen från början måste definiera gränser, ansvar, policyer, loggning, övervakning, användningsmönster och stoppregler.

## Huvudförklaring

### AI förändrar säkerhetsytan

En AI-förmåga har flera angrepps- och riskytor. Vissa liknar traditionell IT-säkerhet, andra är mer specifika för AI.

Den traditionella ytan finns fortfarande kvar: identiteter, åtkomst, nätverk, API:er, databaser, klienter, sårbarheter, leverantörsåtkomst, driftmiljö och loggning. Dessa kontroller blir inte mindre viktiga för att AI används. Tvärtom blir de ofta viktigare eftersom AI kan ge användare effektivare sätt att nå, sammanställa och bearbeta information.

Den AI-specifika ytan uppstår i samspelet mellan instruktioner, kontext, modellbeteende, verktyg och utdata. En användare kan försöka manipulera modellen genom instruktioner. Ett dokument som hämtas in som kontext kan innehålla skadliga instruktioner. En modell kan sammanställa information på ett sätt som kringgår den åtkomstlogik som gällde i källsystemen. En AI-agent kan använda verktyg på ett sätt som får större effekt än användaren avsåg. En modell kan generera svar som verkar auktoritativa men är felaktiga, olämpliga eller säkerhetsmässigt riskabla.

Arkitektens första uppgift är därför att bredda hotmodellen. Det räcker inte att fråga: "Är systemet skyddat?" Man måste också fråga: "Vad får modellen veta, göra, föreslå, kombinera, minnas, logga, skicka vidare och påverka?"

### Prompt injection och instruktioners säkerhetsvärde

Prompt injection är en risk där en användare, ett dokument eller en extern källa försöker påverka modellens beteende genom instruktioner. Det kan handla om att få modellen att ignorera tidigare regler, avslöja instruktioner, sammanställa otillåten information, använda verktyg felaktigt eller ge svar som bryter mot organisationens policy.

För arkitekten är det viktiga inte bara attackens teknik, utan dess arkitekturella innebörd. I AI-system är instruktioner en del av säkerhetsmodellen. Systempromptar, policyinstruktioner, användarinstruktioner och dokumentinnehåll blandas i samma semantiska miljö. Det innebär att text inte bara är data; text kan också fungera som styrning av beteende.

Detta skapar ett behov av kontrollpunkter:

- tydlig separering mellan systeminstruktioner, användarinstruktioner och hämtad kontext
- begränsning av vilka verktyg modellen får använda
- filtrering eller märkning av extern och osäker kontext
- testning av kända manipulationsmönster
- loggning av promptar, kontext och modellrespons där det är lämpligt och tillåtet
- policyer för vilken typ av information som aldrig får skickas till modellen

Det är sällan realistiskt att helt eliminera prompt injection som risk i öppna, textbaserade AI-flöden. Arkitekturfrågan blir därför hur risken begränsas, upptäcks och isoleras.

### Dataläckage och otillåten kontext

AI kan skapa dataläckage på flera sätt.

Det mest uppenbara är att känslig information skickas till en extern modell eller tjänst utan rättsligt, tekniskt eller avtalsmässigt stöd. Men läckage kan också uppstå internt. En AI-assistent som har åtkomst till många datakällor kan sammanställa information som användaren inte borde ha sett i kombination. En sökbaserad AI-lösning kan hämta dokument där åtkomstkontrollerna inte följer med från källsystemet. En chattlogg kan lagra personuppgifter eller sekretessbelagd information längre än nödvändigt.

Därför behöver AI-säkerhet kopplas direkt till informationsklassning och kontextstyrning. Frågan är inte bara om data får användas i ett system. Frågan är om data får användas i just detta AI-sammanhang, för detta syfte, av denna användare, med denna modell, i denna miljö och med denna loggning.

Ett praktiskt arkitekturmönster är att införa en kontextpolicy. Den beskriver vilka typer av kontext en AI-förmåga får använda:

- användarens egen information
- verksamhetsdokument med behörighetskontroll
- öppna informationskällor
- klassificerade interna källor
- personuppgifter
- sekretessreglerad information
- historiska ärenden
- loggar och tekniska data
- data från andra myndigheter eller externa parter

För varje kategori bör arkitekturen ange tillåtna användningsfall, skyddsnivå, loggningskrav, granskning, retention och om data får lämna organisationens kontrollerade miljö.

### Auktorisation måste följa med in i AI-flödet

Ett vanligt fel i AI-lösningar är att man återanvänder befintliga datakällor men inte återanvänder deras åtkomstlogik på ett tillräckligt strikt sätt. Resultatet blir att AI-förmågan tekniskt kan se mer än användaren får se.

Det räcker inte att användaren är inloggad. AI-flödet måste kontrollera vad användaren får göra i varje steg:

- vilka källor får användaren söka i?
- vilka dokument får användaren se?
- vilka fält eller datatyper får användaren använda?
- får användaren sammanställa information över flera källor?
- får användaren exportera resultat?
- får modellen anropa verktyg eller bara ge svar?
- får användaren använda AI-resultatet i beslutsnära arbete?

Detta blir särskilt viktigt vid RAG-lösningar, där modellen hämtar information från interna källor för att skapa svar. Om behörighetskontrollen sker före dokumenthämtning men inte vid sammanställning kan användaren få indirekt tillgång till information som borde varit skyddad. Om behörighetskontrollen sker i användargränssnittet men inte i API-lagret kan andra klienter kringgå skyddet.

Arkitektens princip bör vara att AI-förmågan aldrig ska öka användarens faktiska informationsbehörighet utan ett uttryckligt beslut och dokumenterat ansvar.

### Guardrails är nödvändiga men inte tillräckliga

Guardrails är skyddsmekanismer som begränsar oönskat AI-beteende. De kan vara tekniska, organisatoriska eller processuella. Exempel är innehållsfilter, policykontroller, begränsade verktygsanrop, svarsmallar, blocklistor, klassificering av användarfrågor, manuell granskning och regler för vilka processer AI får stödja.

Guardrails är viktiga, men de får inte bli en ersättning för arkitektur. En organisation som säger "vi löser det med guardrails" utan att definiera dataflöden, ansvar, loggning, modellklasser, åtkomst och eskaleringsvägar har inte byggt säkerhetsarkitektur. Den har lagt skydd ovanpå en oklar lösning.

Arkitekten bör se guardrails som en kontrollnivå bland flera:

1. **Syfteskontroll:** Är användningsfallet tillåtet?
2. **Datakontroll:** Vilka data får användas?
3. **Identitets- och åtkomstkontroll:** Vem får göra vad?
4. **Modellkontroll:** Vilken modellklass får användas?
5. **Verktygskontroll:** Vilka externa åtgärder får AI initiera?
6. **Outputkontroll:** Hur får resultatet användas?
7. **Loggning och uppföljning:** Kan händelser granskas?
8. **Incidenthantering:** Vad händer när något går fel?

Säker AI kräver lager på lager av kontroller. Ingen enskild guardrail kan bära hela ansvaret.

### AI-gateway som säkerhetskomponent

I kapitel 8 introducerades AI-gateway som ett mellanlager för AI-anrop. Ur säkerhetsperspektiv kan en AI-gateway fungera som en central kontrollpunkt mellan användare, applikationer, modeller, verktyg och datakällor.

En AI-gateway kan exempelvis hantera:

- autentisering och auktorisation för AI-anrop
- kontroll av vilken modell som får användas för vilket syfte
- filtrering eller maskning av känslig information
- policybeslut baserade på informationsklassning
- kostnads- och volymbegränsningar
- loggning av anrop, metadata och beslut
- routing mellan olika modeller eller modellklasser
- blockering av otillåtna promptar eller datatyper
- hantering av systeminstruktioner och standardiserade prompts
- stöd för utvärdering, test och incidentanalys

En AI-gateway löser inte alla säkerhetsproblem, men den kan minska risken att varje AI-lösning bygger egna kontroller. För offentlig sektor kan detta vara särskilt värdefullt eftersom gemensamma kontroller stärker spårbarhet, konsekvens och styrbarhet.

Samtidigt skapar en central gateway ett nytt kritiskt beroende. Den måste designas för robusthet, tydligt ägarskap, förändringshantering och möjlighet till granskning. Om gatewayen blir en flaskhals eller en svart låda kan den motverka sitt syfte.

### Modellmissbruk och funktionsmissbruk

AI-säkerhet handlar inte bara om externa attacker. Det handlar också om att legitima användare kan använda AI på olämpliga sätt.

En medarbetare kan mata in för känslig information i en generell AI-tjänst. En handläggare kan luta sig för tungt mot ett AI-genererat förslag. En utvecklare kan använda AI-genererad kod utan granskning. En analytiker kan skapa sammanställningar som överskrider syftet med den ursprungliga datainsamlingen. En chef kan använda AI för att prioritera ärenden utan tillräcklig transparens.

Därför behöver säkerhetsarkitekturen inkludera användningsstyrning. Det innebär att organisationen definierar vilka användningsmönster som är tillåtna, begränsade eller förbjudna. Detta bör kopplas till AI-outputklassificering:

- informativt stöd
- sammanfattande stöd
- strukturerande stöd
- rådgivande stöd
- beslutsnära stöd
- automatiserat beslut eller åtgärd

Ju närmare AI kommer faktisk påverkan på beslut, rättigheter, skyldigheter, tillsyn, resurstilldelning eller myndighetsutövning, desto starkare behöver kontrollerna vara.

### Loggning, spårbarhet och integritet

Säkerhetsarkitektur kräver loggning. Men AI-loggning är känslig. Promptar och svar kan innehålla personuppgifter, sekretess, arbetsmaterial, interna bedömningar eller känsliga metadata. Samtidigt kan organisationen behöva loggar för incidenthantering, kvalitetssäkring, revision och ansvar.

Arkitekten behöver därför utforma loggning som balanserar spårbarhet och dataminimering. Allt bör inte loggas i klartext bara för att det är tekniskt möjligt. Men det måste finnas tillräckligt med spårbarhet för att kunna förstå vad som hänt.

En användbar uppdelning är:

- **Teknisk loggning:** tidpunkt, tjänst, modell, anropsvolym, felkoder och prestanda.
- **Säkerhetsloggning:** användare, behörighet, policybeslut, blockerade anrop och avvikande mönster.
- **Kontextloggning:** vilka källor eller dokument som användes, utan att alltid lagra hela innehållet.
- **Beslutsloggning:** hur AI-resultat användes i en process och vem som gjorde den slutliga bedömningen.
- **Utvärderingsloggning:** resultat av tester, kvalitetsmätningar och återkommande kontroller.

För offentlig sektor måste loggning också kopplas till bevarande, gallring, offentlighet, sekretess, dataskydd och arkivkrav. Detta bör inte lämnas till tekniska team i efterhand. Det är en arkitekturfråga från början.

### AI-agenter och verktygsanrop höjer risknivån

När AI bara genererar text är riskerna betydande men ofta begränsade till information, rekommendation och användarbeteende. När AI får använda verktyg ökar risknivån. En AI-agent kan exempelvis söka i system, uppdatera poster, skicka meddelanden, skapa ärenden, kalla API:er eller initiera arbetsflöden.

Detta kräver en annan säkerhetsmodell. Arkitekten bör utgå från principen att en AI-agent inte ska få mer behörighet än nödvändigt och att varje verktygsanrop ska vara avgränsat, loggat och begripligt. Det bör finnas skillnad mellan att föreslå en åtgärd och att utföra den.

Viktiga kontrollfrågor är:

- Har agenten egen identitet eller agerar den som användaren?
- Hur syns det i loggar att en åtgärd initierades av AI?
- Krävs mänskligt godkännande för vissa åtgärder?
- Kan agenten kombinera verktyg på oväntade sätt?
- Finns begränsningar för volym, tid, transaktioner och datatyper?
- Kan agentens verktygsåtkomst återkallas snabbt?
- Finns separata miljöer för test, pilot och produktion?

Agentiska lösningar bör sällan införas direkt i kritiska offentliga processer utan tydliga stoppregler och stegvis mognad.

## Scenario eller beslutskontext

En myndighet vill införa en intern AI-assistent för handläggare. Assistenten ska kunna söka i vägledningar, interna rutiner och tidigare ärenden samt hjälpa till att sammanfatta relevanta underlag. Målet är att minska tid för informationssökning och öka likformigheten i bedömningar.

Vid första anblick verkar lösningen relativt ofarlig. AI:n ska inte fatta beslut. Den ska bara hjälpa handläggare att hitta och sammanfatta information. Men säkerhetsarkitekten identifierar flera frågor:

- Innehåller tidigare ärenden personuppgifter eller sekretessreglerad information?
- Får alla handläggare söka i alla tidigare ärenden?
- Kan AI:n sammanställa mönster som en handläggare normalt inte skulle se?
- Hur markeras skillnaden mellan gällande vägledning och historiska bedömningar?
- Vad händer om ett dokument innehåller instruktioner som försöker påverka AI:n?
- Loggas vilka källor som användes för ett svar?
- Kan ett AI-genererat svar kopieras direkt in i ett beslutsunderlag?
- Vem ansvarar för felaktiga eller missvisande sammanfattningar?

Beslutet blir att assistenten får införas stegvis. Första versionen begränsas till kvalitetssäkrade vägledningar och rutindokument. Tidigare ärenden används inte förrän åtkomst, maskning, kontextpolicy och loggning är lösta. AI-output klassificeras som informativt och sammanfattande stöd, inte beslutsnära stöd. Alla svar måste visa källhänvisningar och en tydlig markering om att handläggaren ansvarar för bedömningen.

Poängen är inte att undvika AI. Poängen är att arkitekturen begränsar risknivån till det organisationen kan styra.

## Strategiska vägval och arkitektöverväganden

### Centraliserade säkerhetskontroller eller lokala lösningar

Ett centralt vägval är om AI-säkerhet ska hanteras genom gemensamma plattformskontroller eller byggas in separat i varje lösning.

Centraliserade kontroller, exempelvis via AI-gateway, gemensamma policyer och standardiserad loggning, ger konsekvens och styrbarhet. De gör det lättare att följa upp användning, införa gemensamma regler och hantera leverantörsbyten. Nackdelen är att centralisering kan bli långsam, tung och svår att anpassa till lokala behov.

Lokala kontroller ger flexibilitet. Team kan snabbare anpassa skydd till specifika användningsfall. Nackdelen är fragmentering: olika tolkningar av säkerhet, varierande loggning, svårare revision och risk för att pilotlösningar blir permanenta utan tillräcklig styrning.

För offentlig sektor är ofta en hybrid lämplig: centrala minimikrav och gemensamma kontrollpunkter, men lokal riskanalys och anpassning inom tydliga ramar.

### Blockera, tillåta eller differentiera AI-användning

En organisation kan reagera på AI-risker genom att blockera bred användning, tillåta allt med riktlinjer eller differentiera användning efter risk. Det sista är oftast mest arkitekturellt hållbart.

Differentiering innebär att AI-användning delas in efter informationsklass, syfte, modellklass och påverkan. Exempelvis kan allmän textbearbetning med öppna data vara tillåten i breda verktyg, medan sekretessnära analys kräver kontrollerad miljö, särskild modellklass, loggning och godkända datakällor.

Arkitekten bör undvika både naiv öppenhet och generell rädsla. Frågan är inte "AI eller inte AI", utan "vilken AI-användning är lämplig under vilka kontroller?"

### Extern AI-tjänst eller kontrollerad intern miljö

Externa AI-tjänster kan ge snabb tillgång till avancerad funktionalitet, men de kräver tydliga bedömningar av datahantering, avtal, jurisdiktion, loggning, leverantörsstyrning och exit. En kontrollerad intern miljö kan ge bättre styrning men kräver mer kompetens, plattformskapacitet och livscykelansvar.

Arkitekten bör koppla valet till informationsklassning och syfte. Lågkänsliga interna produktivitetsstöd kan ha en annan lösning än AI i myndighetsnära processer. Strategiskt bör organisationen undvika att alla användningsfall pressas in i samma säkerhetsmodell.

### Automatiska åtgärder eller mänskligt godkännande

När AI integreras med verktyg uppstår frågan om AI får utföra åtgärder eller bara föreslå dem. I offentlig sektor bör automatiska åtgärder kräva särskild analys, särskilt när åtgärden påverkar individers rättigheter, ärenden, register, kommunikation eller resursfördelning.

Ett praktiskt mönster är stegvis autonomi:

1. AI ger information.
2. AI sammanfattar underlag.
3. AI föreslår åtgärd.
4. AI förbereder åtgärd som människa godkänner.
5. AI utför begränsad åtgärd inom tydliga regler.
6. AI utför automatiserad åtgärd med efterhandskontroll.

Varje steg kräver starkare kontroller, tydligare ansvar och mer robust uppföljning.

### Hur mycket ska loggas?

För lite loggning gör incidenter, fel och missbruk svåra att utreda. För mycket loggning kan skapa nya risker, särskilt om känsliga promptar och svar sparas brett. Arkitekten måste därför definiera loggningsnivåer.

En enkel princip är att loggning ska vara proportionerlig mot risk. Högre risk kräver mer spårbarhet, men också bättre skydd för loggarna. Låg risk kan ofta hanteras med teknisk och statistisk loggning. Beslutsnära eller känsliga AI-förmågor kan kräva källspårning, policybeslut, användningssyfte och manuell ansvarspunkt.

## Vanliga felsatsningar

- **Felsatsning:** Man behandlar AI-säkerhet som vanlig applikationssäkerhet.
  - **Varför det händer:** Organisationen utgår från befintliga säkerhetsprocesser och missar att instruktioner, kontext och modellbeteende också behöver skyddas.
  - **Hur arkitekten kan undvika det:** Komplettera traditionell hotmodellering med AI-specifika risker som prompt injection, otillåten kontext, hallucinerade svar, modellmissbruk och agentiska verktygsanrop.

- **Felsatsning:** AI får bred åtkomst till data "för att ge bättre svar".
  - **Varför det händer:** Nyttan med AI upplevs öka när modellen får mer kontext, men åtkomstlogik och informationsklassning följer inte alltid med.
  - **Hur arkitekten kan undvika det:** Inför kontextpolicy, behörighetsstyrd dokumenthämtning och principen att AI inte ska utöka användarens faktiska informationsbehörighet.

- **Felsatsning:** Organisationen litar för mycket på guardrails.
  - **Varför det händer:** Guardrails marknadsförs ofta som en snabb lösning på komplexa risker.
  - **Hur arkitekten kan undvika det:** Behandla guardrails som en kontrollnivå bland flera och komplettera med dataarkitektur, åtkomstkontroll, loggning, modellklassning och användningsstyrning.

- **Felsatsning:** AI-piloter saknar incident- och avvecklingsplan.
  - **Varför det händer:** Piloter drivs som innovationsexperiment snarare än som början på en förvaltningsbar AI-förmåga.
  - **Hur arkitekten kan undvika det:** Kräv stoppregler, ansvarig ägare, incidentväg, loggning och exit även för pilotlösningar.

- **Felsatsning:** Agentiska funktioner införs innan organisationen har kontroll över enklare AI-flöden.
  - **Varför det händer:** Möjligheten att låta AI "göra saker" uppfattas som nästa naturliga steg.
  - **Hur arkitekten kan undvika det:** Inför stegvis autonomi och kräv tydlig gräns mellan rekommendation, förberedelse och faktisk åtgärd.

## Arkitektens checklista

- Är AI-förmågans syfte, användningsområde och risknivå tydligt definierade?
- Vilken informationsklassning gäller för de data som används som prompt, kontext, källa, logg och utdata?
- Följer användarens befintliga behörigheter med in i AI-flödet?
- Finns en kontextpolicy som anger vilka källor AI får använda och under vilka villkor?
- Är prompt injection och manipulation via hämtade dokument beaktade i hotmodellen?
- Finns en AI-gateway eller annan kontrollpunkt för policy, loggning, modellval och åtkomst?
- Är det tydligt vilken modellklass som får användas för respektive användningsfall?
- Är guardrails dokumenterade som kontroller, inte som ersättning för arkitektur?
- Är loggning utformad så att både spårbarhet och dataminimering hanteras?
- Finns regler för hur AI-output får användas i beslutsnära processer?
- Finns mänskligt godkännande för åtgärder med hög påverkan?
- Är leverantörens databehandling, lagring, träning, supportåtkomst och jurisdiktion bedömd?
- Finns incidentprocess för felaktiga svar, dataläckage, missbruk och policybrott?
- Kan AI-förmågan stängas av, begränsas eller byta modell utan orimlig verksamhetspåverkan?
- Är säkerhetskraven verifierbara vid upphandling, införande och löpande förvaltning?

## Snabb sammanfattning

- AI förändrar säkerhetsytan genom att instruktioner, kontext, modellbeteende, verktygsanrop och utdata blir delar av riskbilden.
- Säkerhetsarkitektur för AI måste bygga vidare på dataarkitektur, integrationsarkitektur och modellstrategi.
- Prompt injection, dataläckage, otillåten kontext, svag auktorisation och modellmissbruk kräver särskilda kontroller.
- Guardrails är viktiga men otillräckliga om de inte kombineras med tydlig arkitektur, loggning, åtkomstkontroll och governance.
- AI-gateway kan fungera som en central säkerhetskomponent, men måste själv designas som kritisk infrastruktur.
- För offentlig sektor är kopplingen mellan säkerhet, rättssäkerhet, informationsklassning, tillit och ansvar avgörande.
- Ju närmare AI kommer beslut och åtgärder, desto starkare behöver kontroll, spårbarhet och mänskligt ansvar vara.

## Reflektionsfrågor

1. Vilka AI-användningsfall i den egna organisationen innebär störst risk för otillåten kontextanvändning eller dataläckage?
2. Var i organisationens arkitektur skulle en AI-gateway eller motsvarande kontrollpunkt ge mest nytta?
3. Vilka typer av AI-output bör aldrig få användas beslutsnära utan mänsklig granskning?
4. Hur skiljer sig säkerhetskraven mellan en intern AI-assistent, ett AI-baserat beslutsstöd och en AI-agent som kan utföra åtgärder?
5. Vilka loggar behövs för ansvar och revision, och vilka loggar skulle i sig skapa nya integritets- eller sekretessrisker?
6. Vilka AI-risker hanteras redan av befintliga säkerhetsprocesser, och vilka kräver nya arbetssätt?

## Nästa steg

Det här kapitlet har behandlat säkerhetsarkitektur som en förutsättning för ansvarsfull AI. Nästa kapitel flyttar fokus från enskilda arkitekturella kontrollpunkter till hur organisationen bygger långsiktig AI-förmåga. Där blir frågan hur AI går från pilot och projekt till förvaltad kapacitet med drift, förbättring, ansvar, mätning och avveckling.

Säkerhet är en central del av den övergången. En AI-förmåga som inte kan säkras, följas upp och avvecklas är inte mogen för långsiktig användning i offentlig sektor.
