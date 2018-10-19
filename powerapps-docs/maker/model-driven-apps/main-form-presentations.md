---
title: Hovedskjema for presentasjoner av modelldrevne apper i PowerApps | MicrosoftDocs
description: Finn ut hvordan hovedskjemaer vises på ulike enheter
ms.custom: ''
ms.date: 06/27/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
author: Mattp123
ms.assetid: da3ac59a-5413-46cb-b355-1987e42e3853
caps.latest.revision: 35
ms.author: matp
manager: kvivek
ms.openlocfilehash: b8dee40f6dbeba62128434b3eb122add9cb0b373
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/08/2018
ms.locfileid: "39690848"
---
# <a name="how-model-driven-app-main-forms-appear-on-different-devices"></a>Hvordan hovedskjema for modelldrevne apper vises på ulike enheter

Hovedskjemaet brukes av alle modelldrevne appklienter. Dette skjemaet gir en konsekvent brukeropplevelse uansett om noen bruker en nettleser, Dynamics 365 for telefoner, Dynamics 365 for nettbrett eller Dynamics 365 for Outlook.  
  
<a name="BKMK_MainFormPresentations"></a>   
## <a name="main-forms"></a>Hovedskjemaer  
 Hvilken som helst hovedskjema som finnes for en enhet kan vises på forskjellige måter, avhengig av faktoren i tabellen nedenfor. Når du utformer et hovedskjema, bør du vurdere hvordan det fungerer i alle presentasjoner.  
  
