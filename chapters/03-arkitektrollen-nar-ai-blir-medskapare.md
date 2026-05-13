# Kapitel 3: Arkitektrollen när AI blir medskapare

## Varför detta kapitel finns

AI förändrar inte bara vilka lösningar IT-arkitekter behöver ta ställning till. AI förändrar också hur arkitekturarbetet utförs. En arkitekt kan i dag använda AI-stöd för att sammanfatta komplex dokumentation, identifiera luckor i kravbilder, föreslå alternativa arkitekturmönster, formulera beslutsunderlag, granska konsekvenser och skapa första versioner av modeller, principer och texter.

Det betyder inte att AI ersätter arkitektens omdöme. Snarare flyttas en del av arkitektens värde från att producera material till att formulera rätt frågor, bedöma kvaliteten i svaren, sätta in resultaten i verksamhetens kontext och ta ansvar för vilka beslut som faktiskt förs vidare. Arkitekten blir mer av en kvalificerad kurator, kritisk granskare och strategisk översättare mellan verksamhet, teknik, data, juridik, säkerhet och styrning.

I offentlig sektor är detta särskilt viktigt. Arkitekturbeslut påverkar ofta rättssäkerhet, transparens, informationshantering, upphandling, långsiktig förvaltningsbarhet och medborgarnas förtroende. Ett AI-genererat underlag kan vara snabbt och välformulerat men ändå bygga på fel antaganden, föråldrad information eller otillräcklig förståelse för ansvar och regelverk. Därför måste arkitekten kunna använda AI som medskapare utan att låta AI bli en obemärkt beslutsfattare.

Kapitlet behandlar hur arkitektrollen förändras när AI blir en del av det dagliga arkitekturarbetet: från analys och dokumentation till modellering, kravarbete och beslutsberedning.

## Lärandemål

Efter kapitlet ska läsaren kunna:

- skilja mellan AI som produktivitetsstöd, analysstöd och beslutsstöd i arkitekturarbetet
- bedöma vilka delar av arkitektens arbete som lämpar sig för AI-stöd och vilka som kräver särskild mänsklig granskning
- beskriva hur kvalitetssäkring, spårbarhet och ansvar bör utformas när AI används i arkitekturarbete
- identifiera risker med AI-genererade arkitekturunderlag, exempelvis falsk precision, osynliga antaganden och bristande kontext
- formulera principer för ansvarsfull användning av AI i arkitekturforum och beslutsprocesser

## Innan vi börjar

I kapitel 1 beskrevs AI på tre nivåer: som arbetsverktyg, som systemkomponent och som strategisk förändringskraft. Detta kapitel fördjupar den första nivån: AI som arbetsverktyg för arkitekten.

I kapitel 2 flyttades fokus från systemdesign till förmågedesign. Där blev poängen att AI inte bör börja med en teknisk lösning, utan med frågan vilken verksamhetsförmåga som ska stärkas. Samma princip gäller när AI används i arkitektens egen arbetsprocess. AI bör inte införas för att det går att automatisera textproduktion, utan för att det stärker arkitektens förmåga att analysera, se samband, pröva alternativ och skapa bättre beslutsunderlag.

Tre begrepp introduceras i detta kapitel:

- **AI-augmented architecture:** arkitekturarbete där AI används för att förstärka arkitektens analys, dokumentation, modellering eller beslutsberedning.
- **Promptad analys:** ett arbetssätt där arkitekten styr AI genom tydliga frågor, avgränsningar, roller, kriterier och kontext.
- **Mänskligt ansvar:** principen att ansvar för arkitekturbeslut, riskbedömning och rekommendationer inte kan delegeras till AI.

## Huvudförklaring

### Från dokumentproducent till omdömesbärare

Traditionellt har mycket arkitekturarbete varit beroende av arkitektens förmåga att skapa dokumentation: målarkitekturer, nulägesbeskrivningar, principer, beslutsunderlag, beroendekartor, konsekvensanalyser och rekommendationer. Dokumentationen har varit viktig eftersom den gör resonemang synliga och möjliga att förankra.

När AI kan producera välformulerade texter på kort tid förändras detta. Själva textproduktionen blir mindre unik. Det betyder inte att dokumentation blir oviktig, men det förändrar var kvaliteten uppstår. Kvaliteten ligger inte längre främst i att kunna skriva ett dokument från början till slut. Den ligger i att kunna avgöra:

