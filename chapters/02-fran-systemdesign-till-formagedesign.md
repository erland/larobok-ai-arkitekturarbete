# Kapitel 2: Från systemdesign till förmågedesign

## Varför detta kapitel finns

Traditionell IT-arkitektur har ofta haft systemet som sin naturliga utgångspunkt. Arkitekten beskriver applikationer, integrationer, informationsobjekt, tekniska plattformar, gränssnitt och beroenden. Det är fortfarande nödvändigt. Men när AI blir en del av offentlig sektors digitalisering räcker det inte att fråga: ”Vilket system ska vi bygga eller köpa?”

Den mer strategiska frågan blir: ”Vilken verksamhetsförmåga behöver stärkas, och vilken roll bör AI spela i den förmågan?”

Detta skifte är centralt. AI skapar sällan värde isolerat. En modell, en chatbot, en klassificeringsfunktion eller en prediktiv komponent är inte i sig en förmåga. Värdet uppstår först när AI kopplas till rätt data, rätt process, rätt ansvar, rätt beslutssituation, rätt uppföljning och rätt styrning. Därför behöver IT-arkitekten kunna röra sig från systemdesign till förmågedesign.

I offentlig sektor är detta särskilt viktigt. En digital tjänst är inte bara en teknisk lösning. Den är ofta en del av myndighetsutövning, service, tillsyn, handläggning, beslutsstöd eller samhällskritisk verksamhet. Om AI införs utan att förmågan förstås riskerar organisationen att optimera fel sak: snabbare ärendehantering men svagare rättssäkerhet, bättre självservice men sämre tillgänglighet, automatiserad analys men oklart ansvar.

Kapitel 1 introducerade tre perspektiv på AI: AI som arbetsverktyg, AI som systemkomponent och AI som strategisk förändringskraft. Detta kapitel fördjupar det tredje perspektivet. Det visar hur arkitekten kan använda förmågedesign för att placera AI i rätt sammanhang innan tekniska lösningar väljs.

## Lärandemål

Efter kapitlet ska läsaren kunna:

- förklara skillnaden mellan systemdesign och förmågedesign i en AI-kontext
- beskriva hur AI kan påverka verksamhetsförmågor, beslutspunkter och värdeflöden
- identifiera när AI bör betraktas som en stödjande komponent och när AI förändrar själva förmågan
- resonera om arkitekturval utifrån ansvar, data, process, styrning och långsiktig förvaltning
- använda förmågekartor som stöd för AI-prioritering och strategiska vägval

## Innan vi börjar

I föregående kapitel definierades en AI-förmåga som en kombination av data, modeller, integrationer, processer, kontroller, ansvar och uppföljning som gör AI användbar i ett specifikt syfte. Den definitionen är viktig här.

En AI-förmåga är bredare än ett AI-system. Den omfattar även allt runt omkring tekniken: vem som äger syftet, vilken data som används, hur resultat tolkas, hur fel upptäcks, hur medborgare eller medarbetare påverkas, och hur organisationen vet att lösningen fortsätter vara lämplig över tid.

Detta kapitel introducerar tre nya huvudbegrepp:

- **Capability architecture:** arkitektur som beskriver vilka verksamhetsförmågor organisationen behöver och hur dessa stöds av processer, information, teknik, kompetens och styrning.
- **Decision intelligence:** strukturerat arbete med hur beslut fattas, förbättras, automatiseras eller stöds med data, analys och AI.
- **Value stream:** ett värdeflöde som visar hur värde skapas från behov till resultat, exempelvis från en ansökan till ett beslut, från en felanmälan till åtgärd, eller från upptäckt risk till tillsynsinsats.

Begreppen är användbara eftersom AI ofta påverkar just förmågor, beslut och värdeflöden snarare än bara enskilda system.

## Huvudförklaring

### Systemdesign börjar i lösningen

Systemdesign behövs för att skapa fungerande lösningar. Den svarar på frågor som:

- Vilka komponenter ingår?
- Hur ska systemen integreras?
- Vilka datamodeller används?
- Vilka gränssnitt behövs?
- Hur uppfylls krav på säkerhet, prestanda och tillgänglighet?
- Hur ska lösningen förvaltas?

Detta är kärnfrågor för IT-arkitektur. Problemet uppstår när systemdesign blir den första och dominerande linsen för AI-satsningar.

Om organisationen börjar med frågan ”Vilken AI-lösning ska vi införa?” riskerar diskussionen att snabbt bli produkt-, plattforms- eller leverantörsdriven. Det kan leda till att tekniken får en roll innan verksamhetens behov är tillräckligt förstått.

Exempel på systemdrivna frågor är:

- Ska vi införa en intern AI-assistent?
- Ska vi använda en kommersiell språkmodell?
- Ska vi bygga en egen modell?
- Ska vi skapa en central AI-plattform?
- Ska vi automatisera en viss typ av ärende?

Alla dessa frågor kan vara relevanta. Men de bör inte vara startpunkten. Startpunkten bör vara vilken förmåga som ska stärkas och vilka beslut eller arbetsmoment som är strategiskt viktiga.

### Förmågedesign börjar i verksamhetens kapacitet

Förmågedesign utgår från vad organisationen behöver kunna göra. En verksamhetsförmåga är relativt stabil över tid, även när processer, system och organisation förändras. En kommun behöver till exempel kunna hantera ansökningar, ge stöd till invånare, planera resurser, följa upp kvalitet, hantera avvikelser och samverka med andra aktörer. En myndighet behöver kunna utreda, besluta, informera, följa upp, utöva tillsyn och utveckla regelverk eller tjänster.

När AI diskuteras utifrån förmågor förändras frågorna:

- Vilken förmåga är strategiskt viktig att stärka?
- Vilka beslut inom förmågan är svåra, långsamma, riskfyllda eller kostsamma?
- Var finns återkommande mönster som AI kan hjälpa till att upptäcka?
- Vilka dataförutsättningar finns?
- Vilket ansvar får inte bli otydligt?
- Vilka delar bör automatiseras, vilka bör stödjas och vilka bör förbli mänskliga?
- Hur påverkas rättssäkerhet, transparens och tillit?

Detta gör arkitekturarbetet mer strategiskt. Arkitekten blir inte bara den som beskriver lösningen, utan den som hjälper organisationen förstå var AI hör hemma i helheten.

### Förmågekartan som AI-kompass

En förmågekarta beskriver organisationens centrala förmågor. Den är inte en processkarta och inte en systemkarta, även om den kan kopplas till båda. Dess styrka är att den ger ett relativt stabilt språk för att diskutera prioriteringar.

I AI-eran kan förmågekartan användas som en kompass för att undvika lösningsjakt. I stället för att samla idéer som ”vi borde ha en chatbot” eller ”vi borde automatisera dokumentanalys” kan organisationen fråga:

- Vilka förmågor har störst verksamhetsmässig betydelse?
- Vilka förmågor har störst problem med kapacitet, kvalitet eller ledtid?
- Vilka förmågor är datamogna nog för AI-stöd?
- Vilka förmågor är för känsliga för hög grad av automation?
- Vilka förmågor kräver särskild transparens och mänsklig kontroll?
- Vilka förmågor skulle påverkas mest av bättre prognoser, klassificering, sammanfattning eller beslutsstöd?

Detta skapar en mer balanserad AI-portfölj. Organisationen kan skilja mellan sådant som är lämpligt för experiment, sådant som kräver stark styrning, och sådant som bör avstås tills ansvar, data och juridiska förutsättningar är tydligare.

### AI förändrar beslutspunkter

Många AI-satsningar handlar egentligen om beslut. Det kan vara formella beslut, som myndighetsbeslut, men också informella beslut: prioriteringar, bedömningar, urval, rekommendationer, riskindikatorer, hänvisningar och kvalitetskontroller.