|Presentasjon|Beskrivelse|  
|------------------|-----------------|  
|**Oppdatert**|Det oppdaterte skjemaet gir en ny brukeropplevelse for [oppdaterte og klassiske enheter](create-design-forms.md#updated-versus-classic-entities) og eventuelle egendefinerte enheter i Dynamics 365 (online) og Dynamics 365 lokalt. Disse skjemaene har den nye utformingen for kommandolinjen og aktivere flere funksjoner, som for eksempel automatisk lagring og flyter for forretningsprosesser.|  
|**Dynamics 365 for nettbrett**| Dynamics 365 for nettbrett presenterer innholdet i hovedskjemaet på en måte som er optimalisert for et nettbrett.|  
|**Dynamics 365 for telefoner**| Dynamics 365 for telefoner presenterer innholdet i hovedskjemaet på en måte som er optimalisert for en telefon.|  
|**Klassisk**|Disse skjemaene er for enheter som ikke er oppdaterte. De bruker båndet i stedet for kommandolinjen og navigasjonsruten på venstre side av skjemaet.<br /><br /> Disse skjemaene har et oppsett med to kolonner.|  
  
<a name="BKMK_MainFormComponentsForUpdatedEntities"></a>   
## <a name="updated-forms"></a>Oppdaterte skjemaer  
 Dette diagrammet representerer vanlige komponenter som finnes i oppdaterte enhetsskjemaer.  
  
 ![Diagrammet viser skjemastrukturen for oppdaterte enheter i Dynamics 365](media/updated-form-diagram.png "Diagrammet viser skjemastrukturen for oppdaterte enheter i Dynamics 365")  
  
 Oppsettet for skjemaet fungerer med mange typer skjermer og vindusstørrelser for oppdaterte enheter. Ettersom bredden på vinduet reduseres, flyttes fanekolonnene nedover, slik at du kan bla ned for å arbeide med dem i stedet for at de blir komprimert eller at du trenger å bla til høyre.  
  
 Tabellen nedenfor viser tilgjengelige komponenter i hovedskjemaet for oppdaterte enheter.  
  
|Komponent|Sammendrag|  
|---------------|-------------|  
|**Navigasjonsfelt**|Bruker dataene i områdekartet og gjør det mulig å flytte til ulike områder i programmet.<br /><br /> Navigasjonsruten som brukes i klassisk skjemaer er ikke inkludert i det oppdaterte skjemaet. I forbindelse med en post gir navigasjonsfeltet tilgang til visninger av relaterte poster. Underordnede rutenett som er konfigurert til å vise nyttige poster for relaterte enheter i stedet for å navigere til relaterte poster ved å bruke navigasjonsruten eller navigasjonsfeltet gir en bedre opplevelse for de fleste.|  
|**Kommandolinje**|Bruker dataene som er definert for båndene til å levere kommandoer som er relevante for posten.<br /><br /> De fem første kommandoene vises etterfulgt av en ellipse (![Flere kommandoer-knapp](media/not-available.gif "Flere kommandoer-knapp")) som viser en undermeny hvor flere kommandoer kan velges.|  
|**Bilde**|Når en enhet har et bildefelt og alternativet **Primærbilde** for enheten er satt til **Standardbilde**, kan et bilde vises i toppteksten når skjemaet er konfigurert til å vise det.|  
|**Topptekst**|Felt som er plassert i toppteksten forblir synlige når brødteksten i skjemaet rulles nedover.<br /><br /> Opptil fire felt kan plasseres i toppteksten. Flere linjer med tekst, nettressurser eller iFrames er ikke tillatt i toppteksten. Topptekst og bunntekst har noen av de samme egenskapene som inndelinger.|  
|**Prosesskontroll**|Når en enhet har aktive flyter for forretningsprosesser vises prosesskontrollen under overskriften. Mer informasjon: [Flyter for forretningsprosesser](/flow/business-process-flows-overview)|  
|**Brødtekst**|Brødteksten er delen av skjemaet som inneholder fanene og som kan rulles.|  
|**Faner**|Med faner kan brødteksten i skjemaet deles vannrett. Fanene har en etikett som kan vises. Hvis etiketten vises, kan du velge den for å vise eller skjule innholdet.<br /><br /> Faner inneholder opptil tre kolonner, og bredden på hver kolonne kan angis til en prosentdel av den totale bredden. Når du oppretter en ny fane er hver kolonne forhåndsutfylt med en inndeling.|  
|**Inndelinger**|En inndeling bruker den tilgjengelige plassen i en fanekolonne. Inndelingene har en etikett som kan vises, og det kan vises en linje under etiketten.<br /><br /> Inndelinger kan ha opptil fire kolonner og inneholder alternativer for hvordan etiketter for feltene i inndelingen vises.|  
|**Felt**|Felt viser kontrollene som brukes til å vise eller redigere data i en enhetspost. Felt kan formateres slik at de bruker opptil fire kolonner i en inndeling.|  
|**Avstand**|En avstand gjør det mulig å legge til et tomt område i en inndelingskolonne.|  
|**Underordnede rutenett**|Underordnede rutenett tillater visning av en liste i skjemaet. Muligheten til å vise diagrammer med et underordnet rutenett er ikke tilgjengelig i skjemaer for oppdaterte enheter.|  
|**Hurtigvisningsskjema**|Et hurtigvisningsskjema viser data fra en post som refereres av et oppslagsfelt i skjemaet. Enheten som er målet for oppslaget, må ha et hurtigvisningsskjema før en kan legges til i skjemaet. Mer informasjon: [Opprett og redigere hurtigvisningsskjemaer](create-edit-quick-view-forms.md)|  
|**Nettressurser**|HTML- og Microsoft Silverlight-nettressurser kan legges til hovedskjemaer, men de vil ikke vises når du bruker Dynamics 365 for telefoner og nettbrett.|  
|**iFrame**|En innebygd ramme som du konfigurerer for å vise en nettside fra et annet nettområde. **Viktig:**  <ul><li>Når siden som vises i en iFrame, er på et annet domene, bruker nettlesere et høyere nivå av sikkerhet. Dette kan komplisere kravene for at innholdet i en iFrame skal kunne samhandle med dataene i skjemaet.</li><li>Visning av et enhetsskjema i en iFrame som er innebygd i et annet enhetsskjema, støttes ikke. 
|**Bing-kart**|Når denne kontrollen er tilstede i et skjema for en oppdatert enhet og systeminnstillingen **Aktiver Bing-kart** er aktivert med en gyldig nøkkel for Bing-kart, kan kontrollen brukes i et skjema til å vise plasseringen for en av adressene i en oppdatert enhet en gang. Mer informasjon: [Konfigurasjon av Bing-kart](configure-bing-maps-legacy.md)|  
|**Bunntekst**|Et ubegrenset antall felt, nettressurser eller iFrames kan legges til i bunnteksten. Feltene er skrivebeskyttet bare når de vises i bunnteksten. Topptekst og bunntekst har noen av de samme egenskapene som inndelinger.|  
|**Statuslinje**|Statuslinjen viser statusfeltet for posten, et varselfelt og en knapp for lagring.|  
  
<a name="BKMK_CRMforTabletsPresentation"></a>   
## <a name="dynamics-365-for-phones-and-tablets-forms"></a>Skjemaer for Dynamics 365 for telefoner og nettbrett  
 De fleste systemenheter og egendefinerte enheter er tilgjengelige for Dynamics 365 for telefoner og nettbrett. Hovedskjemaet for disse enhetene endres til en presentasjon som er optimalisert for telefoner og nettbrett.  
  
<a name="BKMK_EntitiesEnabledForCRMForTablets"></a>   
### <a name="entities-enabled-for-dynamics-365-for-phones-and-tablets"></a>Enheter som er aktivert for Dynamics 365 for telefoner og nettbrett  
 Bare enheter som er aktivert for Dynamics 365 for telefoner og nettbrett, bruker denne presentasjonen av hovedskjemaet. Mer informasjon: [Enheter vist i Dynamics 365 for telefoner og nettbrett](https://docs.microsoft.com/dynamics365/customer-engagement/customize/customize-phones-tablets#BKMK_CustomEntity)  
  
### <a name="form-design"></a>Skjemautforming  
 Dynamics 365 for telefoner og nettbrett tar mange av elementene fra hovedskjemaet og presenterer dem på en måte som er optimalisert for telefoner og nettbrett. Disse diagrammene viser dynamisk tilpasning fra nettapp til apper for nettbrett og telefon.  
  
 **Nettapp**  
  
 ![Dynamisk tilpasning fra nettapp for Dynamics 365-skjema](media/custon-reflow-web-app.png "Dynamisk tilpasning fra nettapp for Dynamics 365-skjema")  
  
 **Nettbrettapp**  
  
 ![Dynamisk tilpasning fra nettbrettapp for Dynamics 365-skjema](media/reflow-tablet-app.png "Dynamisk tilpasning fra nettbrettapp for Dynamics 365-skjema")  
  
 **Telefonapp**  
  
 ![Dynamisk tilpasning fra telefonapp for Dynamics 365-skjema](media/custon-reflow-phone-app.png "Dynamisk tilpasning fra telefonapp for Dynamics 365-skjema")  
  
 Skjemaelementene endres til et bredt panoramaoppsett i Dynamics 365 for nettbrett, hvor brukere sveiper på skjermen for å endre elementer som er synlige i en visningsport. I Dynamics 365 for telefoner sveiper brukere på skjermen for å se en annen kolonne eller rute med elementer, og prosesskontrollen vises over hver kolonne.  
  
### <a name="view-port-element"></a>Vis portelement  
 Disse elementene er alltid synlige i visningsporten i forbindelse med et skjema:  
  
 **Navigasjonsfelt**  
 Navigasjonsfeltet er en presentasjon av områdekartet som er optimalisert for berøring. Mer informasjon: [Endre navigasjonsalternativer](https://docs.microsoft.com/dynamics365/customer-engagement/customize/customize-phones-tablets#BKMK_NavigationOptions)  
  
 **Hjem**  
 Hjem-knappen flytter brukere til instrumentbordet som er startsiden for Dynamics 365 for telefoner og nettbrett.  
  
 **Prosesskontroll**  
 Hvis enheten har en forretningsprosess aktivert, vises den i øvre høyre hjørne ved siden av søkekontrollen i Dynamics 365 for nettbrett, og øverst på skjermen i Dynamics 365 for telefoner.  
  
 **Søk**  
 Trykk på søkekontrollen for å åpne skjermen for å søke etter poster.  
  
 **Kommandolinje**  
 Som standard vises noen kommandoer som vises i appen hvis den kjøres i en nettleser, ikke i Dynamics 365 for telefon- og nettbrettapper. I likhet med nettappen, er kommandolinjen kontekstavhengig, slik at de tilgjengelige kommandoene endres avhengig av hva som vises eller er valgt. Mer informasjon [Endre kommandoer](https://docs.microsoft.com/dynamics365/customer-engagement/customize/customize-phones-tablets#BKMK_ChangeCommands)  
  
### <a name="form-elements"></a>Skjemaelementer  
 Skjemaelementene som vises, er tatt fra hovedskjemaet og vises som en rekke paneler brukerne ser gjennom visningsporten.  
  
 I Dynamics 365 for nettbrett viser det første panelet kontaktinformasjon om relasjoner for posten. I Dynamics 365 for telefoner viser det første panelet også topptekstfeltet fra skjemaet ovenfor relasjonsflisene.  
  
 ![Relasjonspanel for Dynamics 365 for nettbrett](media/mobile-app-form-relationships.png "Relasjonspanel for Dynamics 365 for nettbrett")  
  
 I kontakt- og brukerskjemaer viser det øverste elementet et kommunikasjonskort for posten. Kommunikasjonskortet inneholder knapper for å starte kommunikasjon med personen. For andre enheter vises et kommunikasjonskort hvis det er et hurtigvisningsskjema for kontakt innebygd i hovedskjemaet.  
  
 Du kan vise flere fliser som er basert på enhetsrelasjoner, men du kan ikke tilpasse flisene for følgende enheter:  
  
|Enhet|Fliser|  
|------------|-----------|  
|Konto|Eier|  
|Kontakt|Firmanavn, eier|  
|Kundeemne|Eier|  
|Salgsmulighet|Konto, eier|  
  
 Du kan tilpasse de gjenværende flisene med redigeringsprogrammet for skjema. Rekkefølgen er låst, men du kan angi hvilke elementer som skal vises i relasjonspanelet.  
  
 I Dynamics 365 for nettbrett begynner det andre panelet med navnet på den første fanen i skjemaet. Alle felten som er inkludert i toppteksten, er inkludert, og deretter innholdet i den første fanen. I Dynamics 365 for telefoner vises topptekster i den første kolonnen.  
  
 ![Første panel for skjema for CRM for Nettbrett](media/mobile-app-form-first-panel.png "Første panel for skjema for CRM for Nettbrett")  
  
 Hvis det er en aktiv prosessflyt i skjemaet, viser den tredje fanen i Dynamics 365 for nettbrett oppgaver for det gjeldende trinnet i prosessen. I Dynamics 365 for telefoner flyter prosesskontrollen over rutene, utvider seg over brukerens gjeldende rute når kontrollen er valgt, og er alltid synlig og klar til bruk.  
  
 De gjenværende panelene i skjemaet inneholder faneinnholdet i skjemaet. Alle underordnede rutenett som finnes, vises som et separat panel.  
  
 Skjemaet for Dynamics 365 for telefoner og nettbrett viser alltid etikettene for faner og underordnede rutenett. Innstillingen **Vis etikett på skjemaet** brukes ikke.  
  
> [!NOTE]
>  For å optimalisere ytelsen på mobile enheter er antall objekter begrenset til 5 faner eller 75 felt og 10 underordnede rutenett.  
  
 Skjemaer for Dynamics 365 for telefoner og nettbrett støtter ikke disse:  
   
-   Bing-kart  
  
-   Yammer
  
-   Aktivitetsfeeder  
  
-   Bruk av tema  
  
 I tillegg vises enhetsbilder i listevisninger og kontaktkort, men ikke i det gjeldende skjemaet.  
  
<a name="BKMK_MultipleForms"></a>   
### <a name="multiple-forms"></a>Flere skjemaer  
 Dynamics 365 for telefoner og nettbrett støtter flere skjemaer, men viser ikke hvordan brukere kan bytte mellom skjemaer hvis de har tilgang til mer enn ett. Brukere vil se det første skjemaet de har tilgang til, i skjemarekkefølgen.  
  
 Hvis du for eksempel har disse hovedskjemaene for mulighetsenheten og har tilordnet de følgende sikkerhetsroller for hvert skjema, ser du skjemarekkefølgen som vises i tabellen nedenfor.  
  
|Skjemarekkefølge|Skjemanavn|Sikkerhetsroller|  
|----------------|---------------|--------------------|  
|1|**Første salgsskjema**|Selger|  
|2|**Andre salgsskjema**|Selger og salgssjef|  
|3|**Tredje salgsskjema**|Salgssjef|  
|4|**Fjerde salgsskjema**|Salgsdirektør|  
  
-   Personer med rollen selger vil alltid se **Første salgsskjema**.  
  
-   Personer med rollen salgssjef vil alltid se **Andre salgsskjema**.  
  
-   Personer med rollen salgsdirektør vil alltid se **Fjerde salgsskjema**.  
  
<a name="BKMK_ClassicPresentation"></a>   
## <a name="classic-forms"></a>Klassiske skjemaer  
 Diagrammet nedenfor viser de vanligste skjemakomponentene som brukes i den klassiske presentasjonen.  
  
 ![Viktige skjemaelementer](media/elements.png "Viktige skjemaelementer")  
  
 Skjemaene for oppdaterte enheter har arvet mange komponenter fra de klassiske skjemaene, men det finnes viktige forskjeller.  
  
 Skjemaer som bruker den klassiske presentasjonen, inkluderer ikke navigasjonsfeltet, og båndet brukes i stedet for kommandolinjen. Disse skjemaene støtter ikke enhetsbilder, prosesskontrollen, hurtigvisningsskjemaer, automatisk lagring eller Bing-kart. Feltene i toppteksten kan ikke redigeres.  
  
 Skjemaassistenten vises for enkelte enheter, for eksempel `Article`.  
  
## <a name="next-steps"></a>Neste trinn  
 [Opprette og utforme skjemaer](create-design-forms.md)   

 