- om frågan är rätt ställd
- om underlaget bygger på rätt kontext
- om viktiga perspektiv saknas
- om resonemanget är spårbart
- om rekommendationen är rimlig för organisationens styrning och riskaptit
- om konsekvenserna är tydliga nog för beslut

Arkitekten behöver därför bli starkare i omdöme, strukturering och kritisk granskning. AI kan hjälpa till att generera material, men arkitekten måste äga slutsatsen.

### Tre nivåer av AI-stöd i arkitekturarbetet

AI-stöd i arkitekturarbete kan grovt delas in i tre nivåer.

#### 1. Produktivitetsstöd

Produktivitetsstöd handlar om att göra befintliga arbetsmoment snabbare. Exempel är att sammanfatta mötesanteckningar, omformulera text, skapa en första disposition, extrahera frågor ur ett dokument eller jämföra två versioner av ett beslutsunderlag.

Detta är ofta den minst kontroversiella användningen, men den är inte riskfri. Även en sammanfattning kan utelämna viktiga nyanser. En omformulering kan ändra betydelsen. En förenkling kan ta bort osäkerhet som borde ha varit synlig.

Arkitektens uppgift är att se produktivitetsstöd som ett sätt att frigöra tid, inte som ett sätt att sänka kraven på kvalitet.

#### 2. Analysstöd

Analysstöd innebär att AI används för att hitta mönster, ställa motfrågor, föreslå risker, jämföra alternativ eller identifiera konsekvenser. Exempel kan vara att be AI granska en målarkitektur utifrån säkerhet, förvaltning, interoperabilitet eller informationsklassning.

Här blir nyttan större, men även risken. AI kan ge ett resonemang som låter professionellt men som saknar täckning i organisationens faktiska miljö. Den kan föreslå arkitekturmönster som är rimliga generellt men olämpliga i offentlig sektor. Den kan också missa lokala beroenden som bara finns i äldre system, avtal, processer eller förvaltningsmodeller.

Analysstöd bör därför användas som ett sätt att bredda arkitektens tänkande, inte som ett sätt att ersätta analysen.

#### 3. Beslutsstöd

Beslutsstöd innebär att AI används för att formulera rekommendationer, väga alternativ eller skapa beslutsunderlag. Detta kan vara kraftfullt, men kräver tydlig styrning. I offentlig sektor måste beslut kunna förklaras, motiveras och granskas. Om AI används i beslutsberedning behöver det vara tydligt vilken roll AI haft.

En viktig gräns går mellan att AI hjälper till att strukturera ett underlag och att AI i praktiken avgör rekommendationen. Arkitekten bör kunna svara på frågan: "Hade vi kunnat motivera detta beslut utan att hänvisa till att AI föreslog det?" Om svaret är nej är underlaget för svagt.

### Promptad analys som arkitektkompetens

När AI används som medskapare blir förmågan att formulera frågor central. En dålig prompt ger ofta generiska svar. En bra prompt ger bättre struktur, tydligare avgränsningar och fler användbara perspektiv.

Promptad analys är mer än att skriva instruktioner till ett verktyg. För arkitekten handlar det om att översätta arkitekturproblemet till en form där AI kan hjälpa till utan att förlora kontexten. En bra promptad analys anger normalt:

- syftet med analysen
- vilken typ av arkitekturbeslut som ska stödjas
- organisationens kontext och avgränsningar
- relevanta kvalitetsattribut, till exempel säkerhet, skalbarhet, interoperabilitet, tillgänglighet och förvaltningsbarhet
- särskilda villkor för offentlig sektor, till exempel informationsklassning, upphandling, transparens och lång livscykel
- vilken typ av svar som önskas, exempelvis risklista, jämförelsetabell, beslutsfrågor eller arkitekturprinciper
- vilka antaganden AI ska redovisa
- vilka osäkerheter som ska markeras

Arkitekten bör också använda AI iterativt. Första svaret bör sällan betraktas som färdigt. Det bör granskas, ifrågasättas och följas upp med mer precisa frågor.

### AI-genererat material behöver provenance

