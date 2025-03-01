---
title: Bruk løsningskontroll til å validere appene i PowerApps | Microsoft Docs
description: Bruk løsningskontrollen til å validere løsningen.
author: Mattp123
manager: kvivek
ms.service: powerapps
ms.component: cds
ms.topic: article
ms.date: 07/09/2019
ms.author: matp
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="use-solution-checker-to-validate-your-model-driven-apps-in-powerapps"></a>Bruk løsningskontroll til å validere de modelldrevne appene i PowerApps

For å overholde komplekse forretningskrav kan produsenter av modelldrevne apper ofte ende opp med svært avanserte løsninger som tilpasser og utvider Common Data Service-plattformen. Med avanserte implementeringer kommer økt risiko der problemer med ytelse, stabilitet og pålitelighet blir introdusert, som kan ha en negativ innvirkning på brukeropplevelsen. Å identifisere og forstå hvordan du løser disse problemene kan være komplisert og tidkrevende. Med løsningskontrollen kan du utføre en omfattende statisk analysekontroll av løsningene mot et sett med regler for beste fremgangsmåte og raskt finne disse problematiske mønstrene. Når kontrollen er fullført, får du en detaljert rapport som viser en liste over problemene som ble funnet, komponentene og koden som er berørt, og koblinger til dokumentasjon som beskriver hvordan du løser hvert enkelt problem.

Løsningskontrollen analyserer disse løsningskomponentene: 
- Common Data Service-plugin-moduler
- Egendefinerte Common Data Service-arbeidsflytaktiviteter 
- Common Data Service-webressurser (HTML og JavaScript)
- Common Data Service-konfigurasjoner, for eksempel SDK-meldingstrinn 

Løsningskontroll fungerer sammen med uadministrerte løsninger som kan eksporteres fra et miljø. 

