---
title: Transformer InfoPath-skjemaet ditt til en lerretsapp | Microsoft Docs
description: Begynn å transformere InfoPath-skjemaet ditt til PowerApps med informasjon om vanlige scenarioer og hvordan du oppretter disse elementene i en lerretsapp.
author: emcoope-msft
manager: kvivek
ms.service: powerapps
ms.topic: article
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 04/05/2018
ms.author: emcoope
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: a5b9ddb2006a53796f782db3c620fa592f2a5aed
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71994875"
ms.PowerAppsDecimalTransform: true
---
# <a name="transform-your-infopath-form-to-powerapps"></a>Transformer InfoPath-skjemaet ditt til PowerApps

Er du en person som bygger fantastiske ting i InfoPath og som ønsker å levere disse fantastiske tingene på en mer robust plattform?

## <a name="key-advantages-of-powerapps-over-infopath"></a>De viktigste fordelene med PowerApps i forhold til InfoPath

I likhet med de fleste privilegerte InfoPath-brukere har du brukt de unike ferdighetene dine til å bygge flotte skjemaer en stund nå. Du er veldig fornøyd med skjemaene, men du vet også at de har sine begrensninger: den &quot;klassiske&quot; utformingen, en mindre optimal opplevelse på mobilenheter, usikkerheten om fremtidig bruk samt å alltid stå fast når du skal koble til andre tjenester uten å skrive kode.

PowerApps-teamet har tatt disse og mange andre utfordringer på alvor. De har arbeidet hardt for å gi deg bedre opplevelser og gjøre det mulig for deg å opprette lerretsapper ved å dra nytte av forretnings- og teknologiferdighetene du besitter. Ved å bruke PowerApps kan du raskt utvikle og distribuere de riktige forretningsløsningene uten å skrive kode.

**PowerApps sikrer en kraftfull fremtid**  
PowerApps er en SaaS (Software as a Service)-plattform som er utviklet for å gi deg muligheten til raskt å bygge apper med høy funksjonsevne, som du kan distribuere på nettet, til SharePoint, Dynamics 365, Teams, Power BI eller til en mobil enhet, uten ekstra arbeid. Siden du kan distribuere dem bare ved å gi noen nettadressen til den publiserte appen, er de like enkle å oppdatere.

**Dele appene**  
Har du noen gang prøvd å bygge en app og deretter publisere den for iOS eller Android-enheter? Det er komplisert. Hvis du vil distribuere enda en app eller oppdatere den eksisterende, må brukerne utføre mange flere trinn. Ikke med PowerApps. Brukerne dine installerer PowerApps Mobile på enhetene sine og logger seg på. Og vips, så har de alle de høyfunksjonelle appene du har delt med dem. Når du senere oppdaterer disse appene eller sender ut nye apper, vises disse appene på brukernes enheter. Mobilapper uten alt styret med behandling av enheter er en stor fordel for deg og bedriften din.

**Når vi likevel snakker om mobilen**  
Med PowerApps kan du utnytte potensialet i brukerens mobile enhet. Du har tilgang til akselerasjon, kameraet, kompasset, tilkoblingsinformasjon og posisjonssignaler: alt fra appen din. Dette åpner en hel ny verden av muligheter for bygging av apper for å få arbeidet unnagjort. Og naturligvis er berøringsfunksjonalitet automatisk i PowerApps: det kreves ingen ekstra kodeskriving når du bygger appen.