När flera personer arbetar med arkitekturdokumentation behöver organisationen förstå var innehåll kommer ifrån. Det gäller särskilt när AI används. Det betyder inte att varje mening måste märkas, men det bör finnas en praktisk nivå av spårbarhet.

För arkitekturbeslut är det viktigt att kunna se:

- vilka delar av underlaget som bygger på organisationsspecifik fakta
- vilka delar som bygger på extern kunskap eller generella antaganden
- vilka delar som är AI-genererade eller AI-bearbetade
- vem som har granskat och godkänt underlaget
- vilka osäkerheter eller verifieringspunkter som finns kvar

Detta kan beskrivas som innehållets **provenance**: dess ursprung, bearbetning och granskningskedja. För offentlig sektor är detta nära kopplat till transparens och ansvar. Om ett beslutsunderlag senare ifrågasätts bör organisationen kunna visa hur det togs fram.

### Mänskligt ansvar kan inte outsourcas

En vanlig missuppfattning är att AI minskar behovet av ansvarsfördelning eftersom verktyget bara är ett stöd. I praktiken kan det bli tvärtom. Ju mer AI används i förberedelser, analyser och texter, desto viktigare blir det att ansvar är tydligt.

Mänskligt ansvar innebär inte att en enskild arkitekt ska bära allt ansvar själv. Det innebär att organisationen måste definiera roller för beställning, användning, granskning och godkännande. Någon måste ansvara för att kontexten är korrekt. Någon måste granska risker. Någon måste godkänna rekommendationer. Någon måste avgöra när underlaget är tillräckligt.

Arkitektens roll blir ofta att synliggöra dessa ansvarspunkter och se till att AI inte gör dem otydliga.

### Arkitekturmodeller när AI hjälper till

AI kan stödja modellering genom att föreslå komponenter, relationer, informationsflöden, integrationspunkter eller kvalitetsattribut. Det kan vara användbart, särskilt i tidiga skeden när man vill skapa hypoteser.

Men modeller är inte bara diagram. En arkitekturmodell är ett sätt att göra vissa aspekter av verkligheten synliga och andra mindre synliga. Därför måste arkitekten avgöra vad modellen ska användas till. En modell för strategisk förankring behöver andra detaljer än en modell för säkerhetsgranskning eller förvaltningsplanering.

AI-genererade modeller riskerar att bli visuellt övertygande men arkitektoniskt svaga. De kan sakna viktiga beroenden, blanda logiska och fysiska nivåer, föreslå komponenter utan ägarskap eller dölja osäkerhet bakom snygg struktur.

Arkitekten bör därför behandla AI-genererade modeller som hypoteser. De kan vara startpunkter för diskussion, men de måste valideras mot verklig systemkarta, informationsmodell, integrationskatalog, säkerhetskrav och förvaltningsansvar.

### Kravarbete och AI

AI kan hjälpa till att strukturera krav, hitta motsägelser, föreslå kvalitetskrav och identifiera saknade perspektiv. Det är särskilt värdefullt när kravmaterial är omfattande, otydligt eller fragmenterat.

Samtidigt finns en risk att AI gör krav mer välformulerade utan att de blir mer sanna. Ett dåligt krav kan låta bättre efter AI-bearbetning men fortfarande vara fel. Arkitekten behöver därför skilja mellan språklig kvalitet och arkitekturell kvalitet.

I offentlig sektor bör AI-stött kravarbete särskilt granskas utifrån:

- om kraven är förenliga med verksamhetens mandat
- om rättsliga och informationssäkerhetsmässiga begränsningar är synliga
- om ansvar och uppföljning är definierade
- om krav går att verifiera
- om kraven riskerar att låsa organisationen till en viss leverantör eller teknisk lösning
- om kraven stödjer långsiktig förvaltning

### Arkitekten som motfrågemotor

En av de mest värdefulla användningarna av AI är att skapa fler frågor. Arkitektens kvalitet syns ofta inte bara i svaren, utan i vilka frågor som ställs innan organisationen bestämmer sig.

AI kan användas för att generera motfrågor till ett initiativ, till exempel:

- Vilka antaganden gör vi om data?
- Vilka beslut påverkas?
- Vem ansvarar om AI-stödet ger fel rekommendation?
- Hur följer vi upp kvalitet över tid?
- Vilka grupper kan påverkas negativt?
- Vad händer om leverantören ändrar villkor?
- Vilka systemberoenden underskattas?
- Hur avvecklar vi lösningen om den inte fungerar?

När AI används på detta sätt blir den inte en beslutsmaskin, utan en förstärkare av arkitektens kritiska tänkande.

## Scenario eller beslutskontext

En myndighet vill införa AI-stöd i sitt arkitekturkontor. Syftet är att minska tiden för att ta fram beslutsunderlag och skapa mer enhetliga analyser inför arkitekturforum. Flera arkitekter använder redan generativa AI-verktyg informellt för att sammanfatta möten, skriva utkast och jämföra lösningsalternativ.

Ledningen ser produktivitetsvinster men är osäker på riskerna. Informationssäkerhetsfunktionen oroar sig för att känslig information kan matas in i externa verktyg. Jurister frågar hur AI-genererade underlag ska hanteras vid diarieföring och insyn. Arkitekturforum undrar om AI kan användas för att standardisera konsekvensanalyser.

Det strategiska vägvalet är inte "AI eller inte AI". Det verkliga vägvalet är vilken roll AI ska få i arkitekturarbetet.

Organisationen kan välja en restriktiv linje där AI endast får användas för allmänna formuleringar och icke-känsligt material. Det minskar vissa risker men kan leda till skugg-användning om arbetssättet upplevs som för begränsande.

Organisationen kan välja en kontrollerad linje där AI används i definierade arbetsmoment, exempelvis sammanfattning, strukturering, riskfrågor och jämförelse av alternativ. Då krävs tydliga regler för informationsklassning, granskning och märkning av AI-stöd.

Organisationen kan välja en mer offensiv linje där AI integreras i arkitekturprocessen som ett standardiserat analysstöd. Då behöver organisationen investera i verktyg, kompetens, loggning, kvalitetssäkring, roller och governance.

Arkitektens uppgift är att hjälpa organisationen se dessa alternativ som arkitekturval, inte bara som verktygsval.

## Strategiska vägval och arkitektöverväganden

### Vägval 1: Individuell produktivitet eller gemensam arkitekturförmåga

AI kan införas som personligt stöd för enskilda arkitekter eller som en gemensam förmåga i arkitekturfunktionen.

Individuell användning ger snabb nytta och låg tröskel. Arkitekter kan effektivisera egna arbetsmoment utan omfattande införandeprojekt. Risken är att arbetssätten blir ojämna, att kvaliteten varierar och att organisationen inte vet hur AI påverkar beslutsunderlag.

Gemensam arkitekturförmåga kräver mer styrning men ger bättre spårbarhet, kvalitet och lärande. Då kan organisationen definiera mallar, godkända användningsfall, granskningsrutiner och gemensamma promptmönster.

Arkitekten bör fråga: Är AI-användningen något varje arkitekt får lösa själv, eller en förmåga som organisationen behöver styra och förvalta?

### Vägval 2: Effektivisera befintliga processer eller omforma arkitekturprocessen

Det är frestande att använda AI för att göra befintliga processer snabbare. Men AI kan också motivera en omformning av själva arkitekturarbetet. Om analys, dokumentation och granskning kan stödjas på nya sätt kan arkitekturforum få bättre beslutsunderlag tidigare. Roadmap-arbete kan bli mer iterativt. Principer kan testas mot fler scenarier. Risker kan identifieras tidigare.

Samtidigt är det riskabelt att omforma processer innan organisationen förstår kvalitet och ansvar. En klok strategi kan vara att börja med avgränsade användningsfall och successivt ändra arbetsprocessen när erfarenhet och styrning finns på plats.

Arkitekten bör fråga: Använder vi AI för att göra samma sak snabbare, eller för att göra arkitekturarbetet bättre?

### Vägval 3: Generella AI-verktyg eller organisationsanpassat AI-stöd

Generella AI-verktyg är ofta kraftfulla och enkla att börja använda. De passar för allmän textbearbetning, brainstorming och strukturering. Men de saknar ofta djup förståelse för organisationens målarkitektur, principer, systemlandskap, informationsmodeller och styrdokument.

