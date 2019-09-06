---
title: Hurtigstart for bruk av et eksisterende miljø til å validere den eldre webklient-appen med Enhetlig grensesnitt | MicrosoftDocs
description: Lær hvordan du planlegger og utfører overgang fra eldre webklient til Enhetlig grensesnitt
ms.custom: ''
ms.date: 07/24/2019
ms.reviewer: ''
ms.service: powerapps
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
author: Mattp123
ms.assetid: null
caps.latest.revision: 25
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---


<!--editor comment: I notice two mentions of Dynamics 365 Home page and both are followed by the URL but the text isn't linked. Just want to point that out in case it wasn't intentional. -->


# <a name="quick-start-for-using-an-existing-environment-to-validate-your-legacy-web-client-app-with-the-unified-interface"></a>Hurtigstart for bruk av et eksisterende miljø for å validere den eldre webklient-appen med Enhetlig grensesnitt

Hurtigstartemnet viser deg hvordan du bruker et eksisterende miljø til å opprette et Enhetlig grensesnitt-program basert på den gjeldende konfigurasjonen eller standardløsningen. Dette gjør det mulig for deg å utforske og teste Enhetlig grensesnitt mens du kjører eksisterende eldre webklientprogrammer parallelt. En bruker kan deretter bytte mellom miljøer for en side-ved-side-visning. For lignende instruksjoner som viser hvordan du oppretter et nytt sandkassemiljø for å isolere testingen og vise bare Enhetlig grensesnitt-opplevelsen, kan du se [Hurtigstart for overføring av eldre webklientprogrammer av Dynamics 365 for Customer Engagement-apper til Enhetlig grensesnitt](transition-web-app.md).

