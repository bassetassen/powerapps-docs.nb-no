---
title: Hurtigstart for overføring av webklientprogrammet for Dynamics 365 for Customer Engagement-apper til Enhetlig grensesnitt | MicrosoftDocs
description: Lær hvordan du overfører et eldre webklientprogram til Enhetlig grensesnitt
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
ms.assetid: 14c4c18c-927c-4ea2-ba66-0531285a99a7
caps.latest.revision: 25
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="quick-start-for-transitioning-your-dynamics-365-for-customer-engagement-apps-web-client-application-to-unified-interface"></a>Hurtigstart for overføring av webklientprogrammet for Dynamics 365 for Customer Engagement-apper til Enhetlig grensesnitt

Rammeverket for det enhetlige grensesnittet bruker også webutformingsprinsipper som gir respons, for å formidle en optimal visnings- og samhandlingsopplevelse for alle skjermstørrelser, -enheter eller -retninger. Dette hurtigstartemnet forklarer hvordan du overfører webklientprogrammet for Dynamics 365 for Customer Engagement-apper til Enhetlig grensesnitt ved hjelp av et nytt ikke-produksjonsmiljø. Hvis du vil bruke et eksisterende ikke-produksjonsmiljø til å overføre webklientprogrammet, kan du se [Hurtigstart for bruk av et eksisterende miljø for å validere den eldre webklient-appen med Enhetlig grensesnitt](transition-web-app-existing.md). 


## <a name="prerequisites"></a>Forhåndskrav
- Et eldre webklientprogram for Dynamics 365 for Customer Engagement-apper. 
- Selv om det ikke er nødvendig, anbefaler vi et ikke-produksjonsmiljø for å teste programmet og kontrollere at det ikke påvirker gjeldende distribusjon eller utviklingssykluser. Mer informasjon: [Administrere sandkasseforekomster](/dynamics365/customer-engagement/admin/manage-sandbox-instances)

## <a name="prepare-the-environment"></a>Klargjøre miljøet
Først velger du et ikke-produksjonsmiljø og aktiverer modusen **Bruk bare det enhetlige grensesnittet**, som bruker Enhetlig grensesnitt for alle modelldrevne apper i miljøet. Dette inkluderer også eventuelle Dynamics 365 for Customer Engagement-programmoduler som opprinnelig ble konfigurert for den gamle webklienten.

1. Logg på [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc), velg **Miljø**, og velg deretter et sandkassemiljø. 

2. Velg **Innstillinger** > **Virkemåte**, og slå på **Bruk bare det enhetlige grensesnittet**.

   > [!div class="mx-imgBorder"] 
   > ![Bruk bare innstillingen for enhetlig grensesnitt](media/use-unified-interface-only-pac.png)

Du kan også angi dette i Dynamics 365 for Customer Engagement-apper. Gå til **Innstillinger** > **Administrasjon** > **Systeminnstillinger**, og i **Generelt**-kategorien setter du **Aktiver bare det enhetlige grensesnittet** til **Ja**.

> [!div class="mx-imgBorder"] 
> ![Bruk bare det nye enhetlige grensesnittet](media/use-unified-interface-only.png "Bruk bare det nye enhetlige grensesnittet")


> [!NOTE]
> Hvis du må bytte miljøet tilbake til den opprinnelige tilstanden, kan du veksle mellom Enhetlig grensesnitt-innstillingen for å gå tilbake til det opprinnelige grensesnittet. Mer informasjon: [Aktiver bare det enhetlige grensesnittet](/dynamics365/customer-engagement/admin/enable-unified-interface-only)

## <a name="run-and-validate-your-application-in-the-unified-interface"></a>Kjøre og validere programmet i Enhetlig grensesnitt
Kjør programmene som opprinnelig var webklientprogrammer. Vær oppmerksom på at når du har aktivert **Bruk bare det enhetlige grensesnittet**, bruker alle tilgjengelige apper i miljøet Enhetlig grensesnitt, selv om programmet opprinnelig ble konfigurert for webklienten.

Hvis du vil kjøre appen, logger du deg på [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc), velger **Apper** og velger deretter programmet du vil kjøre. Du kan også gå direkte til **Mine apper**-siden i Dynamics 365 for Customer Engagement-apper, for eksempel *https://contoso.crm.dynamics.com/apps/*.

### <a name="validate-your-app-processes-and-customizations"></a>Validere apper, prosesser og tilpassinger 
Vi anbefaler at du tester alle brukstilfeller. Du kan begynne med de mest kritiske brukstilfellene eller gruppere dem i logiske utformingsmønstre. Siden Enhetlig grensesnitt er basert på responsiv utforming anbefaler vi at du utfører tester med forskjellige enheter som har forskjellige skjermoppløsninger. Når du tester programmet, kan du kontrollere at tilpassingene er kompatible med Enhetlig grensesnitt, og om det finnes noen funksjoner som krever en ny utforming eller mangler funksjonalitet. Lag en plan for å se gjennom disse elementene, og legg inn spørsmål og tilbakemeldinger på våre fellesskapsfora. <!-- Link tbd -->

