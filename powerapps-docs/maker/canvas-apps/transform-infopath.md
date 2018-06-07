---
title: Transformer InfoPath-skjemaer til PowerApps | Microsoft Docs
description: Kom i gang med å transformere InfoPath-skjemaer til PowerApps med mer informasjon om vanlige InfoPath-scenarioer og hvordan du oppretter disse elementene i PowerApps.
services: powerapps
documentationcenter: na
author: dewcatpaint1
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/05/2018
ms.author: cathed
ms.openlocfilehash: 4e81566ec427b4faa064b1ba5891fa2526497b34
ms.sourcegitcommit: eac8ad7b54a0b0eba6444a38a952dbfd17bc64b5
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/08/2018
ms.locfileid: "30998457"
---
# <a name="transform-your-infopath-forms-to-powerapps"></a>Transformer InfoPath-skjemaer til PowerApps

Er du en person som bygger fantastiske ting i InfoPath, og som ønsker å levere disse fantastiske tingene på en mer robust plattform?

## <a name="key-advantages-of-powerapps-over-infopath"></a>De viktigste fordelene med PowerApps i forhold til InfoPath

Hvis du er som de fleste priviligerte InfoPath-brukere, har du allerede brukt de unike evnene dine til å bygge flotte skjemaer en stund. Selv om du er veldig fornøyd med skjemaene du lager, vet du at de har sine begrensninger: den &quot;klassiske&quot; utformingen, de gir ikke de beste opplevelsene på mobile enheter, usikkerheten om fremtidig bruk samt du er alltid låst når det gjelder å koble til andre tjenester uten å skrive kode.

PowerApps-teamet har tatt disse og flere andre utfordringer på alvor. De har jobbet hardt for å gi deg bedre opplevelser med PowerApps. Målet er å gi deg muligheten til å lage apper ved å dra nytte av forretningsevnene dine samt ferdighetene du har med eksisterende teknologi, slik at du kan bruke PowerApps til raskt å bygge og distribuere de riktige forretningsløsningene uten å skrive kode.

**PowerApps sikrer en kraftfull fremtid**  
PowerApps er en SaaS-plattform (Software as a Service), som er utviklet for å gi deg muligheten til raskt å bygge apper med høy funksjonsevne som du kan distribuere på nettet, til SharePoint, Dynamics 365, Teams, Power BI eller til en mobil enhet uten ekstra arbeid. Siden de er så enkle å distribuere (du trenger bare å gi noen URL-adressen til den publiserte appen), er de like enkle å oppdatere.

**Dele appene**  
Har du noen gang prøvd å bygge en app og deretter publisere den på Google eller Apples appbutikk? Det er komplisert. Desto mer utfordrende blir det hvis du vil distribuere enda en app eller oppdatere den eksisterende, da det blir mange flere trinn for brukerne dine. Ikke med PowerApps. Brukerne dine installerer Microsoft PowerApps-appen gjennom appbutikken sin, logger på med sitt eget Microsoft-brukernavn og -passord og vips så har de alle de høyfunksjonelle appene du har delt med dem. Når du senere oppdaterer disse appene eller sender ut nye apper, vises det på brukernes enheter. Mobilapper uten alt styret med enhetsadministrering er en stor fordel for deg og bedriften din.

**Når vi likevel snakker om mobilen**  
Med PowerApps kan du utnytte kraften i brukerens mobile enhet. Via appen får du tilgang til akselerasjon, kameraet, kompasset, tilkoblingsinformasjon og plasseringssignaler. Dette åpner en hel ny verden av muligheter for bygging av apper for å få arbeidet unnagjort. Og naturligvis er berøringsfunksjonalitet kun automatisk i PowerApps, ingenting krever ekstra kodeskriving når du bygger appen.