Decision intelligence hjälper arkitekten att analysera dessa beslut. I stället för att bara fråga om ett arbetsmoment kan automatiseras bör arkitekten fråga:

- Vilket beslut påverkas?
- Vem fattar beslutet i dag?
- Vilken information används?
- Vilka fel kan uppstå?
- Vad händer om AI påverkar beslutet?
- Behöver beslutet kunna förklaras i efterhand?
- Är AI ett stöd, en rekommendation, en automatisk åtgärd eller bara en informationskälla?
- Vem ansvarar när beslutet blir fel?

I offentlig sektor är detta avgörande. Även när AI inte fattar ett formellt beslut kan den påverka beslutsunderlaget. Om en AI-assistent sammanfattar ärenden, rangordnar risker eller föreslår svar kan den i praktiken styra uppmärksamhet och tolkning. Arkitekturen behöver därför beskriva inte bara tekniska dataflöden utan även beslutspåverkan.

### Värdeflödet visar var AI kan göra nytta

Ett värdeflöde beskriver hur ett behov blir ett resultat. För offentlig sektor kan värdeflöden handla om service till medborgare, handläggning, tillsyn, vårdflöden, utbildningsstöd, informationsförsörjning eller intern styrning.

AI kan påverka ett värdeflöde på flera sätt:

- före flödet, genom prognoser och behovsanalys
- tidigt i flödet, genom vägledning, sortering eller kompletteringskontroll
- mitt i flödet, genom beslutsstöd, analys eller sammanfattning
- sent i flödet, genom kvalitetskontroll, uppföljning eller avvikelseanalys
- efter flödet, genom lärande, förbättring och återkoppling

För arkitekten är det viktigt att inte bara identifiera var AI kan sättas in, utan också vad det gör med hela flödet. En förbättring i ett steg kan skapa flaskhalsar eller risker i ett annat. Om AI snabbar upp inkommande ärenden men inte förändrar beslutskapaciteten kan köer flyttas snarare än lösas. Om AI förbättrar självservice men gör det svårare att nå en människa kan tillgängligheten försämras för vissa grupper. Om AI identifierar fler risker än organisationen kan hantera skapas en styrningsfråga, inte bara en teknisk fråga.

### AI som stödjande komponent eller förmågeförändring

Ett centralt vägval är om AI endast stödjer en befintlig förmåga eller om AI förändrar förmågan i grunden.

AI som stödjande komponent kan till exempel vara:

- sammanfattning av interna dokument
- sökstöd i kunskapsmaterial
- språkstöd för medarbetare
- klassificering av inkommande ärenden
- förslag på kompletteringar
- tekniskt stöd för arkitekturdokumentation

Här är förmågan i stort sett densamma, men vissa moment blir effektivare eller mer konsekventa.

AI som förmågeförändring kan till exempel vara:

- riskbaserad tillsyn där AI påverkar prioritering av insatser
- proaktiv service där organisationen identifierar behov innan medborgaren ansöker
- prediktiv resursplanering som förändrar styrmodellen
- automatiserad kvalitetskontroll som förändrar ansvarsfördelning
- AI-stödd beslutsberedning som ändrar hur handläggning organiseras

Här påverkas förmågans logik. Processer, roller, ansvar, kontroller och styrning behöver omprövas.

Arkitekten bör vara särskilt uppmärksam när AI flyttar från stödjande komponent till förmågeförändring utan att organisationen märker det. Det kan ske gradvis. En enkel sammanfattningsfunktion kan börja användas som beslutsunderlag. En klassificering kan börja styra prioritering. Ett rekommendationsstöd kan i praktiken bli normerande. Då krävs starkare governance.

## Scenario eller beslutskontext

En offentlig organisation vill använda AI för att förbättra hantering av inkommande ärenden. Det första förslaget är att införa en AI-tjänst som klassificerar ärenden och föreslår nästa steg.