Organisationsanpassat AI-stöd kan kopplas till interna kunskapskällor, mallar och principer. Det kan ge mer relevant stöd, men kräver starkare kontroll över data, åtkomst, uppdatering, kvalitet och livscykel.

Arkitekten bör väga nytta mot kontroll. För känsliga eller beslutspåverkande arbetsmoment räcker sällan ett generellt verktyg utan tydliga begränsningar.

### Vägval 4: AI som idépartner eller AI som beslutsberedare

Som idépartner kan AI användas för att bredda perspektiv, skapa alternativ och generera frågor. Detta är ofta relativt lågrisk om känslig information hanteras korrekt.

Som beslutsberedare får AI en mer central roll i att strukturera konsekvenser och rekommendationer. Då krävs högre krav på spårbarhet, kvalitetssäkring och mänsklig granskning.

Arkitekten bör göra rollen explicit. I varje användningsfall bör det vara tydligt om AI används för idéutveckling, analys, formulering, granskning eller rekommendation.

### Vägval 5: Central kontroll eller distribuerat lärande

Offentlig sektor har ofta starka krav på kontroll, men AI-utvecklingen rör sig snabbt. För mycket central kontroll kan bromsa lärande och leda till informell användning utanför styrda kanaler. För mycket frihet kan skapa risker, ojämlik kvalitet och bristande insyn.

Ett balanserat angreppssätt är att skilja mellan experimentzoner och produktionsnära användning. I experimentzoner kan arkitekter pröva arbetssätt med låg risk och icke-känsligt material. I produktionsnära användning krävs tydligare regler, godkända verktyg och dokumenterad granskning.

Arkitekten bör hjälpa organisationen att skapa kontrollerat lärande snarare än antingen total frihet eller total låsning.

## Vanliga felsatsningar

### Felsatsning: Att likställa snabbare dokumentation med bättre arkitektur

- **Varför det händer:** AI kan snabbt producera text som ser strukturerad och professionell ut. Det kan skapa en känsla av kvalitet även när analysen är ytlig.
- **Hur arkitekten kan undvika det:** Bedöm underlag utifrån spårbarhet, antaganden, konsekvenser och beslutskvalitet, inte enbart utifrån läsbarhet.

### Felsatsning: Att använda AI utan tydliga informationsregler

- **Varför det händer:** Individuella verktyg är lätta att använda, och arkitekter arbetar ofta med material som känns internt men inte alltid uppfattas som känsligt.
- **Hur arkitekten kan undvika det:** Kräv regler för informationsklassning, tillåtna verktyg, förbjudet innehåll och hantering av organisationsspecifik information.

### Felsatsning: Att låta AI formulera rekommendationer utan granskning

- **Varför det händer:** AI kan ge tydliga och övertygande rekommendationer även när kontexten är ofullständig.
- **Hur arkitekten kan undvika det:** Separera AI-genererade alternativ från mänskligt godkända rekommendationer. Dokumentera vem som äger slutsatsen.

### Felsatsning: Att promptkompetens betraktas som en individuell färdighet snarare än en organisatorisk tillgång

- **Varför det händer:** Tidiga AI-användare utvecklar egna arbetssätt som inte delas, granskas eller standardiseras.
- **Hur arkitekten kan undvika det:** Skapa gemensamma promptmönster, exempel och kvalitetskriterier för återkommande arkitekturarbeten.

### Felsatsning: Att bortse från diarieföring, insyn och arkivering

- **Varför det händer:** AI-användning ses som en informell del av arbetsprocessen snarare än som en del av beslutsberedningen.
- **Hur arkitekten kan undvika det:** Klargör när AI-stödda underlag blir handlingar, hur versioner hanteras och hur beslutsunderlag ska kunna granskas i efterhand. Exakta krav bör verifieras mot organisationens juridiska funktion.

### Felsatsning: Att AI blir en dold normkälla

- **Varför det händer:** Om AI ofta används för att formulera principer, krav och rekommendationer kan dess generella antaganden gradvis påverka organisationens arkitektur.
- **Hur arkitekten kan undvika det:** Säkerställ att arkitekturprinciper, målarkitektur och styrande dokument är den primära normkällan. AI bör prövas mot dessa, inte ersätta dem.

## Arkitektens checklista