> [!IMPORTANT]
>  For miljøer med Dynamics 365 for Field Service- eller Dynamics 365 for Project Service Automation-apper kan du se [Dynamics 365 for Customer Engagement-apper](transition-web-app.md#dynamics-365-for-customer-engagement-apps).

## <a name="prerequisites"></a>Forhåndskrav 
- Et eksisterende eldre webklientprogram for Dynamics 365 for Sales eller Service. 
- Selv om det ikke er nødvendig, anbefaler vi at du bruker et ikke-produksjonsmiljø til å teste programmet. Mer informasjon: [Administrere sandkasseforekomster](/dynamics365/customer-engagement/admin/manage-sandbox-instances) 

## <a name="overview"></a>Oversikt 
Dette emnet er for eksisterende kunder som for øyeblikket bruker gamle webklientprogrammer, som har behov for å planlegge og utføre overføringen til Enhetlig grensesnitt. Hvis du vil sette opp et parallelt miljø, oppretter du et nytt program basert på standardløsningen slik det står i dag. Dette kan gjøres i det gjeldende utviklingssandkassemiljøet uten at det påvirker det eksisterende arbeidet.

Når du har fullført trinnene i denne artikkelen, kan brukere med riktig rolle se den nye appen din i applisten i både Dynamics 365 for Customer Engagement-rullegardinapplisten eller på Dynamics 365-startsiden (http://home.dynamics.com).

![Appliste](media/app-list.png)

Når du har fullført oppgavene som er beskrevet i dette emnet, i utviklingsmiljøet ved hjelp av en løsning, kan du importere løsningen til testmiljøet, noe som gjør det mulig for en bredere gruppe forretningsbrukere å teste og sammenligne appen i en kjent miljø. 

Følg prosessene for behandling av programlevetid (ALM) og utviklingsoperasjonsprosesser. Vi anbefaler at du utfører alle trinnene som er beskrevet i en løsningskontekst. Når du tester og validerer appen i utviklingsmiljøet, kan du ytterligere teste appen ved å starte den som et pilotprogram for flere brukere, for eksempel i et produksjonsmiljø. Ved å ha den modelldrevne appen og områdekartet i en løsning kan appen eksporteres fra miljøet der du opprettet den nye appen, etterfulgt av de eksisterende prosessene videre i miljøforløpet. 

## <a name="process-for-validating-your-legacy-web-client-app-in-an-existing-environment"></a>Prosess for validering av eldre webklientapp i et eksisterende miljø
 
Prosessen med å validere den eldre webklientappen i et eksisterende miljø omfatter tre trinn:  

1.  Opprette en ny løsning som er basert på standardløsningen
2.  Opprette en ny modelldrevet app 
3.  Konfigurere appegenskaper  

Hvis du nylig har satt **Bruk bare det enhetlige grensesnittet** til **På** i utviklingsmiljøet ved å følge emnet [Hurtigstart for overføring av eldre webklientprogrammer av Dynamics 365 for Customer Engagement-apper til Enhetlig grensesnitt](transition-web-app.md), må du sette innstillingen tilbake til **Av** slik at du kan kjøre de eksisterende eldre webklientappene.

### <a name="create-a-new-solution-thats-based-on-the-default-solution"></a>Opprette en ny løsning som er basert på standardløsningen
1. Logg på [PowerApps-utviklerportal](https://make.powerapps.com).   
2. Velg ønsket miljø i listen over miljøer.  
3. I navigasjonsruten til venstre velger du **Løsninger**. 
4. Velg **Ny løsning** på menylinjen. 
5. Angi følgende egenskaper i ruten **Ny løsning**: 
   - **Name**. Skriv inn et navn for løsningen. For eksempel *App for enhetlig grensesnitt*. 
   - **Utgiver**. Velg utgiveren som organisasjonen bruker. Pass på at du følger styringsreglene for tilpassing for de eksisterende tilpassingene. Dette sikrer at skjemanavnene for den modelldrevne appen og områdekartet er konsekvent med eksisterende standarder. 
   - **Versjon**. Dette må angis i henhold til eksisterende standarder og styring for løsninger. 
6. Velg **Opprett**.  
7. Den nye løsningen opprettes i listen over løsninger. Velg den for å åpne løsningen og gå til neste del. 

### <a name="create-a-new-model-driven-app-in-the-new-solution"></a>Opprette en ny modelldrevet app i den nye løsningen
I dette trinnet skal du opprette en ny app som benytter dine eksisterende tilpassinger, slik at du kan oppleve dem i Enhetlig grensesnitt. Du oppretter appen i beholderen for den nye løsningen, som du opprettet i den forrige delen.  

1. Velg **Ny**på menylinjen, pek på **App**, og velg deretter **Modelldrevet app**.
2. På siden **Opprett en ny app** skriver du inn følgende egenskaper: 
   - **Name**. Angi et navn for programmet slik det passer. For eksempel *Ditt programnavn* + *Ny* eller *Enhetlig grensesnitt-test*. 
   - **Unikt navn**. Dette starter med ditt løsningsprefiks og den forenklede versjonen av appnavnet du angav. Du kan gjøre endringer eller la den være slik den vises.  
   - **Beskrivelse**. Legg til en beskrivelse for appen, for eksempel *For testformål for det nye enhetlige grensesnittet for løsningen vår*.  
3. Velg **Bruk eksisterende løsning til å opprette appen**, og velg deretter **Neste**. 
4. I **Velg løsning**-listen velger du **Standardløsning**, i listen **Velg områdekart** velger du **Områdekart**, og deretter velger du **Fullført**.  

   > [!div class="mx-imgBorder"] 
   > ![Velge en eksisterende løsning](media/select-existing-solution.png "Velge en eksisterende løsning")

5. Skjemautforming åpnes, og alle appkomponentene i standardløsningen vises. Velg **Publiser**.  
6. Når publiseringsprosessen er fullført, velger du **Spill av**.  

Et nytt vindu åpnes i leseren med den nye modelldrevne appen som inneholder alle enheter, områdekart og områdekarttilpassinger som var i Dynamics 365 for Customer Engagement-standardprogrammet.  

> [!div class="mx-imgBorder"] 
> ![Ny Enhetlig grensesnitt-app](media/new-unified-interface-app.png "Ny Enhetlig grensesnitt-app")

Legg merke til at når du går tilbake til nettleserkategorien med PowerApps-utviklerportalen med **Løsninger**-området, er både den nye modelldrevne appen og en områdekartklientutvidelse med lignende navn en del av løsningen du opprettet.  

> [!div class="mx-imgBorder"] 
> ![Løsningsressurser](media/solution-assets.png "Løsningsressurser")

I dette trinnet oppretter du en ny modelldrevet app i en løsning, som du kan importere til test- eller evalueringsmiljøene. Du kan komme i gang med å oppleve den nye appen nå, men før du gjør dette, må du konfigurere et par innstillinger for den nye appen i neste trinn. Dette vil gjøre det mulig å dele med andre brukere.

### <a name="configure-app-properties"></a>Konfigurere appegenskaper
Oppgavene som kreves for å konfigurere de modelldrevne appegenskapene, omfatter: 

- Tilordne brukerroller til den nye appen, slik at ikke-administratorer får tilgang til å bruke appen.  
- Tilpasse en egendefinert URL-adresse, slik at en snarvei til den nye appen enkelt kan deles, bokmerkes eller huskes av brukere. 


1. Naviger til *miljø-URL*/**apper**. URL-adressen vil se omtrent slik ut: https://*DittMiljø*.crm.dynamics.com/apps. Når du gjør det, åpnes en liste over alle appene i miljøet. 
2. Finn den nye modelldrevne appen du opprettet.  
3. Velg en appflis, velg ellipsen, og velg deretter **Behandle roller**.   

   > [!div class="mx-imgBorder"] 
   > ![Behandle roller](media/select-app-ellipsis.png "Behandle roller")

4. Området for tilgjengelige roller vises i ruten til høyre. Velg rollene etter behov for å gi ikke-administratorbrukere tilgang til appen. 

    > [!IMPORTANT]
    > Kontroller at alle brukere har tilgang til minst én sikkerhetsrolle som inneholder **Lese**-tilgang til rettigheten **Modelldrevet app**. Du kan finne denne rettigheten i kategorien Tilpassing i sikkerhetsrollen. Brukere uten denne rettigheten mottar en feil ved åpning av en modelldrevet app.  Legg merke til at sikkerhetsrollene Systemadministrator og Systemtilpasser allerede har denne rettigheten aktivert. 
 
   > [!div class="mx-imgBorder"] 
   > ![Modelldrevet app-rettighet](media/model-driven-app-privilege.png "Modelldrevet app-rettighet")

5. I ruten **Behandle roller** kan du eventuelt utvide **Suffiks for URL-adresse for appen** for å tilpasse den egendefinerte URL-adressen for den modelldrevne appen. Legg merke til at du kan spesifisere de fleste ting. Angi for eksempel *ny*, slik at forhåndsvisningen viser URL-adressen *https://YourEnvironment.crm.dynamics.com/apps/new*.   

   > [!div class="mx-imgBorder"] 
   > ![Suffiks for URL-adresse for appen](media/app-url-suffix.png "Suffiks for URL-adresse for appen")

   Dette blir den tilpassede URL-adressen som brukes og deles, slik at brukere kan starte opplevelsen av det enhetlige grensesnittet direkte. Brukere kan sette bokmerke på koblingen hvis de vil. 

6. Velg **Lagre**. 

Nå kan brukere med riktig rolle se den nye appen din i applisten i både Dynamics 365 for Customer Engagement-rullegardinapplisten eller på Dynamics 365-startsiden (http://home.dynamics.com). 
  
   ![Appliste](media/app-list.png "Appliste")

Siden **Bruk bare det enhetlige grensesnittet** er satt til **Av**, vil brukere, når de navigerer til rot-URLen til miljøet, fremdeles lande på standard **Dynamics 365 – tilpasset**-program som før. Dette forventes hvis du vil fortsette å støtte eksisterende eldre webklientapper, samtidig som du tester og arbeider med Enhetlig grensesnitt-apper.  

## <a name="compare-your-new-app-to-the-default-dynamics-365-app"></a>Sammenligne den nye appen med standard Dynamics 365-appen  
Nå er du klar til å starte appen. Du kan sammenligne den nye Enhetlig grensesnitt-appen med Dynamics 365 – tilpasset-appen ved å bruke de samme dataene, brukerrollene, forretningsreglene, arbeidsflytene, plugin-modulene og så videre, fordi de er i samme miljø. Dette gjør det mulig for deg å lære organisasjonen din om at alle de grunnleggende kjernefunksjonene fremdeles er der, og samtidig kan du begynne med å utforske de nye Enhetlig grensesnitt-forbedringene.  

> [!TIP]
> Hvis du vil vise apper side ved side på én skjerm, kan du trykke tastene for Windows og pil venstre (eller pil høyre) samtidig for å dele opp webleservinduene på samme skjerm. 

> [!NOTE]
> Hvis du fortsetter å utføre tilpassinger i standard områdekart, for eksempel endringer i navigasjonen eller dypere båndtilpassinger for knapper og handlinger, må du gjenta prosessen ved å opprette en annen modelldrevet app eller utføre de samme tilpassingene i det nye områdekartet som er relatert til den modelldrevne appen.  

## <a name="validate-your-new-app"></a>Validere den nye appen  
Når programmet viser Enhetlig grensesnitt, kan du starte validering av appen, prosessene og tilpassingene for å identifisere hvordan overføringen vil se ut. Vi anbefaler at du tester alle brukstilfeller, men du kan begynne med de mest kritiske eller gruppere i logiske utformingsmønstre. Siden Enhetlig grensesnitt er basert på responsiv utforming anbefaler vi at du alltid utfører tester med forskjellige enheter som har forskjellige skjermoppløsninger. Når du tester programmet, kan du kontrollere at tilpassingene er kompatible med Enhetlig grensesnitt, og om det finnes noen funksjoner som krever en ny utforming eller mangler funksjonalitet.  

> [!IMPORTANT]
> Gjeldende versjon av Common Data Service- og Dynamics 365 for Customer Engagement-apper inneholder fremdeles mange avskrevne funksjoner. Du bør gå gjennom programmet for alle avskrevne funksjoner og erstatte det som er nødvendig, med nye funksjoner. Mer informasjon: [Viktige endringer (avskrivninger) som kommer i Dynamics 365 Customer Engagement](/dynamics365/get-started/whats-new/customer-engagement/important-changes-coming)

> [!TIP]
> Verktøyet PowerApps-kontroller hjelper deg med kvalitetskontroll av løsningens komponenter.  Mer informasjon: [Bruk løsningskontroll til å validere de modelldrevne appene i PowerApps](../common-data-service/use-powerapps-checker.md)

## <a name="next-steps"></a>Neste trinn
Basert på dine funn kan implementeringsteamet eller-partneren din beregne hvor mye innsats som kreves for å overføre programmet til Enhetlig grensesnitt, og også identifisere potensielle brukervennlighetsforbedringer. Med flere nye funksjoner og egenskaper som er tilgjengelige i Enhetlig grensesnitt, finnes det mulighet til å øke verdien for programbrukerne. 

Overføring til Enhetlig grensesnitt er en utmerket mulighet til å lage et moderne brukergrensesnitt og gå til de eksisterende prosessene for å kontrollere at de fremdeles er gyldige, eller om de trenger forbedring. Dette er også et godt tidspunkt å vurdere om programmet gjenspeiler forretningskravene dine, og om det eksisterende programmet kan spres over flere apper for ulike grupper og roller.
Mer informasjon: [Utforme modelldrevne apper ved hjelp av apputforming](design-custom-business-apps-using-app-designer.md) 

### <a name="see-also"></a>Se også
<!-- Unified Interface transition community (link tbd) <br />  -->
[Strategiplan for enhetlig grensesnitt](unified-interface-playbook.md) <br />
[Forestående brukeropplevelses- og Enhetlig grensesnitt-overgang](approaching-unified-interface.md) <br />
[Om Enhetlig grensesnitt](/dynamics365/customer-engagement/admin/about-unified-interface) <br />
[Hva er modelldrevne apper i PowerApps?](model-driven-app-overview.md) <br />
[Oppdatere apper til Enhetlig grensesnitt](/dynamics365/customer-engagement/admin/update-apps-to-unified-interface) <br />
[Konfigurere instrumentbord for interaktiv opplevelse for modelldrevet app](configure-interactive-experience-dashboards.md) <br />
[Bruke egendefinerte kontroller for datavisualiseringer i modelldrevne apper](use-custom-controls-data-visualizations.md) <br />
[Oversikt over PowerApps component framework](/powerapps/developer/component-framework/overview) <br />
[Enhetlig grensesnitt for alle](/power-platform-release-plan/2019wave2/microsoft-powerapps/unified-interface-app-everybody)
