---
title: Presentasjoner av hovedskjemaer for modelldrevne apper i PowerApps | MicrosoftDocs
description: Finn ut hvordan hovedskjemaer ser ut når de vises på ulike enheter
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
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="how-model-driven-app-main-forms-appear-on-different-devices"></a>Hvordan mhovedskjemaer for modelldrevne apper ser ut på ulike enheter

Hovedskjemaet brukes av alle modelldrevne appklienter. Dette skjemaet inneholder en ensartet brukeropplevelse enten personen bruker en webleser, Dynamics 365 for phones, Dynamics 365 for tablets eller Dynamics 365 for Outlook.  
  
<a name="BKMK_MainFormPresentations"></a>   
## <a name="main-forms"></a>Hovedskjemaer  
 Hovedskjemaer som finnes for en enhet kan vises forskjellig avhengig av faktorer i tabellen nedenfor. Når du utformer et hovedskjema, må du vurdere hvordan det fungerer i de ulike presentasjonene.  
  
|Presentasjon|Beskrivelse|  
|------------------|-----------------|  
|**Oppdatert**|Når det gjelder [Oppdaterte enheter og klassiske enheter](create-design-forms.md#updated-versus-classic-entities) og eventuelle egendefinerte enheter i Dynamics 365 (online) og Dynamics 365 on-premises, gir det oppdaterte skjemaet en ny brukeropplevelse. Disse skjemaene har den nyere utformingen av kommandolinjen, og aktiverer flere funksjoner, for eksempel automatisk lagring og forretningsprosessflyter.|  
|**Dynamics 365 for tablets**| Dynamics 365 for tablets presenterer innholdet i hovedskjemaet på en måte som er optimalisert for et nettbrett.|  
|**Dynamics 365 for phones**| Dynamics 365 for phones presenterer innholdet i hovedskjemaet på en måte som er optimalisert for en telefon.|  
|**Klassisk**|Disse skjemaene er for enhetene som ikke er oppdatert. De bruker båndet i stedet for kommandolinjen og navigasjonsruten på venstre side av skjemaet.<br /><br /> Disse skjemaene har et oppsett med to kolonner.|  
  
<a name="BKMK_MainFormComponentsForUpdatedEntities"></a>   
## <a name="updated-forms"></a>Oppdaterte skjemaer  
 Dette diagrammet representerer vanlige komponenter som finnes i oppdaterte enhetsskjemaer.  
  
 ![Diagrammet viser struktur for oppdatert enhetsskjema i Dynamics 365](media/updated-form-diagram.png "Diagrammet viser struktur for oppdatert enhetsskjema i Dynamics 365")  
  
 For enheter som er oppdaterte fungerer oppsettet for skjemaet med et stort utvalg av skjermer og vindusstørrelser. Når bredden på vinduet reduseres, flyttes kategorikolonner ned slik at du kan rulle nedover for å arbeide med dem i stedet for at de komprimeres eller krever at du må rulle til høyre.  
  
 Tabellen nedenfor viser tilgjengelige komponenter i hovedskjemaet for oppdaterte enheter.  
  
|Komponent|Sammendrag|  
|---------------|-------------|  
|**Navigasjonsfelt**|Bruker dataene i områdekartet for å gi mulighet til å flytte til ulike områder i programmet.<br /><br /> Navigasjonsruten som brukes i klassiske skjemaer er ikke inkludert i det oppdaterte skjemaet. I konteksten til en oppføring vil navigasjonsfeltet gi tilgang til visninger av relaterte oppføringer. I stedet for å navigere til relaterte oppføringer ved hjelp av navigasjonsruten eller ved å bruke navigasjonsfeltet, gir det en bedre opplevelse for de fleste brukere hvis du legger til delrutenett som er konfigurert til å vise nyttige, relaterte enhetsoppføringer.|  
|**Kommandolinjen**|Bruker dataene som er definert for båndene til å gi kommandoer som er relevante for oppføringen.<br /><br /> De fem første kommandoene vises etterfulgt av en ellipse (![Flere kommandoer-knappen](media/not-available.gif "Flere kommandoer-knappen")) som inneholder en undermeny for å velge flere kommandoer.|  
|**Bilde**|Når en enhet har et bildefelt og enhetsalternativet **Hovedbilde** er satt til **Standardbilde**, kan et bilde vises i toppteksten når skjemaet er konfigurert til å vise bildet.|  
|**Topptekst**|Felt som er plassert i toppteksten forblir synlige når brukere ruller nedover i brødteksten i skjemaet.<br /><br /> Du kan plassere opptil fire felt i toppteksten. Flere linjer med tekst, webressurser eller iFrames er ikke tillatt i toppteksten. Topp- og bunnteksten deler enkelte egenskaper med inndelinger.|  
|**Prosesskontroll**|Når en enhet har aktive forretningsprosessflyter, vises prosesskontrollen nedenfor overskriften. Mer informasjon: [Forretningsprosessflyter](/flow/business-process-flows-overview)|  
|**Brødtekst**|Brødteksten er området på skjemaet som kan rulles og som inneholder kategoriene.|  
|**Kategorier**|Kategoriene utgjør vannrette skiller i brødteksten i skjemaet. Kategorier har en etikett som kan vises. Hvis etiketten vises, kan du vise eller skjule kategorier for å vise eller skjule innholdet i dem, ved å velge etiketten.<br /><br /> Kategorier inneholder opptil tre kolonner, og bredden på hver kolonne kan settes til en prosentandel av den totale bredden. Når du oppretter en ny kategori, blir hver kolonne forhåndsutfylt med en inndeling.|  
|**Inndelinger**|En inndeling opptar plassen som er tilgjengelig i en kategorikolonne. Inndelinger har en etikett som kan vises, og det kan vises en linje under etiketten.<br /><br /> Inndelinger kan ha opptil fire kolonner og inneholder alternativer for å vise hvordan etikettene for feltene i inndelingen vises.|  
|**Felt**|Feltene viser kontroller som brukere bruker til å vise eller redigere data i en enhetsoppføring. Feltene kan formateres slik at de bruker opptil fire kolonner i en inndeling.|  
|**Underlagsskive**|Et skille lar deg legge til et tomt område i en inndelingskolonne.|  
|**Delrutenett**|Delrutenett gjør det mulig å vise en liste i skjemaet. Muligheten til å vise diagrammer med et delrutenett er ikke tilgjengelig i skjemaer for oppdaterte enheter.|  
|**Hurtigvisningsskjema**|Et hurtigvisningsskjema viser data fra en oppføring som er referert av et oppslagsfelt i skjemaet. Enheten som er målet for oppslag, må ha et hurtigvisningsskjema før den kan legges til i skjemaet. Mer informasjon: [Opprette og redigere hurtigvisningsskjemaer](create-edit-quick-view-forms.md)|  
|**Webressurser**|HMTL- og Microsoft Silverlight-webressurser kan legges til hovedskjemaer, men de vil ikke vises når du bruker Dynamics 365 for phones og tablets.|  
|**iFrame**|En innebygd ramme som du konfigurerer til å vise en nettside fra et annet nettsted. **Viktig:**  <ul><li>Når siden som vises i en iFrame, er et annet domene, bruker nettlesere en høyere grad av sikkerhet. Dette kan komplisere kravene for samhandling av innholdet i en iFrame med data i skjemaet.</li><li>Visning av et enhetsskjema i en iFrame som er innebygd i et annet skjema for enheten, støttes ikke. 
|**Bing-kart**|Når denne kontrollen finnes i et skjema for en oppdatert enhet og systeminnstillingen **Aktiver Bing-kart** er aktivert med en gyldig nøkkel for Bing-kart, kan denne kontrollen brukes én gang i et skjema til å vise plasseringen av én av adressene i en oppdatert enhet. Mer informasjon: [Konfigurere Bing-kart](configure-bing-maps-legacy.md)|  
|**Bunntekst**|Du kan legge til et ubegrenset antall felt, webressurser eller iFrames i bunnteksten. Felt er skrivebeskyttet når de vises i bunnteksten. Topp- og bunnteksten deler enkelte egenskaper med inndelinger.|  
|**Statuslinjen**|Statuslinjen viser statusfeltet for oppføringen, en systemstatusfeltet og lagre-knappen.|  
  
<a name="BKMK_CRMforTabletsPresentation"></a>   
## <a name="dynamics-365-for-phones-and-tablets-forms"></a>Skjemaer for Dynamics 365 for telefoner og nettbrett  
 De fleste systemenheter og egendefinerte enheter er tilgjengelige for Dynamics 365 for phones og tablets. Hovedskjemaet for disse enhetene gjøres om til en presentasjon som er optimalisert for telefoner eller nettbrett.  
  
<a name="BKMK_EntitiesEnabledForCRMForTablets"></a>   
### <a name="entities-enabled-for-dynamics-365-for-phones-and-tablets"></a>Enheter som er aktivert for Dynamics 365 for telefoner og nettbrett  
 Bare enheter som er aktivert for Dynamics 365 for phones og tablets, bruker denne presentasjonen av hovedskjemaet. Mer informasjon: [Enheter som vises i Dynamics 365 for phones og tablets](https://docs.microsoft.com/dynamics365/customer-engagement/customize/customize-phones-tablets#BKMK_CustomEntity)  
  
### <a name="form-design"></a>Skjemautforming  
 Dynamics 365 for phones og tablets tar mange av elementene i hovedskjemaet og presenterer dem på en måte som er optimalisert for telefoner eller nettbrett. Følgende diagrammer viser tilbakeflyten fra webappen til nettbrett- og telefonappene.  
  
 **Webapp**  
  
 ![Tilbakeflyt av Dynamics 365-skjema fra webapp](media/custon-reflow-web-app.png "Tilbakeflyt av Dynamics 365-skjema fra webapp")  
  
 **Nettbrettapp**  
  
 ![Tilbakeflyt av Dynamics 365-skjema til nettbrettapp](media/reflow-tablet-app.png "Tilbakeflyt av Dynamics 365-skjema til nettbrettapp")  
  
 **Telefonapp**  
  
 ![Tilbakeflyt av Dynamics 365-skjema til telefonapp](media/custon-reflow-phone-app.png "Tilbakeflyt av Dynamics 365-skjema til telefonapp")  
  
 Skjemaelementer blir omgjort til et bredt panoramaoppsett i Dynamics 365 for tablets, der brukere kan sveipe på skjermen for å endre elementer som er synlige i et visningsområde. I Dynamics 365 for phones sveiper brukere på skjermen for å se en annen kolonne eller elementrute, og prosesskontroll vises over hver kolonne.  
  
### <a name="view-port-element"></a>Vise områdeelement  
 Følgende elementer vises alltid i visningsområdet i konteksten til et skjema:  
  
 **Navigasjonsfelt**  
 Navigasjonsfeltet er en presentasjon av områdekartet som er optimalisert for berøring. Mer informasjon: [Endre navigasjonsalternativer](https://docs.microsoft.com/dynamics365/customer-engagement/customize/customize-phones-tablets#BKMK_NavigationOptions)  
  
 **Hjem**  
 Hjem-knappen som tar brukere til instrumentbordet er startsiden for Dynamics 365 for phones og tablets.  
  
 **Prosesskontroll**  
 Hvis enheten har en forretningsprosess som er aktivert, vises den øverst i høyre hjørne ved siden av søkekontrollen i Dynamics 365 for tablets og øverst på skjermen i Dynamics 365 for phones.  
  
 **Søke**  
 Brukere kan trykke søkekontrollen for å åpne skjermbildet og søke etter oppføringer.  
  
 **Kommandolinje**  
 Noen av kommandoene som vises i appen som kjører i en nettleser, vises som standard ikke i apper for Dynamics 365 for phones og tablets. Kommandolinjen er, på lignende måte som webprogrammet, kontekstavhengig, så de tilgjengelige kommandoene endres avhengig av det som vises eller er valgt. Mer informasjon: [Endre kommandoer](https://docs.microsoft.com/dynamics365/customer-engagement/customize/customize-phones-tablets#BKMK_ChangeCommands)  
  
### <a name="form-elements"></a>Skjemaelementer  
 Skjemaelementene som vises, hentes fra hovedskjemaet og presenteres som en rekke paneler som brukere ser i visningsområdet.  
  
 I Dynamics 365 for tablets viser det første panelet kontaktinformasjon om relasjoner for oppføringen. I Dynamics 365 for phones viser det første panelet også overkriftsfelt fra skjemaet over relasjonsflisene.  
  
 ![Dynamics 365 for nettbrett, relasjonspanel](media/mobile-app-form-relationships.png "Dynamics 365 for nettbrett, relasjonspanel")  
  
 For kontakt- og brukerskjemaer viser det øverste element et kommunikasjonskort for oppføringen. Kommunikasjonskortet inneholder knapper for å starte kommunikasjon med brukeren. Kommunikasjonskort vises for andre enheter hvis det er et innebygd kontakthurtigvisningsskjema i hovedskjemaet.  
  
 Du kan vise flere fliser som er basert på enhetsrelasjoner, men du kan ikke tilpasse flisene for følgende enheter:  
  
|Enhet|Fliser|  
|------------|-----------|  
|Forretningsforbindelse|Eier|  
|Kontakt|Firmanavn, eier|  
|Kundeemne|Eier|  
|Salgsmulighet|Forretningsforbindelse, eier|  
  
 Du kan tilpasse de gjenværende flisene med skjemaredigeringsprogrammet. Rekkefølgen er fast, men du kan angi hvilke elementer som er synlige i relasjonspanelet.  
  
 I Dynamics 365 for tablets begynner det andre panelet med navnet på den første kategorien i skjemaet. Alle felt som er inkludert i toppteksten, inkluderes, og deretter innholdet i den første kategorien. I Dynamics 365 for phones vises topptekster i den første kolonnen.  
  
 ![CRM for nettbrett, skjema først-panel](media/mobile-app-form-first-panel.png "CRM for nettbrett, skjema først-panel")  
  
 Hvis det er en aktiv prosessflyt for skjemaet, viser den tredje kategorien aktiviteter for gjeldende trinn i prosessen i Dynamics 365 for tablets. I Dynamics 365 for phones flyter prosesskontrollen over rutene, utvides over brukerens gjeldende rute når den er valgt, og er alltid synlig og kan alltid vises.  
  
 Gjenværende paneler i skjemaet inneholder innholdet i kategoriene i skjemaet. Eventuelle delrutenett vises som et eget panel.  
  
 Skjemaet i Dynamics 365 for phones viser alltid etikettene for kategorier og delrutenett. Innstillingen **Vis etikett i skjemaet** brukes ikke.  
  
> [!NOTE]
>  Hvis du vil optimalisere ytelsen på mobilenheter, er antall objekter begrenset til 5 kategorier eller 75 felt og 10 delrutenett.  
  
 Skjemaer i Dynamics 365 for phones og tablets støtter ikke følgende:  
   
-   Bing-kart  
  
-   Yammer
  
-   Aktivitetsfeeder  
  
-   Bruk av tema  
  
 I tillegg er enhetsbilder synlige i listevisninger og kontaktkort, men ikke i det faktiske skjemaet.  
  
<a name="BKMK_MultipleForms"></a>   
### <a name="multiple-forms"></a>Flere skjemaer  
 Dynamics 365 for phones og tablets støtter flere skjemaer, men lar ikke brukere veksle mellom skjemaer hvis de har tilgang til mer enn ett. Brukere vil se det første skjemaet i skjemarekkefølgen som de har tilgang til.  
  
 Hvis du for eksempel har følgende hovedskjemaer for enheten for salgsmulighet og har tilordnet følgende sikkerhetsroller for hver enkelt, vil du se skjemarekkefølgen som vises i tabellen nedenfor.  
  
|Skjemarekkefølge|Skjemanavn|Sikkerhetsroller|  
|----------------|---------------|--------------------|  
|1|**Første salgsskjema**|Selger|  
|2|**Andre salgsskjema**|Selger og salgssjef|  
|3|**Tredje salgsskjema**|Salgsleder|  
|4|**Fjerde salgsskjema**|Viseadministrerende direktør for salg|  
  
-   Brukere med rollen Selger vil alltid se **Første salgsskjema**.  
  
-   Brukere med rollen Salgssjef vil alltid se **Andre salgsskjema**.  
  
-   Brukere med rollen Viseadministrerende direktør for salg vil alltid se **Fjerde salgsskjema**.  
  
<a name="BKMK_ClassicPresentation"></a>   
## <a name="classic-forms"></a>Klassisk skjemaer  
 Diagrammet nedenfor viser komponentene hovedskjemaet som brukes i den klassiske presentasjonen.  
  
 ![Hovedskjemaelementer](media/elements.png "Hovedskjemaelementer")  
  
 Skjemaene for oppdaterte enheter har arvet mange komponenter fra klassiske skjemaer, men det er store forskjeller.  
  
 Skjemaer som bruker den klassiske presentasjonen inneholder ikke navigasjonsfeltet, og båndet blir brukt i stedet for kommandolinjen. Disse skjemaene støtter ikke enhetsbilder, prosesskontroll, hurtigvisningsskjemaer, automatisk lagring eller Bing-kart. Feltene i toppteksten kan ikke redigeres.  
  
 Skjemahjelperen vises for enkelte enheter, for eksempel `Article`.  
  
## <a name="next-steps"></a>Neste trinn  
 [Opprette og utforme skjemaer](create-design-forms.md)   

 