En systemdriven ansats skulle snabbt gå till frågor om modellval, integration med ärendehanteringssystemet, API:er, säkerhet och användargränssnitt. Det är viktiga frågor, men de är inte tillräckliga.

En förmågedriven ansats börjar i stället med förmågan ”hantera inkommande ärenden”. Arkitekten analyserar:

- vilka typer av ärenden som kommer in
- vilka beslutspunkter som finns i flödet
- vilka klassificeringar som påverkar rättigheter, prioritet eller handläggningstid
- vilken data som används för att klassificera
- hur felaktig klassificering upptäcks
- vem som ansvarar för korrigering
- om medborgaren behöver informeras om AI-stödet
- hur lösningen följs upp över tid
- hur den påverkar arbetsfördelning och kompetensbehov

Resultatet kan bli att AI är lämpligt för vissa delar men inte andra. Organisationen kan till exempel använda AI för att föreslå kompletteringar och hitta liknande ärenden, men avstå från automatiserad prioritering tills konsekvenserna är bättre förstådda. Arkitekturen blir då mer nyanserad än ”inför AI i ärendehanteringen”.

Det viktiga är inte att AI används maximalt. Det viktiga är att AI används där den stärker förmågan utan att skapa oacceptabla risker.

## Strategiska vägval och arkitektöverväganden

### Vägval 1: Systemoptimering eller förmågeoptimering

**Systemoptimering** fokuserar på att förbättra ett enskilt system eller en avgränsad process. Det kan ge snabb nytta, särskilt när problemen är tydliga och avgränsade.

**Förmågeoptimering** fokuserar på hela verksamhetsförmågan, inklusive process, data, ansvar, styrning och flera system. Det är ofta långsammare i början men ger bättre strategisk riktning.

Arkitekten bör fråga:

- Är problemet lokalt eller tvärgående?
- Förbättrar AI endast ett system, eller påverkar den hela förmågan?
- Finns risk att en lokal optimering försämrar helheten?
- Behöver lösningen samordnas med målarkitektur, portföljstyrning eller informationsstyrning?

I offentlig sektor bör förmågeoptimering ofta vara huvudperspektivet när AI påverkar beslut, prioriteringar, tillgång till service eller myndighetsutövning.

### Vägval 2: Automatisera beslut eller stödja beslut

AI kan användas för att automatisera, rekommendera, prioritera, sammanfatta eller kvalitetssäkra. Dessa nivåer har olika konsekvenser.

Automatisering kan vara motiverad när besluten är enkla, reglerna tydliga, riskerna låga och uppföljningen stark. Beslutsstöd är ofta lämpligare när bedömningen kräver kontext, ansvar, proportionalitet eller mänskligt omdöme.

Arkitekten bör fråga:

- Är beslutet formellt eller informellt?
- Påverkas individers rättigheter, skyldigheter eller tillgång till service?
- Kan beslutet förklaras och granskas?
- Finns mänsklig kontroll som är verklig, inte bara formell?
- Vad händer vid felaktiga rekommendationer?
- Hur mäts kvalitet över tid?

Ett vanligt misstag är att kalla något ”bara stöd” trots att det i praktiken styr beslut. Arkitekturen bör därför beskriva faktisk beslutspåverkan, inte bara avsedd funktion.

### Vägval 3: Central prioritering eller lokal innovation

En central AI-portfölj kan ge styrning, återanvändning, säkerhet och kostnadskontroll. Lokal innovation kan ge snabbare lärande och bättre verksamhetsnära lösningar.

Arkitekten bör inte välja det ena helt på bekostnad av det andra. Ett mer robust mönster är central styrning av principer, plattformar, riskklassning och gemensamma kontroller, kombinerat med lokal identifiering av behov och experiment inom tydliga ramar.

Frågor att ställa:

- Vilka AI-förmågor är strategiskt gemensamma?
- Vilka bör utvecklas nära verksamheten?
- Vilka beslut kräver central arkitekturgranskning?
- Vilka komponenter bör återanvändas?
- Hur undviks skugg-AI och okontrollerade lokala lösningar?
- Hur fångas lärdomar från lokala initiativ in i den gemensamma arkitekturen?