> [!NOTE]
> - Dette emnet forklarer hvordan du kjører løsningskontroll fra PowerApps-utviklerportalen. En PowerShell-modul er også tilgjengelig og kan brukes til å samhandle direkte med tjenesten. Microsoft.PowerApps.Checker.PowerShell-modulen kan brukes til å analysere administrerte og uadministrerte løsninger for støttede versjoner av lokale og nettbaserte miljøer, eller for å automatisere og integrere tjenesten i dine egne køer for utvikling og lansering. Mer informasjon: [Microsoft.Powerapps.Checker.PowerShell-oversikt]( /powershell/powerapps/overview?view=pa-ps-latest#get-started-using-the-microsoftpowerappscheckerpowershell-module) 
> - Løsningskontroll fungerer ikke med løsninger som inneholder JavaScript som bruker ECMAScript 6 (2015) eller senere versjoner. Når JavaScript ved hjelp av disse versjonene blir funnet, rapporteres et problem med JS001-syntaksen for webressursen.

## <a name="enable-the-solution-checker"></a>Aktivere løsningskontrollen
Løsningskontrollen er aktivert som standard i alle Common Data Service-miljøer. En **Løsningskontroll**-meny er tilgjengelig når du velger en uadministrert løsning i **Løsninger**-området i PowerApps. Hvis alternativet **Kjør** ikke er tilgjengelig på **Løsningskontroll**-menyen, kan du aktivere det ved å installere løsningen for PowerApps-sjekk. Installer det ved å følge disse trinnene:   

1. Logg på [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) og velg Common Data Service-miljøet der du ønsker å aktivere løsningskontrollen. 
2. I navigasjonsruten til venstre velger du **Løsninger**.
3. Velg **Løsningskontroll** på verktøylinjen, og deretter **Installer** – dette åpner siden Microsoft AppSource. Hvis webleseren blokkerer siden, må du tillate popup-vinduer. 

   > [!div class="mx-imgBorder"]
   > ![Installere løsningskontroll](media/solution-checker-install.png "Installere løsningskontroll")

4. Velg **Gratis prøveversjon** på siden AppSource. 

5. Hvis du er enig, godtar du vilkårene og velger miljøet du vil installere PowerApps-kontrollerløsningen i. 
6. Når installasjonen er fullført, kan du oppdatere **Løsning**-listen på PowerApps-nettstedet for å bekrefte at løsningskontrollen er tilgjengelig.  
7. Du kan kontrollere en løsning ved å [kjøre løsningskontrollen](#run-the-solution-checker).


<!-- ### Components created with the PowerApps checker
When you install the PowerApps checker these solution specific components are created. 
- Entities: The entities that are created are required to store the results of solution analysis and the status of analysis jobs in your environment.
   - Analysis Component
   - Analysis Job
   - Analysis Result
- System job: A system job is created so admins can remove solution analysis data from the environment. The job contains a configuration value, currently set to remove the solution analysis data after 60 days, which an administrator can override. 
- Security Roles: Two security roles, **Export Customizations**, and **Solution Checker** are created. These roles are required to export the solution for analysis, and storing the analysis results to the entities in your environment.
- User principle: The **PowerApps Advisor** user is created that allows the checker to authenticate with your Common Data Service environment and assign the two security roles, Export Customizations and Solution Checker. The PowerApps Advisor is an application user and does not consume a license.  -->

## <a name="run-the-solution-checker"></a>Kjøre løsningskontrollen
Når du har installert den PowerApps-kontrollen i miljøet, er et **Løsningskontroll**-menyelement tilgjengelig når du velger en uadministrert løsning i **Løsninger** -området i PowerApps. 

1. Logg på [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc). 
2. Velg **Løsninger** i venstre rute. 
3. Ved siden av den uadministrerte løsningen du vil analysere, velger du **...**, peker på **Løsningskontroll**, og velger deretter **Kjør**. 

   > [!div class="mx-imgBorder"]
   > ![Kjøre løsningskontroll-kommandoen](media/solution-checker-run.png "Kjøre løsningskontroll-kommandoen")

4.  Statusruten øverst til høyre på **Løsninger**-siden viser **Løsningskontroll kjører**. 

    > [!div class="mx-imgBorder"]
    > ![Status for løsningskontroll](media/solution-checker-status.png "Status for løsningskontroll")
   
    Legg merke til følgende:
    - Løsningskontrollen kan bruke noen minutter på å fullføre analysen. 
    
    - I denne perioden vises tilstanden **Kjører...** i **Løsningskontroll**-kolonnen i **Løsning**-listen. 
    
    - Du mottar en e-postvarsling og en varsling i **Varslinger**-området på PowerApps-nettstedet når kontrollen fullføres.  

5.  [Vis rapporten](#review-the-solution-checker-report) når kontrollen er fullført.

## <a name="cancel-a-check"></a>Avbryte en kontroll

Når du har sendt en løsningskontroll i miljøet, kan kontrollen avbrytes gjennom statusruten i det øvre høyre området på **Løsninger**-siden. 

Når du avbryter en kontroll, slutter løsningskontrollen å kjøre og statusen for løsningskontrollen returnerer til forrige tilstand. 

## <a name="solution-checker-states"></a>Tilstander for løsningskontroll
Når du installerer løsningskontrollen i miljøet, blir **Løsningskontroll**-kolonnen tilgjengelig i **Løsninger**-listen. Denne kolonnen viser løsningsanalysetilstandene for en løsning. 

|Tilstand  |Beskrivelse  |
|---------|---------|
|Er ikke kjørt    | Løsningen er aldri analysert.        |
|Kjører     | Løsningen blir analysert.       |
|Kunne ikke fullføres     |  Løsningsanalysen ble forespurt, men analysen ble ikke fullført.       |
|Resultater for *dato og klokkeslett*   | Løsningsanalysen er fullført og resultater er tilgjengelig for nedlasting.      |
|Kunne ikke fullføres. Resultat for *dato og klokkeslett*     | Den nyeste analyseforespørselen ble ikke fullført. De siste vellykkede resultatene kan lastes ned.         |
|Kontrollert av Microsoft     | Dette er en Microsoft-administrert løsning. Løsningsanalyse er ikke tillatt i disse løsningene.         |
|Kontrollert av utgiver     | Dette er en tredjepart-administrert løsning. Løsningsanalyse er for øyeblikket ikke tilgjengelig for disse løsningene.        |


## <a name="review-the-solution-checker-report"></a>Se gjennom løsningskontrollrapporten
Når en løsningskontroll er fullført, kan du vise analyserapporten i portalen, eller du kan laste ned rapporten fra webleseren. I portalen har du alternativer for å filtrere, gruppere resultater etter **Problem**, **Sted** eller **Alvorlighetsgrad** og vise detaljert informasjon om problemer som er oppdaget i løsningen. 

1. Velg **Løsninger** i venstre rute.
2. Ved siden av den uadministrerte løsningen der du vil vise løsningskontrollrapporten, velger du **...**, peker på **Løsningskontroll** og velger deretter **Vis resultater**.  
3. Velg et problem for å vise detaljer og veiledning for hvordan du løser problemet.

    > [!div class="mx-imgBorder"] 
    > ![](media/solution-checker-viewresults.png "Visningsresultater for løsningskontroll")

Løsningskontrollresultatene er også tilgjengelige for nedlasting. Zip-filen for løsningskontrollen lastes ned i mappen som er angitt av webleseren. Nedlastingsrapporten er i [!INCLUDE [pn-excel-short](../../includes/pn-excel-short.md)]-format og inneholder flere visualiseringer og kolonner som hjelper deg med å identifisere innvirkningen på, typen og plasseringen av hvert problem som registreres i løsningen. En kobling til detaljert informasjon om hvordan du løser problemet, er også oppgitt. 

1. Velg **Løsninger** i venstre rute.
2. Ved siden av den uadministrerte løsningen der du vil laste ned løsningskontrollrapporten, velger du **...**, peker på **Løsningskontroll** og velger deretter **Last ned resultater**.  
3. Zip-filen for løsningskontroll lastes ned til mappen som er angitt i webleseren.

Her er et sammendrag av hver kolonne i rapporten.

|Rapportfelt |Beskrivelse  |Gjelder for komponent   |
|---------|---------|---------|
|Problem     |   Tittelen på problemet som er identifisert i løsningen.      | Alle        |
|Kategori     | Kategorisering av problemet som er identifisert, for eksempel **Ytelse**, **Bruk** eller **Støtte**.      |  Alle     |
|Alvorlighetsgrad     | Representerer den potensielle virkningen av problemet som identifiseres. Tilgjengelige innvirkningstyper er **høy**, **medium**, **lav** og **informasjon**.         |  Alle       |
|Veiledning     |  Kobling til artikkelen med detaljer om problemet, innvirkning og anbefalt handling.       |  Alle       |
|Komponent     |  Løsningskomponenten der problemet ble identifisert.        |   Alle      |
|Location     |  Plasseringen og/eller kildefilen til komponenten der problemet som ble funnet, oppstod, for eksempel samlingen eller JavaScript-filnavnet.        |  Alle       |
|Linjenr.     |  Linjenummerreferansen til problemet i den berørte webressurskomponenten.       |  Webressurser       |
|Modul     | Navn på modul der problemet som ble identifisert i samlingen, ble oppdaget.     |   Plugin-modul eller egendefinert arbeidsflytaktivitet      |
|Type     | Type problem som ble identifisert i samlingen.        | Plugin-modul eller egendefinert arbeidsflytaktivitet        |
|Medlem     |  Medlem av problemet som ble identifisert i samlingen.      | Plugin-modul eller egendefinert arbeidsflytaktivitet        |
|Setning     | Kodesetningen eller konfigurasjonen som førte til problemet.        |  Alle       |
|Kommentarer     | Informasjon om problemet som inkluderer løsningstrinn på høyt nivå.         |  Alle       |


## <a name="best-practice-rules-used-by-solution-checker"></a>Regler for anbefalt fremgangsmåte som brukes av løsningskontrollen

|Løsningskomponent  |Navn på regel  |Regelbeskrivelse  |
|---------|---------|---------|
|Plugin-modul eller arbeidsflytaktivitet   | [il-specify-column](http://go.microsoft.com/fwlink/?LinkID=398563&error=il-specify-column&client=PAChecker&source=featuredocs)  | Unngå å velge alle kolonner via spørrings-API-er for Dynamics 365 for Customer Engagement.     |
|Plugin-modul eller arbeidsflytaktivitet   | [meta-remove-dup-reg](http://go.microsoft.com/fwlink/?LinkID=398563&error=meta-remove-dup-reg&client=PAChecker&source=featuredocs)     | Unngå duplikate plugin-modul-registreringer for Dynamics 365 for Customer Engagement.     |
|Plugin-modul eller arbeidsflytaktivitet   | [il-turn-off-keepalive](http://go.microsoft.com/fwlink/?LinkID=398563&error=il-turn-off-keepalive&client=PAChecker&source=featuredocs)   | Angi Vedlikehold til usann når du bruker eksterne verter i plugin-modulen Dynamics 365 for Customer Engagement.     |
|Plugin-modul eller arbeidsflytaktivitet   | [il-avoid-unpub-metadata](http://go.microsoft.com/fwlink/?LinkID=398563&error=il-avoid-unpub-metadata&client=PAChecker&source=featuredocs)   | Unngå å hente upubliserte metadata for Dynamics 365 for Customer Engagement.     |
|Plugin-modul eller arbeidsflytaktivitet   | [il-avoid-batch-plugin](http://go.microsoft.com/fwlink/?LinkID=398563&error=il-avoid-batch-plugin&client=PAChecker&source=featuredocs)   | Unngå å bruke satsvise forespørselstyper i plugin-moduler og arbeidsflytsaktiviteter for Dynamics 365 Customer Engagement.    |
|Plugin-modul eller arbeidsflytaktivitet   | [meta-avoid-reg-no-attribute](http://go.microsoft.com/fwlink/?LinkID=398563&error=meta-avoid-reg-no-attribute&client=PAChecker&source=featuredocs)  | Inkluder filtreringsattributter med registreringer for Dynamics 365 for Customer Engagement-plugin-modulen.    |
|Plugin-modul eller arbeidsflytaktivitet   | [meta-avoid-reg-retrieve](http://go.microsoft.com/fwlink/?LinkID=398563&error=meta-avoid-reg-retrieve&client=PAChecker&source=featuredocs)  | Vær forsiktig med Dynamics 365 for Customer Engagement-plugin-moduler som er registrert for Retrieve- og RetrieveMultiple-meldinger.    |
|Plugin-modul eller arbeidsflytaktivitet   | [meta-remove-inactive](http://go.microsoft.com/fwlink/?LinkID=398563&error=meta-remove-inactive&client=PAChecker&source=featuredocs)    | Fjerne inaktive konfigurasjoner i Dynamics 365 for Customer Engagement.    |
|Plugin-modul eller arbeidsflytaktivitet   | [il-meta-avoid-crm2011-depr-message](http://go.microsoft.com/fwlink/?LinkID=398563&error=il-avoid-crm2011-depr-message&client=PAChecker&source=featuredocs)  | Ikke bruk Microsoft Dynamics CRM 2011-avskrevede meldinger.     |
|Plugin-modul eller arbeidsflytaktivitet   | [meta-avoid-crm4-event](http://go.microsoft.com/fwlink/?LinkID=398563&error=meta-avoid-crm4-event&client=PAChecker&source=featuredocs) | Ikke bruk fase for registrering av plugin-modul for Microsoft Dynamics CRM 4.0.    |
|Plugin-modul eller arbeidsflytaktivitet   | [il-avoid-specialized-update-ops](http://go.microsoft.com/fwlink/?LinkID=398563&error=il-avoid-specialized-update-ops&client=PAChecker&source=featuredocs)  | Ikke bruk spesialiserte oppdateringsoperasjonsforespørsler i Dynamics 365 for Customer Engagement.    | 
| Plugin-modul eller arbeidsflytaktivitet |  [il-use-autonumber-feature](http://go.microsoft.com/fwlink/?LinkID=398563&error=il-use-autonumber-feature&client=PAChecker)  |Bruk den automatiske tallfunksjonen i stedet for en tilpasset automatisk nummereringsløsning. | 
| Plugin-modul eller arbeidsflytaktivitet  | [il-avoid-parallel-plugin](http://go.microsoft.com/fwlink/?LinkID=398563&error=il-avoid-parallel-plugin&client=PAChecker)  | Bruken av parallelle mønstre bør unngås i plugin-moduler.  |
| Plugin-modul eller arbeidsflytaktivitet  | [il-avoid-lock-plugin](http://go.microsoft.com/fwlink/?LinkID=398563&error=il-avoid-lock-plugin&client=PAChecker)  | Unngå låsing av statiske medlemmer i plugin-moduler.  |
| Plugin-modul eller arbeidsflytaktivitet  | [meta-avoid-retrievemultiple-annotation](http://go.microsoft.com/fwlink/?LinkID=398563&error=meta-avoid-retrievemultiple-annotation&client=PAChecker)  | Unngå å registrere en plugin-modul på RetrieveMultiple av merknader.  |
|Webressurser  | [web-use-async](http://go.microsoft.com/fwlink/?LinkID=398563&error=web-use-async&client=PAChecker&source=featuredocs)  |  Samhandle med HTTP- og HTTPS-ressurser asynkront.   |
|Webressurser  | [meta-remove-invalid-form-handler](http://go.microsoft.com/fwlink/?LinkID=398563&error=meta-remove-invalid-form-handler&client=PAChecker&source=featuredocs)  | Korriger eller fjern ugyldig skjema for registrering av hendelser for Dynamics 365 for Customer Engagement.   |
|Webressurser  | [meta-remove-orphaned-form-element](http://go.microsoft.com/fwlink/?LinkID=398563&error=meta-remove-orphaned-form-element&client=PAChecker&source=featuredocs)  | Korriger eller fjern isolert skjema for registrering av hendelser for Dynamics 365 for Customer Engagement.   |
|Webressurser  | [web-avoid-modals](http://go.microsoft.com/fwlink/?LinkID=398563&error=web-avoid-modals&client=PAChecker&source=featuredocs)  | Unngå å bruke modale dialogbokser.   |
|Webressurser  | [web-avoid-crm2011-service-odata](http://go.microsoft.com/fwlink/?LinkID=398563&error=web-avoid-crm2011-service-odata&client=PAChecker&source=featuredocs)   | Ikke fokuser på endepunktet for Microsoft Dynamics CRM 2011 OData 2.0.     |
|Webressurser  | [web-avoid-crm2011-service-soap](http://go.microsoft.com/fwlink/?LinkID=398563&error=web-avoid-crm2011-service-soap&client=PAChecker&source=featuredocs)  | Ikke fokuser på SOAP-tjenestene for Microsoft Dynamics CRM 2011.   |
|Webressurser  | [web-avoid-browser-specific-api](http://go.microsoft.com/fwlink/?LinkID=398563&error=web-avoid-browser-specific-api&client=PAChecker&source=featuredocs) | Ikke bruk eldre API-er eller nettleser-plugin-moduler for Internet Explorer.   |
|Webressurser  | [web-avoid-2011-api](http://go.microsoft.com/fwlink/?LinkID=398563&error=web-avoid-2011-api&client=PAChecker&source=featuredocs)  | Ikke bruk avskrevet Microsoft Dynamics CRM 2011-objektmodell.  |
|Webressurser  | [web-use-relative-uri](http://go.microsoft.com/fwlink/?LinkID=398563&error=web-use-relative-uri&client=PAChecker&source=featuredocs)   | Ikke bruk absolutte URL-adresser for endepunkt for Common Data Service.    |
|Webressurser  | [web-use-client-context](http://go.microsoft.com/fwlink/?LinkID=398563&error=web-use-client-context&client=PAChecker&source=featuredocs)  | Bruk klientkontekster.   |
|Webressurser  | [web-use-dialog-api-param](http://go.microsoft.com/fwlink/?LinkID=398563&error=web-use-dialog-api-param&client=PAChecker&source=featuredocs)   | Bruk API-parametere for dialogboks.   |
|Webressurser  | [web-use-org-setting](http://go.microsoft.com/fwlink/?LinkID=398563&error=web-use-org-setting&client=PAChecker&source=featuredocs)   | Bruk organisasjonsinnstillinger.   |
|Webressurser  | [web-use-grid-api](http://go.microsoft.com/fwlink/?LinkID=398563&error=web-use-grid-api&client=PAChecker&source=featuredocs)   | Bruk API-er for rutenett.    |
|Webressurser  | [web-avoid-isActivityType](http://go.microsoft.com/fwlink/?LinkID=398563&error=web-avoid-isActivityType&client=PAChecker&source=featuredocs)   | Erstatt Xrm.Utility.isActivityType-metoden med ny Xrm.Utility.getEntityMetadata, og ikke bruk i regler på båndet.    |
|Webressurser  | [meta-avoid-silverlight](http://go.microsoft.com/fwlink/?LinkID=398563&error=meta-avoid-silverlight&client=PAChecker&source=featuredocs)   | Bruk av webressursen Silverlight blir avskrevet.   |
| Webressurser  | [web-remove-debug-script](http://go.microsoft.com/fwlink/?LinkID=398563&error=web-remove-debug-script&client=PAChecker)  | Unngå å inkludere feilsøkingsskript i ikke-utviklingsmiljøer.  | 
| Webressurser  | [web-use-strict-mode](http://go.microsoft.com/fwlink/?LinkID=398563&error=web-use-strict-mode&client=PAChecker)  | Bruk Strict-modus når det er mulig.  | 
| Webressurser  | [web-use-strict-equality-operators](http://go.microsoft.com/fwlink/?LinkID=398563&error=web-use-strict-equality-operators&client=PAChecker)  | Bruk strenge likhetstegn.  | 
| Webressurser  | [web-avoid-eval](http://go.microsoft.com/fwlink/?LinkID=398563&error=web-avoid-eval&client=PAChecker)  | Ikke bruk "eval"-funksjonen eller funksjonsekvivalenter.  | 


### <a name="see-also"></a>Se også
[Gode fremgangsmåter og veiledning for Common Data Service](../../developer/common-data-service/best-practices/index.md)<br />
[Gode fremgangsmåter og veiledning for modelldrevne apper](../../developer/model-driven-apps/best-practices/index.md)<br />
[Vanlige problemer og løsninger for Løsningskontroll](common-issues-resolutions-solution-checker.md)<br />