**Lås opp mulighetene**  
Med InfoPath var hovedregelen at du jobbet med data fra én datakilde. Det ble imidlertid vanskelig hvis du ønsket å gjøre oppdateringer et annet sted (som på en SharePoint-liste i en annen områdesamling) eller koble til eksterne tjenester, og konsepter som kodingen bak kunne holde deg våken om natten. Ikke med PowerApps. Den er utformet slik at du kan jobbe med flere datakilder og tjenestetilkoblinger i én app. I skrivende stund er det [mer enn 150 koblinger](https://docs.microsoft.com/powerapps/connections-list#all-connectors) som støtter en kombinasjon av lokalt lagrede data og data lagret i skyen, Microsoft Office 365- og Azure-tjenester som Flow og Dynamics 365 og en rekke tredjeparts tjenester inkludert populære mål som Dropbox, Google, Salesforce og Slack. Nå kan du bygge løsninger som skaleres etter hvor brukerne trenger deg, ikke bare der de originale dataene er lagret.

## <a name="powerapps-and-sharepoint-even-better-together"></a>PowerApps og SharePoint: enda bedre sammen

PowerApps er et flott verktøy som gjør SharePoint-opplevelsen bedre på to måter. Du kan velge å enten tilpasse skjemaene til en SharePoint-liste eller opprette en frittstående app for å arbeide med SharePoint-dataene.

**Egendefinering av et SharePoint-skjema** er flott hvis brukerne skal bruke listen til sitt daglige arbeid, men du ønsker å tilpasse hvordan de legger til / viser / redigerer elementer i SharePoint-listen. Hvis du klikker på **Tilpass skjemaer** opprettes en &quot;skjemaapp&quot; med enkle skjermbilder som endrer modus (ny/rediger/vis) basert på kontekst. Disse appene administreres av SharePoint, og tillatelsene for appene er de samme som tillatelsene for redigering/visning av lister.

**Når du oppretter en PowerApps-lerretsapp via SharePoint**, kan du kjøre appen alene på en mobil enhet. Den kan også bygges inn i en SharePoint-side. Når du klikker på den, åpnes en app med tre skjermbilder (listevisning, ny-/rediger-skjema, vis-skjema).  Tillatelses-/delingsmodellen for disse appene er ikke bundet til SharePoint, men administreres via PowerApps.

Nå forstår du forskjellen mellom de to alternativene, og det neste avsnittet gir en oversikt over hvordan hvert av dem brukes.

## <a name="sharepoint-forms"></a>SharePoint-skjemaer

PowerApps-teamet og SharePoint-teamet har samarbeidet for å lage en ny artikkel om tilpasning, som du kan bruke med SharePoint.  Hvis du er som de fleste SharePoint-utviklere, har du lært InfoPath å samhandle med SharePoint. Selv om SharePoint er flott, er standardskjemaene litt kjedelige og har lite rom for tilpasning eller forretningslogikk uten InfoPath. Vel, det var på gamlemåten.

Med PowerApps kan du nå tilpasse listeskjemaene dine som opprinnelig funksjonalitet. Og når du gjør det, får du fullt utbytte av PowerApps. På skjermdumpen under ser du et eksempel på et PowerApps-skjema med en innebygd Power BI-rapport.  Hele løsningen var ferdig på under 15 minutter.

![Integrering med SharePoint](./media/transform-infopath/sharepoint-integration.png)

En annen viktig funksjon i PowerApps er muligheten til enkelt å koble til en annen SharePoint-områdekobling eller et annen miljø fra samme skjema. Vil du for eksempel lage et skjema som viser og oppdaterer data fra SharePoint Online og det lokale SharePoint-miljøet samtidig? Ikke noe problem. Installer den [lokale datagatewayen](https://docs.microsoft.com/powerapps/gateway-management), og i løpet av noen minutter er du klar og kan koble PowerApps, Power BI, Microsoft Flow og Azure Logic Apps til med lokalt lagrede data. Du trenger ikke endre noen regler i brannmuren. Denne appen kan kobles til Microsoft Flow og gi enda et funksjonsnivå.

## <a name="a-standalone-sharepoint-app"></a>En frittstående SharePoint-app

Hvis du ønsker å bygge en fullstendig, frittstående app basert på SharePoint-dataene i stedet for å bare oppdatere opplevelsen med listeskjemaet, kan du bruke denne teknikken. Dette er også den beste måten å komme i gang på, slik at du kan begynne å lære å bruke PowerApps-lerretet og bygge fremtidens apper fra alle mulige datakilder.

Kom i gang ved å gå til SharePoint-listen du ønsker å samhandle med, og:

1. Klikk på PowerApps på menylinjen.
2. Velg Opprette en app.
3. Skriv inn et navn.
4. Klikk på Opprett.

Nå bygger PowerApps en standardapp som du deretter kan tilpasse.

Start enkelt. I den første appen bør du bare ha en enkel, tilpasset liste med bare ett par ulike typer felter. På denne måten kan du bygge et solid grunnlag uten å bli overveldet. Ikke bekymre deg, du vil raskt få taket på det og kan gå videre til mer komplekse apper.  Se denne [dokumentasjonen](https://docs.microsoft.com/powerapps/generate-app-from-sharepoint-list-interface) eller denne [fellesskapsvideoen](https://youtu.be/BnYe_7fpZRM) for å få hjelp til å gå gjennom den første appen din. Eksempelet under viser vanlige InfoPath-jobber og hvordan du utfører dem i PowerApps. Hver av disse bygger på en enkel SharePoint-listeapp.

# <a name="how-do-you-do-that-with-powerapps"></a>Slik gjør du dette med PowerApps

Nå som du kjenner til de grunnleggende konseptene, kan vi gå videre. Når du har laget din første app, vil det neste avsnittet hjelpe deg å ta i bruk noen av de vanligste InfoPath-konseptene i PowerApps.

**Skjule/vise/låse et felt basert på en verdi**  
En av de vanligste måtene å lage et vellykket skjema på, er å ha en streng forretningslogikk og evne til å gjennomføre den. Én måte å gjøre dette på, er å endre tilstanden til et felt basert på en verdi eller en handling. Med PowerApps kan du velge kontrollen og stille DisplayMode til Edit eller View for å angi om en bruker kan endre feltet. En annen metode er å bruke en enkel If-formel for å kunne gjøre dette på visse betingelser. Først velger du etiketten du vil redigere, og deretter klikker du på låseikonet for å låse opp kortet slik at du kan endre verdien.

![Skjule/vise/låse datakort](./media/transform-infopath/hide-show-lock.png)

Rull ned til nederst på kortet til høyre, og rediger egenskapene for Standardmodus.

![If/Else-uttrykk](./media/transform-infopath/if-else-statement.png)

Bruk et If-uttrykk i dette eksempelet. If(ThisItem.Color = &quot;Blue&quot;, DisplayMode.View, DisplayMode.Edit). Dette uttrykket sier at hvis Color-feltet for det aktuelle elementet er blått, er dyrefeltet skrivebeskyttet, og hvis ikke kan feltet redigeres.

Hvis du ikke vil vise kortet i det hele tatt, kan du sette inn en lignende funksjon i Synlig-feltet over Visningsmodus.

Andre ting du kan leke med, er å skjule en Godta-knapp slik at den bare vises hvis brukerens e-postadresse samsvarer med godkjennerens e-postadresse. Tips: Bruk «User().Email» for å få tilgang til den aktuelle brukerens e-postadresse. Så du kan gjøre knappen synlig ved å bruke If(YourDataCard.Text = User().Email, true, false) der YourDataCard er det kortet der godkjennerens e-postadresse er lagret.

**Betinget formatering**  
På lignende måte som over, der du skjulte feltet, kan du også gi brukeren visuell tilbakemelding. Kanskje du ønsker gjøre teksten rød hvis verdien som skrives inn ligger utenfor det godkjente området, eller endre teksten og fargen på Last opp-knappen etter at en fil er lastet opp? Disse tingene gjør du ved å bruke funksjoner, som f.eks. If-funksjonen, i egenskapene for felter for f.eks. farge eller synlighet.

Du kan for eksempel bruke If-funksjonen sammen med [IsMatch](https://docs.microsoft.com/powerapps/functions/function-ismatch)-funksjonen for å endre tekstfargen på e-postfeltet til rød hvis brukeren ikke har skrevet inn en gyldig e-postadresse. Dette gjør du ved å stille inn Color-verdien for TextInput1 til If(IsMatch(TextInput1.Text, Email), Black, Red) der TextInput1 er feltet der brukeren skriver inn en e-postadresse. IsMatch støtter en rekke forhåndsdefinerte mønstre som f.eks. e-post, eller du kan opprette et selv. Du finner mer informasjon om betinget formatering i denne [fellesskapsvideoen](https://powerusers.microsoft.com/t5/Video-Webinar-Gallery/PowerApps-Conditional-Formatting-and-Popups/m-p/84962).

**Implementere rollebasert sikkerhet**  
Den første funksjonen du må vurdere, er [DataSourceInfo](https://docs.microsoft.com/powerapps/functions/function-datasourceinfo). Hvilken informasjon som returneres fra datakilden varierer etter datakilden, men ofte kan du bruke DataSourceInfo(YourDataSource, DataSourceInfo.EditPermission) for å sjekke om brukeren har tilgang til å redigere dataene. Erstatt YourDataSource med navnet på datakilden din. Med denne kan du bare vise et skjema eller en knapp hvis brukeren har tilgang til å redigere. Sjekk DataSourceInfo-dokumentasjonen for en fullstendig liste over informasjon du kan bruke funksjonen til å spørre etter.

Hvis du heller vil bruke Active Directory-grupper til å administrere tilgang til knapper eller skjemaer i appen, må du gå dypere. For å gjøre dette må du utnytte fleksibiliteten til PowerApps og opprette dine egne koblinger ved bruk av Microsoft Graph API-en. Dette høres kanskje skremmende ut, men det finnes trinnvis [dokumentasjon](https://powerapps.microsoft.com/blog/implementing-role-based-permission/) som veileder deg gjennom det.

**Sende en e-post fra appen**  
Det er flere måter å sende e-post fra PowerApps på. Den enkleste måten er å bruke Office 365 Outlook Connector. Med denne koblingen kan du sende en e-post som deg selv fra appen. Du kan også motta e-postmeldinger og andre oppgaver som samhandler med innboksen din. Se [dokumentasjonen](https://docs.microsoft.com/powerapps/connections/connection-office365-outlook) eller denne [fellesskapsvideoen](https://powerusers.microsoft.com/t5/Video-Webinar-Gallery/Send-an-email-from-PowerApps/m-p/74349) om hvordan du sender e-posten.

Hvis du trenger å sende en mer kompleks e-post, kanskje ved å opprette en godkjenningskjede for en SharePoint-godkjenningsarbeidsflyt, bør du velge å opprette en Microsoft Flow og koble appen til den. Når du kobler appen din til Microsoft Flow, får du tilgang til den fulle effekten til en arbeidsflytmotor som på samme måte som PowerApps har svært gode tilkoblinger til eksterne data og tjenester. Se denne [dokumentasjonen](https://docs.microsoft.com/powerapps/using-logic-flows) for mer informasjon om kobling av PowerApps og Microsoft Flow.

Hvis du fortsatt ikke har funnet det e-postalternativet du ønsker, kan du også bruke PowerApps-koblingene for Benchmark Email, Gmail, MailChimp, Outlook.com, SendGrid eller SMTP. Det er PowerApps styrke, tilkoblingsmuligheter.

**Arbeidsflyter**  
Det er vanskelig å snakke om forretningsapper og forretningslogikk uten en arbeidsflytmotor. Den gode nyheten er at PowerApps-teamet ikke har funnet opp hjulet på nytt og gir deg en annen arbeidsflytmotor. De gir deg i stedet en robust kobling til Microsoft Flow-tjenesten. Nå kan du automatisere prosesser og oppgaver på tvers av over [200 ulike tjenester](https://flow.microsoft.com/connectors/), ved å bruke den brukervennlige arbeidsflytmotoren. Se denne [dokumentasjonen](https://docs.microsoft.com/powerapps/using-logic-flows) for mer informasjon om kobling av PowerApps og Microsoft Flow.

**Variabler med PowerApps**  
Når du bygger løsninger, er det naturlig å tenke at det må involvere variabler. Selv om PowerApps har tre typer variabler, vil du kun bruke dem hvis du må. I stedet for å tenke på å hente data, lagre dem i en variabel og henvise denne variabelen, skal du tenke på å bare henvise disse dataene direkte. Den beste måten å skjønne dette på, er å se til Excel. I Excel er Total ikke en variabel, men summen av de andre feltene. Så hvis du vil bruke denne verdien et annet sted i regnearket, angir du feltet du har beregnet summen i. [Dokumentasjonen](https://docs.microsoft.com/powerapps/working-with-variables) forklarer dette på en god måte. Vær åpen for en ny måte å tenke på.

Hvis du fortsatt trenger variabler (det er mange tilfeller du trenger dem), vil dette hjelpe deg å forstå de ulike alternativene. Husk at med PowerApps trenger du ikke definere variabler. Bare bruk én av funksjonene til å angi et navn og en verdi som skal lagres, og variabelen er opprettet. Du kan vise variablene du har opprettet ved å klikke på Vis på menylinjen og deretter velge Variabler. Variabler oppbevares i minnet og verdiene slettes når du lukker appen. De tre variabeltypene er som følger:

- Globale variabler er det du vanligvis først tenker på. Her kan du bruke [Angi](https://docs.microsoft.com/powerapps/functions/function-set)-funksjonen til å angi en verdi for variabelen, og deretter er den tilgjengelig i hele appen. Et eksempel på hvordan du kan bruke funksjonen, er Set(YourVariable, YourValue). Deretter kan du henvise til YourVariable etter navnet i hele appen.
- Kontekstvariabler er variabler som bare er tilgjengelige på skjermbildet de defineres på. De tilbakestilles når du lukker skjermbildet. Disse brukes ofte til å lagre informasjon som overføres fra et tidligere skjermbilde eller for eksempel til å sjekke om skjemaet har blitt sendt inn. Vanlig bruk av [UpdatedContext](https://docs.microsoft.com/powerapps/functions/function-updatecontext) er UpdateContext( { Submitted: "true" } ). Dette vil angi variabelen Submitted til sann. Du kan ta denne delen av Send-knappen på siden til å sjekke om informasjonen er sendt inn og endre alle feltene til skrivebeskyttet. Merk: Du bruker ":" Samlinger brukes til å lagre tabeller med informasjon, som kan oppdateres enkeltvis. Se [Samle inn](https://docs.microsoft.com/powerapps/functions/function-clear-collect-clearcollect) for å komme i gang. Et eksempel på bruk kan være å opprette en handlekurv når brukeren merker ulike SharePoint-elementer han/hun vil sende inn. Det finnes en [fellesskapsvideo](https://powerusers.microsoft.com/t5/Video-Webinar-Gallery/Learn-about-PowerApps-Collections/m-p/89180) som viser dette konseptet i bruk.

**Rullegardinmenyer med undermenyer**  
Rullegardinmenyer med undermenyer er svært nyttige. Med disse kan du sortere valgene i én rullegardinmeny basert på verdiene som er valgt i forrige rullegardinmeny. I PowerApps opprettes disse ofte ved å ha to datakilder i appen. Den første datakilden er dataene du arbeider med eller oppdaterer, og den andre datakilden brukes til å lagre verdiene for å danne de undermenyene du ønsker. Under finner du et eksempel på den andre datakilden med valgalternativene.

![Rullegardinmenyer med undermenyer](./media/transform-infopath/cascading-dropdowns.png)

Nå oppretter du den første rullegardinkontrollen, og for Items-egenskapene bruker du formelen Distinct(Impacts, Title) til kun å vise Cost, Program Impact og Schedule på rullegardinmenyen. Deretter legger du til neste rullegardinmeny og angir Items-egenskapen til Filter(Impacts,ddSelectType.Selected.Value in SCategory) der ddSelectTyp er navnet på den første rullegardinmenyboksen. Og så enkelt lager du rullegardinmenyer med undermenyer. Du finner mer informasjon i denne publiseringen fra PowerApps-teamet [SharePoint: Rullegardinmeny med undermenyer i fire enkle trinn!](https://powerusers.microsoft.com/t5/PowerApps-Community-Blog/SharePoint-Cascading-Dropdowns-in-4-Easy-Steps/ba-p/16248) Du kan også se denne [fellesskapsvideoen](https://powerusers.microsoft.com/t5/Video-Webinar-Gallery/PowerApps-Cascading-Dropdown/m-p/92813) – og ikke bekymre deg, du kan gjøre det akkurat like enkelt uten SharePoint.

**Ikke bygg én superapp**  
Med PowerApps kan du kalle opp én app fra en annen app, så i stedet for det voldsomme InfoPath-skjemaet som holdes sammen med tyggegummi, kan du bygge en gruppe med apper som kaller opp hverandre. Du kan til og med overføre data frem og tilbake mellom appene, noe som gjør utviklingen enklere.

## <a name="next-steps"></a>Neste trinn

Takket være informasjonen over er du nå klar til å ta skrittet ut i verden og ta den med storm, med én PowerApps-app om gangen. Under finner du noen koblinger som kan være nyttige etter hvert som du prøver deg frem. Den ene av disse koblingene leder til webområdet til PowerApps-fellesskapet. Bli en del av fellesskapet i dag, og utvid ferdighetene dine raskere enn du vil klare på egen hånd.

[**Formelreferanse**](https://docs.microsoft.com/en-us/powerapps/formula-reference) – Bare det å se gjennom standardfunksjonene er alltid en god kilde til inspirasjon.

[**PowerApps-fellesskapet**](https://powerusers.microsoft.com/t5/PowerApps-Community/ct-p/PowerApps1) – Se eksempler, kom i kontakt med andre, still spørsmål, svar på andres spørsmål og bidra til å få PowerApps-fellesskapet å vokse.