**Lås opp mulighetene**  
Med InfoPath bruker du vanligvis data fra én kilde. Imidlertid ble det vanskelig hvis du ville oppdatere en annen kilde (for eksempel en SharePoint-liste i en annen områdesamling) eller koble til eksterne tjenester. Konsepter som kode bak holdt deg våken om natten. PowerApps er utformet slik at du kan jobbe med flere datakilder og tjenestetilkoblinger i én app. For øyeblikket støtter [mer enn 200 koblinger](connections-list.md#all-standard-connectors) en kombinasjon av lokale og skybaserte data, inkludert Microsoft Office 365- og Azure-tjenester som Microsoft Flow og Dynamics 365. Du kan også koble til en rekke tredjepartstjenester, for eksempel Dropbox, Google, Salesforce, Slack og andre populære mål.

Nå kan du bygge løsninger som skaleres etter hvor brukerne trenger deg, ikke bare der de originale dataene er lagret.

## <a name="powerapps-and-sharepoint-even-better-together"></a>PowerApps og SharePoint: enda bedre sammen

PowerApps er et flott verktøy som gjør SharePoint-opplevelsen bedre på to måter. Du kan velge å enten tilpasse skjemaene til en SharePoint-liste eller opprette en frittstående app for å arbeide med SharePoint-dataene.

**Å tilpasse et SharePoint-skjema** er flott hvis du ønsker å tilpasse hvordan brukere legge til, viser eller redigerer elementer i en liste som de bruker til sitt daglige arbeid. Hvis du klikker på **Tilpass skjemaer**, opprettes en &quot;skjemaapp&quot; med én skjerm som endrer modus (ny/rediger/vis) basert på kontekst. Disse appene administreres av SharePoint, og tillatelsene for appene er de samme som tillatelsene for redigering/visning av lister.

**Når du oppretter en PowerApps-lerretsapp via SharePoint**, kan du kjøre appen alene på en mobil enhet. Du kan også bygge inn appen på en SharePoint-side. Hvis du klikker på dette, opprettes en app med tre skjermer (bla gjennom listen, vis detaljer og opprett/oppdater et element). Tillatelses-/delingsmodellen for disse appene er ikke bundet til SharePoint, men administreres via PowerApps.

Nå forstår du forskjellen mellom de to alternativene, og det neste avsnittet gir en oversikt over hvordan hvert av dem brukes.

## <a name="sharepoint-forms"></a>SharePoint-skjemaer

PowerApps- og SharePoint-teamene har samarbeidet for å lage en artikkel om tilpasning, som du kan bruke med SharePoint. Hvis du er som de fleste SharePoint-utviklere, har du lært InfoPath å samhandle med SharePoint. SharePoint er flott, men standardskjemaene er litt kjedelige og har lite rom for tilpasning eller forretningslogikk uten InfoPath. Vel, det var på gamlemåten.

Med PowerApps kan du nå tilpasse listeskjemaene dine som opprinnelig funksjonalitet. Og når du gjør det, får du fullt utbytte av PowerApps. På skjermdumpen under ser du et eksempel på et PowerApps-skjema med en innebygd Power BI-rapport. Hele løsningen var ferdig på under 15 minutter.

![Integrering med SharePoint](./media/transform-infopath/sharepoint-integration.png)

En annen viktig funksjon i PowerApps er muligheten til enkelt å koble til en annen SharePoint-områdekobling eller et annen miljø fra samme skjema. Vil du for eksempel lage et skjema som viser og oppdaterer data fra SharePoint Online og det lokale SharePoint-miljøet samtidig? ingen fare. Hvis du installerer den [lokale datagatewayen](gateway-management.md), er du klar i løpet av noen minutter og kan koble til PowerApps, Power BI, Microsoft Flow og Azure Logic Apps med lokalt lagrede data. Ingen endringer i brannmurreglene er påkrevd. Du kan gå enda lengre ved å koble til denne appen med Microsoft Flow.

## <a name="a-standalone-sharepoint-app"></a>En frittstående SharePoint-app

Bruk denne teknikken hvis du ønsker å bygge en fullstendig, frittstående app basert på SharePoint-dataene i stedet for bare å oppdatere opplevelsen med listeskjemaet. Dette er også den beste måten å komme i gang på, slik at du kan begynne å lære hvordan PowerApps-lerretet fungerer og bygge fremtidens apper fra alle mulige datakilder.

Følg disse trinnene for å komme i gang:

1. Åpne SharePoint-listen som du ønsker å bygge en app fra.
1. Velg **PowerApps** på menylinjen, og velg deretter **Opprett en app**.
1. Gi den et navn, og velg **Opprett**.

PowerApps bygger en app til deg som du kan tilpasse.

I den første appen begynner du med en enkel, tilpasset liste med bare et par ulike typer felter. På denne måten kan du bygge et solid grunnlag uten å bli overveldet. Ikke bekymre deg, du vil raskt få taket på det og kan gå videre til mer kompliserte apper. Se denne [dokumentasjonen](app-from-sharepoint.md#generate-an-app-from-within-sharepoint-online) eller denne [fellesskapsvideoen](https://youtu.be/BnYe_7fpZRM) for å få hjelp til å gå gjennom den første appen din. Eksempelet under viser vanlige InfoPath-jobber og hvordan du utfører dem i PowerApps. Hver av disse bygger på en enkel SharePoint-listeapp.

## <a name="how-do-you-do-that-with-powerapps"></a>Hvordan gjør du dette med PowerApps?

Nå som du kjenner til de grunnleggende konseptene, kan vi gå videre. Når du har laget din første app, vil dette avsnittet hjelpe deg å ta i bruk noen av de vanligste InfoPath-konseptene i PowerApps.

**Skjul/vis/lås et felt basert på en verdi**  
Vellykkede skjemaer fremtvinger ofte streng forretningslogikk ved for eksempel å endre tilstanden til et felt basert på en verdi eller en handling. Med PowerApps kan du angi **DisplayMode**-egenskapen for en kontroll til **Rediger** eller **Vis** for å angi om en bruker kan endre feltet. Du kan også bruke en enkel **If**-formel for å gjøre dette på visse betingelser. Først velger du kortet som du vil redigere, og deretter velger du låsikonet. Dette trinnet låser opp kortet slik at du kan endre verdien.

![Skjule/vise/låse datakort](./media/transform-infopath/hide-show-lock.png)

I ruten til høyre ruller du til **Display Mode** -egenskapen, slik at du kan redigere den.

![If/Else-uttrykk](./media/transform-infopath/if-else-statement.png)

Bruk en **If**-formel i dette eksempelet:

```If(ThisItem.Color = "Blue"; DisplayMode.View; DisplayMode.Edit)```

Denne formelen angir at hvis det gjeldende elementets **Farge**-felt er **blått**, er **Dyr**-feltet skrivebeskyttet. Ellers kan feltet redigeres.

Hvis du vil skjule kortet i stedet for å gjøre det skrivebeskyttet, setter du inn en lignende funksjon i **Synlig**-egenskapen rett over **DisplayMode**.

Du kan for eksempel også prøve deg på å vise godkjenningsknappen bare hvis brukerens e-postadresse samsvarer med godkjennerens e-postadresse. Referanse Bruk **bruker (). E-post** for å få tilgang til den gjeldende brukerens e-postadresse.) Så du kan lagre godkjennerens e-postadresse i **YourDataCard** og angi knappens **Synlig**-egenskap etter denne formelen:

```If( YourDataCard.Text = User().Email; true; false )```

**Betinget formatering**  
På lignende måte som over, der du skjulte feltet, kan du også gi brukeren visuell tilbakemelding. Kanskje vil du gjøre teksten rød hvis den angitte verdien faller utenfor det godkjente området, eller endre teksten og fargen på en Last opp-knapp når brukeren laster opp en fil. Du kan gjøre begge ved hjelp av en funksjon, for eksempel **If**, for egenskaper som **Farge** eller **Synlig**.

Du kan for eksempel bruke **If**-funksjonen sammen med [IsMatch](functions/function-ismatch.md)-funksjonen for å endre tekstfargen på e-postfeltet til rødt hvis brukeren ikke har skrevet inn en gyldig e-postadresse. Du gjør dette ved å angi **Farge**-verdien for **TextInput1** (der brukeren skriver inn en e-postadresse) etter denne formelen:

```If( IsMatch(TextInput1.Text; Email); Black; Red )```

**IsMatch** støtter en rekke forhåndsdefinerte mønstre, for eksempel e-post, eller du kan opprette et selv. Du finner mer informasjon om betinget formatering i denne [fellesskapsvideoen](https://powerusers.microsoft.com/t5/Video-Webinar-Gallery/PowerApps-Conditional-Formatting-and-Popups/m-p/84962).

**Implementere rollebasert sikkerhet**  
Den første funksjonen du må vurdere, er [DataSourceInfo](functions/function-datasourceinfo.md). Hvilken informasjon som returneres fra datakilden, varierer, men du kan ofte bruke denne formelen til å bekrefte om brukeren har tilgang til å redigere dataene (erstatt *YourDataSource* med navnet på datakilden):

```DataSourceInfo( YourDataSource; DataSourceInfo.EditPermission )```

På denne måten kan du bare vise et skjema eller en knapp hvis brukeren har tilgang til å redigere. Sjekk [DataSourceInfo](functions/function-datasourceinfo.md)-dokumentasjonen for en fullstendig liste over informasjon som du kan bruke funksjonen til å spørre etter.

Du må gå dypere hvis du heller vil bruke Active Directory-grupper til å administrere tilgang til knapper eller skjemaer i appen. Hvis du vil gjøre dette, må du utnytte fleksibiliteten til PowerApps og opprette dine egne koblinger ved bruk av Microsoft Graph-API-en. Hvis dette høres skremmende ut, kan du følge dette [blogginnlegget](https://powerapps.microsoft.com/blog/implementing-role-based-permission/) for trinnvis veiledning.

**Sende en e-post fra appen**  
Du kan sende en e-postmelding fra PowerApps på mange måter, men det enkleste er å bruke Office 365 Outlook Connector. Med denne koblingen kan du sende en melding som deg selv fra appen. Du kan også motta e-postmeldinger og andre oppgaver som samhandler med innboksen din. Se [dokumentasjonen](connections/connection-office365-outlook.md) eller denne [fellesskapsvideoen](https://powerusers.microsoft.com/t5/Video-Webinar-Gallery/Send-an-email-from-PowerApps/m-p/74349) om hvordan du sender e-post.

Du kan sende mer komplekse meldinger (for eksempel som en del av en arbeidsflyt for SharePoint-godkjenning) ved å bruke Microsoft Flow og koble appen til flyten som du oppretter. Når du kobler appen din til Microsoft Flow, får du fullt utbytte av en arbeidsflytmotor som i likhet med PowerApps har svært gode tilkoblinger til eksterne data og tjenester. Se denne [dokumentasjonen](using-logic-flows.md) for mer informasjon om hvordan du kobler PowerApps og Microsoft Flow.

Hvis du fortsatt ikke har funnet e-postalternativet du ønsker, kan du også utnytte PowerApps-koblingene for Benchmark Email, Gmail, MailChimp, Outlook.com, SendGrid eller SMTP. Tilkoblingsmulighetene er PowerApps’ styrke.

**Arbeidsflyter**  
Det er vanskelig å snakke om forretningsapper og forretningslogikk uten en arbeidsflytmotor. Den gode nyheten er at PowerApps-teamet ikke har funnet opp hjulet på nytt og gir deg en annen arbeidsflytmotor. De gir deg i stedet en robust kobling til Microsoft Flow-tjenesten. Du kan automatisere prosesser og oppgaver på tvers av over [200 ulike tjenester](https://flow.microsoft.com/connectors/), ved å bruke den brukervennlige arbeidsflytmotoren. Se denne [dokumentasjonen](using-logic-flows.md) for mer informasjon om hvordan du kobler PowerApps og Microsoft Flow.

**Variabler med PowerApps**  
Når du bygger løsninger, er det naturlig å tenke at det må involvere variabler. Du finner flere typer variabler i PowerApps, men bruk dem bare når det er nødvendig. I stedet for å tenke på å hente data, lagre dem i en variabel og referere til denne variabelen kan du vurdere å referere til disse dataene direkte. Hvis du sammenligner modellen med Excel, er den lettere å forstå. I Excel er Total ikke en variabel, men summen av de andre feltene. Så hvis du vil bruke denne verdien et annet sted i regnearket, angir du cellen hvor du beregnet summen. [Dokumentasjonen](working-with-variables.md) forklarer dette på en god måte. Vær åpen for en ny måte å tenke på.

Hvis du fortsatt trenger en variabel (det er mange tilfeller der du trenger dem), vil dette hjelpe deg med å forstå de ulike alternativene. Husk at med PowerApps trenger du ikke å definere variabler. Bare bruk én av funksjonene til å angi et navn og en verdi som skal lagres, og variabelen er opprettet. Du kan vise variablene du har opprettet, ved å velge **Variabler** på **Visning**-fanen. Variabler oppbevares i minnet og verdiene slettes når du lukker appen. Du kan opprette disse typene variabler:

- Globale variabler er det du vanligvis først tenker på. Bruk [Angi](functions/function-set.md)-funksjonen til å angi en global verdi for variabelen og gjøre den tilgjengelig i hele appen:

    ```Set( YourVariable; YourValue )```

    Deretter kan du referere til *YourVariable* etter navn i hele appen.

- Kontekstvariabler er variabler som bare tilgjengelige på skjermbildet de defineres på. De tilbakestilles når du lukker skjermbildet. Disse brukes ofte til for eksempel å lagre informasjon som overføres fra et tidligere skjermbilde eller til å sjekke om skjemaet har blitt sendt inn. Hvis du vil angi en kontekstvariabel, kan du bruke [UpdateContext](functions/function-updatecontext.md)-funksjonen, som i dette eksemplet:

    ```UpdateContext( { Submitted: "true" } )```

    Dette eksemplet angir verdien for en variabel med navnet **Sendt** til **sann**. Du kan legge til denne formelen til **OnSelect**-egenskapen for en Send-knapp for å sjekke at informasjonen er sendt inn, og endre alle feltene til skrivebeskyttet.

- Samlinger lagrer tabeller med informasjon, som kan oppdateres enkeltvis. Bruk [Samle inn](functions/function-clear-collect-clearcollect.md) til å opprette en handlekurv, for eksempel når brukeren merker ulike SharePoint-elementer som de ønsker å sende. En [fellesskapsvideo](https://powerusers.microsoft.com/t5/Video-Webinar-Gallery/Learn-about-PowerApps-Collections/m-p/89180) viser dette konseptet i bruk.

**Rullegardinmenyer med undermenyer**  
Rullegardinmenyer med undermenyer er svært nyttige fordi du kan for eksempel filtrere valgene i én rullegardinmeny basert på verdien som er valgt i forrige rullegardinmeny. I PowerApps opprettes disse ofte ved å ha to datakilder i appen. Den første datakilden er dataene du viser eller oppdaterer, og den andre datakilden lagrer verdiene for å danne de undermenyene. Denne grafikken viser et eksempel på den andre datakilden med valgalternativene.

![Rullegardinmenyer med undermenyer](./media/transform-infopath/cascading-dropdowns.png)

I dette eksemplet kan du legge til en rullegardinliste med navnet **ddSelectType** og angi **Elementer**-egenskapen etter denne formelen:

```Distinct( Impacts; Title )```

Rullegardinlisten viser bare kostnader, programeffekt og tidsplan. Deretter kan du legge til neste rullegardinmeny og angi **Elementer**-egenskapen etter denne formelen:

```Filter( Impacts; ddSelectType.Selected.Value in SCategory )```

Og så enkelt lager du rullegardinmenyer med undermenyer. Hvis du vil ha mer informasjon, kan du ta en titt på dette innlegget fra PowerApps-teamet [SharePoint: Gjennom gripende rulle gardin lister i fire enkle trinn! ](https://powerusers.microsoft.com/t5/PowerApps-Community-Blog/SharePoint-Cascading-Dropdowns-in-4-Easy-Steps/ba-p/16248) eller denne [fellesskapsvideoen](https://powerusers.microsoft.com/t5/Video-Webinar-Gallery/PowerApps-Cascading-Dropdown/m-p/92813). Ikke bekymre deg, du kan gjøre det akkurat like enkelt uten SharePoint.

**Ikke bygg én superapp**  
Med PowerApps kan du kalle opp én app fra en annen. Så i stedet for det voldsomme InfoPath-skjemaet som holdes sammen med tyggegummi, kan du bygge en gruppe med apper som kaller opp hverandre. Du kan til og med sende data mellom appene, noe som gjør utviklingen enklere.

## <a name="next-steps"></a>Neste trinn

Takket være PowerApps og informasjonen over er du nå klar til å ta skrittet ut og erobre verden, én app om gangen. Nedenfor finner du noen nyttige koblinger som du kan ta med deg videre på reisen, for eksempel koblingen til nettområdet til PowerApps-fellesskapet. Bli en del av fellesskapet i dag, og utvid ferdighetene dine raskere enn du vil klare på egen hånd.

[**Formelreferanse**](formula-reference.md) – Bare det å se gjennom standardfunksjonene er alltid en god kilde til inspirasjon.

[**PowerApps-fellesskapet**](https://powerusers.microsoft.com/t5/PowerApps-Community/ct-p/PowerApps1) – Se eksempler, kom i kontakt med andre, still spørsmål, svar på andres spørsmål og bidra til å få PowerApps-fellesskapet å vokse.