### Vägval 4: Förmågekarta som styrinstrument eller dokumentation

En förmågekarta kan vara ett levande styrinstrument eller en statisk dokumentationsprodukt. I AI-eran bör den vara ett styrinstrument.

Det innebär att förmågekartan används för att:

- prioritera AI-initiativ
- identifiera datamognad
- se beroenden mellan förmågor
- bedöma risk och samhällsvärde
- planera investeringar
- följa upp portföljen
- koppla AI-initiativ till målarkitektur

Om förmågekartan bara beskriver nuläget blir den snabbt passiv. Om den kopplas till beslut blir den ett verktyg för styrning.

### Vägval 5: AI som effektivisering eller AI som omformning

AI kan användas för att göra befintliga arbetssätt snabbare. Det kan också användas för att omforma hur verksamheten skapar värde.

Effektivisering är ofta enklare att motivera. Den passar när befintliga processer är ändamålsenliga men tunga, repetitiva eller informationsintensiva.

Omformning är mer strategiskt men också mer riskfyllt. Den passar när verksamheten behöver förändra sin kapacitet, exempelvis från reaktiv till proaktiv service eller från manuell uppföljning till kontinuerlig riskanalys.

Arkitekten bör fråga:

- Är dagens process värd att effektivisera?
- Riskerar AI att cementera ett föråldrat arbetssätt?
- Kräver nyttan förändrade roller, styrning eller ansvar?
- Vilka förmågor behöver byggas upp innan omformning är möjlig?
- Hur säkerställs att offentlig värdegrund, likabehandling och rättssäkerhet stärks snarare än försvagas?

## Vanliga felsatsningar

### Felsatsning 1: Att börja med verktyget

**Varför det händer:** AI-marknaden, interna förväntningar och ledningens intresse gör att diskussionen snabbt handlar om produkter, modeller och plattformar.

**Hur arkitekten kan undvika det:** Förankra varje AI-initiativ i en verksamhetsförmåga, ett värdeflöde och en beslutssituation. Kräv att problemet beskrivs innan lösningen diskuteras.

### Felsatsning 2: Att behandla AI som ett vanligt systeminförande

**Varför det händer:** Organisationen använder etablerade projektmodeller och upphandlingsmönster som passar traditionella system men inte adaptiva AI-förmågor.

**Hur arkitekten kan undvika det:** Beskriv AI som en livscykelförmåga med kontinuerlig uppföljning, datastyrning, modell- eller tjänsteuppdateringar, ansvar och avvecklingskriterier.

### Felsatsning 3: Att underskatta beslutspåverkan

**Varför det händer:** Lösningen beskrivs som stödjande och därför antas riskerna vara begränsade.

**Hur arkitekten kan undvika det:** Kartlägg faktisk påverkan på beslut, prioriteringar och uppmärksamhet. Bedöm hur användare sannolikt kommer att förlita sig på AI-stödet i praktiken.

### Felsatsning 4: Att optimera ett steg men försämra helheten

**Varför det händer:** Ett AI-initiativ mäts på lokal effektivitet, exempelvis snabbare sortering eller kortare svarstid.

**Hur arkitekten kan undvika det:** Analysera hela värdeflödet. Säkerställ att förbättringen inte skapar nya flaskhalsar, sämre kvalitet eller otydligt ansvar längre fram.

### Felsatsning 5: Att skapa förmågor utan ägare

**Varför det händer:** AI-initiativ startar som experiment och får inte tydlig organisatorisk hemvist.

**Hur arkitekten kan undvika det:** Definiera ansvarskedjan tidigt: syfte, data, modell eller tjänst, integration, användning, uppföljning, risk, incidenthantering och avveckling.

## Arkitektens checklista

Använd checklistan när ett AI-initiativ diskuteras eller när en målarkitektur ska ta höjd för AI.

### Förmåga och syfte