Använd checklistan när AI ska användas i arkitekturarbete eller beslutsberedning.

### Syfte och användningsfall

- Är det tydligt vilket arbetsmoment AI ska stödja?
- Är AI:s roll avgränsad: idépartner, analysstöd, textstöd, granskare eller beslutsberedare?
- Är nyttan kopplad till bättre beslut, inte bara snabbare produktion?
- Finns en gräns för vad AI inte får användas till?

### Information och säkerhet

- Vilken informationsklass har materialet som används?
- Är verktyget godkänt för den typen av information?
- Finns regler för personuppgifter, sekretess och känslig verksamhetsinformation?
- Finns loggning eller annan spårbarhet där det behövs?
- Är det tydligt vilka interna dokument, modeller eller principer AI får använda?

### Kvalitet och granskning

- Har AI-genererat material granskats av en ansvarig person?
- Är antaganden och osäkerheter synliga?
- Har alternativa tolkningar prövats?
- Har underlaget kontrollerats mot målarkitektur, principer och styrande dokument?
- Är rekommendationer motiverade utan att hänvisa till AI som auktoritet?

### Ansvar och process

- Vem äger slutsatsen?
- Vem ansvarar för att underlaget är korrekt?
- Vem godkänner användningen av AI i arbetsmomentet?
- Är AI-användningen dokumenterad på rätt nivå?
- Är det tydligt när AI-stöd övergår från informellt arbetsstöd till beslutsunderlag?

### Offentlig sektor

- Påverkas rättssäkerhet, insyn eller förtroende?
- Behöver juridisk funktion, informationssäkerhet eller dataskydd involveras?
- Finns risk för att AI-stöd skapar otydlig ansvarsfördelning?
- Finns krav på diarieföring, arkivering eller granskningsbarhet?
- Är leverantörsberoenden och dataplacering kända?

## Snabb sammanfattning

- AI förändrar arkitektens arbete genom att stödja analys, dokumentation, modellering, kravarbete och beslutsberedning.
- Den viktigaste förändringen är inte att arkitekten skriver snabbare, utan att arkitektens omdöme, granskning och ansvar blir mer centrala.
- AI-stöd kan delas in i produktivitetsstöd, analysstöd och beslutsstöd. Varje nivå kräver olika grad av kontroll.
- Promptad analys blir en ny arkitektkompetens: att formulera rätt frågor, kontext, kriterier och avgränsningar.
- AI-genererade underlag behöver spårbarhet, särskilt när de påverkar arkitekturforum och beslut.
- Mänskligt ansvar kan inte delegeras till AI. Arkitekten måste kunna motivera slutsatser och synliggöra osäkerheter.
- I offentlig sektor måste AI-stöd i arkitekturarbete hanteras med särskild hänsyn till transparens, informationshantering, rättssäkerhet och tillit.

## Reflektionsfrågor

1. Vilka delar av ditt nuvarande arkitekturarbete lämpar sig bäst för AI-stöd: dokumentation, analys, modellering, kravarbete eller beslutsberedning?
2. Var går gränsen i din organisation mellan AI som informellt arbetsstöd och AI som del av ett formellt beslutsunderlag?
3. Vilka typer av information skulle aldrig få användas i ett generellt AI-verktyg?
4. Hur bör arkitekturforum veta om ett underlag är AI-stött?
5. Vilka gemensamma promptmönster eller granskningsrutiner skulle höja kvaliteten i arkitekturarbetet?
6. Vilka risker uppstår om AI-stöd införs individuellt av arkitekter utan gemensam styrning?
7. Hur kan organisationen uppmuntra lärande utan att skapa okontrollerad användning?

## Nästa steg

Nästa kapitel går från arkitektens individuella och kollektiva arbetssätt till organisationens styrning. När AI börjar påverka analys, dokumentation och beslutsberedning räcker det inte med personligt omdöme. Organisationen behöver arkitekturprinciper, styrmodeller och forum som kan hantera AI som både teknik, verksamhetsförmåga och riskområde.

Kapitel 4 behandlar därför strategisk arkitekturstyrning i AI-eran: hur principer, målarkitekturer och roadmap-arbete behöver utvecklas när AI blir en del av organisationens långsiktiga förändringsagenda.