> [!IMPORTANT]
> Gjeldende versjon av Common Data Service- og Dynamics 365 for Customer Engagement-apper inneholder fremdeles mange avskrevne funksjoner. Du bør gå gjennom programmet for alle avskrevne funksjoner og erstatte det som er nødvendig, med nye funksjoner. Mer informasjon: [Viktige endringer (avskrivninger) som kommer i Dynamics 365 Customer Engagement](/dynamics365/get-started/whats-new/customer-engagement/important-changes-coming)

### <a name="dynamics-365-for-customer-engagement-apps"></a>Apper i Dynamics 365 for Customer Engagement
Hvis du bruker Dynamics 365 for Field Service-eller Dynamics 365 for Project Service Automation -apper og vil teste Enhetlig grensesnitt, må du konfigurere et nytt sandkassemiljø og lage en kopi av produksjonsmiljøet for å oppgradere til den nyeste Field Service versjon 8 og Project Service Automation versjon 3 før validering av disse programmene i Enhetlig grensesnitt. Slik gjør du det:

1. Opprett et nytt sandkassemiljø fra [Power Platform-administrasjonssenteret](https://admin.powerplatform.microsoft.com/environments) eller [Dynamics 365-administrasjonssenteret](https://port.crm.dynamics.com/). Mer informasjon: [Legge til en forekomst i abonnementet](/dynamics365/customer-engagement/admin/add-instance-subscription).

2. Kopier produksjonsmiljøet som har Dynamics 365 for Field Service- eller Dynamics 365 for Project Service Automation-apper, til det nye sandkassemiljøet. Dette gjør du ved å gå til Power Platform-administrasjonssenteret, åpne produksjonsmiljøet og deretter velge **Kopier**.

    > [!div class="mx-imgBorder"] 
    > ![Kopier miljø](media/ppac-copy-environment.png "Kopier miljø")

3. På **Kopier miljø**-siden velger du **Alt**, velger det nye sandkassemiljøet fra **Velg et miljø som skal overskrives**-listen og deretter velger du **Kopier**. 

    > [!div class="mx-imgBorder"] 
    > ![Overskriv miljø](media/ppac-copy-overwrite.png "Overskriv miljø")

4. Dialogboksen **Overskriv miljø** vises. Kontroller at du har valgt riktig miljø, og at du har valgt riktige alternativer, og velg deretter **Bekreft**. 

5. Når kopieringen er vellykket, vises det en bekreftelsesmelding. 

6. På menylinjen velger du **Administrer løsninger** for å åpne **Løsninger**-området. 

    > [!div class="mx-imgBorder"] 
    > ![Administrer løsninger](media/ppac-manage-solutions.png "Administrer løsninger")

    > [!IMPORTANT]
    > Hvis **Administrasjonsmodus** er aktivert, må du deaktivere det, slik at du kan vise **Løsninger**-området. Mer informasjon: [Administrasjonsmodus](/power-platform/admin/sandbox-environments#administration-mode).

7. Finn Field Service- eller Project Service Automation-løsningen, og åpne den. Alternativet for **Oppgradering** skal være tilgjengelig. Velg det for å oppgradere løsningen. 

    > [!div class="mx-imgBorder"] 
    > ![Oppgrader løsning](media/ppac-upgrade-solution.png "Oppgrader løsning")
    
> [!NOTE]
> De siste versjonene av Field Service og Project Service Automation på Enhetlig grensesnitt er tilgjengelige som standard for nylig opprettede forekomster. Hvis du vil oppgradere et eksisterende miljø med installerte tidligere versjoner, må du be om oppgraderingen ved å kontakte [Microsofts kundestøtte.](https://go.microsoft.com/fwlink/?LinkId=853505) 

Mer informasjon: [Nyeste versjoner av Dynamics 365 for Field Service](/dynamics365/customer-engagement/field-service/version-history#latest-versions) og [Startside for Dynamics 365 for Project Service Automation-oppgradering](/dynamics365/customer-engagement/project-service/upgrade-psa-home-page)

## <a name="next-steps"></a>Neste trinn
Basert på dine funn kan implementeringsteamet eller-partneren din beregne hvor mye innsats som kreves for å overføre programmet til Enhetlig grensesnitt, og også identifisere potensielle brukervennlighetsforbedringer. Med flere nye funksjoner og egenskaper som er tilgjengelige i det enhetlige grensesnittet, finnes det mulighet til å øke verdien for programbrukerne. 

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