- Vilken verksamhetsförmåga ska stärkas?
- Är problemet tydligt beskrivet utan att lösningen redan är förutbestämd?
- Är nyttan kopplad till offentligt värde, inte bara intern effektivitet?
- Finns en tydlig koppling till strategi, målarkitektur eller portföljprioritering?

### Beslut och ansvar

- Vilka beslutspunkter påverkas?
- Är AI ett stöd, en rekommendation, en prioritering eller en automatiserad åtgärd?
- Vem ansvarar för beslut som påverkas av AI?
- Finns spårbarhet från AI-resultat till mänsklig åtgärd?
- Kan fel upptäckas, korrigeras och följas upp?

### Data och informationsstyrning

- Vilka data krävs?
- Är datakvalitet, metadata och informationsägarskap tillräckligt tydliga?
- Finns begränsningar kopplade till informationsklassning, sekretess eller personuppgifter?
- Behöver data delas mellan organisationer eller system?
- Finns risk att AI skapar nya inofficiella informationsflöden?

### Värdeflöde och process

- Var i värdeflödet sätts AI in?
- Skapar AI nytta i helheten eller bara i ett enskilt steg?
- Finns risk att flaskhalsar flyttas?
- Påverkas roller, kompetens eller arbetsfördelning?
- Finns plan för förändringsledning?

### Styrning och förvaltning

- Vem äger AI-förmågan över tid?
- Hur följs kvalitet, risk och nytta upp?
- Finns kriterier för när lösningen ska ändras, pausas eller avvecklas?
- Är lösningen förenlig med arkitekturprinciper?
- Behövs central granskning eller särskild governance?

### Offentlig sektors särskilda villkor

- Påverkas rättssäkerhet, likabehandling eller transparens?
- Kan medborgare, företag eller medarbetare förstå hur AI används?
- Finns behov av särskilda kontroller för sårbara grupper?
- Är lösningen möjlig att upphandla, förvalta och granska över tid?
- Skapas beroenden som påverkar digital suveränitet?

## Snabb sammanfattning

- AI bör inte främst förstås som ett nytt system, utan som något som kan förändra verksamhetsförmågor.
- Systemdesign behövs, men bör komma efter att förmåga, värdeflöde och beslutspunkter har förståtts.
- Förmågekartor kan användas som strategiskt styrinstrument för AI-prioritering.
- Decision intelligence hjälper arkitekten analysera hur AI påverkar beslut, ansvar och kvalitet.
- Ett AI-initiativ kan vara en stödjande komponent eller en faktisk förmågeförändring.
- I offentlig sektor måste förmågedesign väga in rättssäkerhet, transparens, ansvar, informationsstyrning och långsiktig förvaltning.
- Arkitektens viktigaste bidrag är att hålla ihop teknikval med verksamhetsnytta, ansvar och offentlig legitimitet.

## Reflektionsfrågor

1. Vilka AI-idéer i din organisation är formulerade som lösningar snarare än som förmågebehov?
2. Vilka verksamhetsförmågor skulle påverkas mest av bättre analys, klassificering, prognoser eller sammanfattning?
3. Finns det beslutspunkter där AI redan påverkar arbetet informellt, utan att detta syns i arkitekturen?
4. Vilka förmågor är inte mogna för AI på grund av bristande data, otydligt ansvar eller svag styrning?
5. Var finns risken att organisationen effektiviserar ett steg i ett värdeflöde men försämrar helheten?
6. Vilka AI-förmågor bör styras centralt och vilka bör utvecklas närmare verksamheten?

## Nästa steg

Detta kapitel har flyttat fokus från system till förmågor, värdeflöden och beslut. Nästa kapitel går från organisationens förmågor till arkitektens eget arbete. Där behandlas hur AI kan bli en medskapare i analys, dokumentation, modellering och beslutsberedning, och vad arkitekten behöver göra för att AI-stödet inte ska ersätta mänskligt omdöme med oreflekterad automation.
