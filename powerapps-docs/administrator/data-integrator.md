---
title: Integrer data i Common Data Service for apper
description: Integrer data fra flere kilder i Common Data Service for apper
author: sabinn-msft
ms.service: powerapps
ms.topic: how-to
ms.component: cds
ms.date: 09/19/2018
ms.author: sabinn
search.audienceType:
- admin
search.app:
- D365CE
- PowerApps
- Powerplatform
ms.openlocfilehash: b8cebc6f9db8a1a7c1a060aad461f4f32fcee05b
ms.sourcegitcommit: 2bcf40aeaa35420dc43f5803f4e57ff0f6afb57b
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 09/19/2018
ms.locfileid: "46469747"
---
# <a name="integrate-data-into-common-data-service-for-apps"></a>Integrer data i Common Data Service for apper

<!--note from editor: the style guide says not to use "the" in front of Common Data Service for Apps, so I'm removing that.-->

Dataintegratoren (for administratorer) er en punkt-til-punkt-integreringstjeneste som brukes til å integrere data i Common Data Service for apper. Den støtter integrering av data fra flere kilder, blant annet Dynamics 365 for Finance and Operations, Dynamics 365 for Sales and SalesForce (forhåndsversjon) og SQL (forhåndsversjon), i Common Data Service for apper. Den støtter også integrering av data i Dynamics 365 for Finance and Operations og Dynamics 365 for Sales. Denne tjenesten har vært generelt tilgjengelig siden juli 2017.  

Vi begynte med førstepartsappene, blant annet Dynamics 365 for Finance and Operations og Dynamics 365 for Sales. Ved å bruke Power Query eller M-baserte koblinger støtter vi nå flere kilder, blant annet SalesForce (forhåndsversjon) og SQL (forhåndsversjon). I nærmeste fremtid kommer vi til å utvide støtten til mer enn 20 kilder. 

> [!div class="mx-imgBorder"]
> ![Datakilde til mål](media/data-integrator/DataIntegratorP2P-new.PNG "Datakilde til mål")

## <a name="how-can-you-use-the-data-integrator-for-your-business"></a>Hvordan kan du bruke dataintegratoren i bedriften?

Dataintegratoren (for administratorer) støtter også prosessbaserte integreringsscenarioer, for eksempel Kundeemne til kontanter, som gir direkte synkronisering mellom Dynamics 365 for Finance and Operations og Dynamics 365 for Sales. Kundeemne til kontanter-maler som er tilgjengelige med dataintegreringsfunksjonen, muliggjør flyt av data for kontoer, kontakter, produkter, salgstilbud, salgsordrer og salgsfakturaer mellom Finance and Operations og Sales. Når data flyter mellom Finance and Operations og Sales, kan du utføre salgs- og markedsføringsaktiviteter i Sales og håndtere ordrefullføring ved å bruke lagerhåndtering i Finance and Operations. 

> [!div class="mx-imgBorder"]
> ![Kundeemne til kontanter](media/data-integrator/ProspectToCash631.png "Kundeemne til kontanter")

Kundeemne til kontanter-integreringen gir selgere mulighet til å håndtere og overvåke salgsprosesser basert på Dynamics 365 for Sales, mens alle aspekter ved fullføring og fakturering skjer ved hjelp av den omfattende funksjonaliteten i Finance and Operations. Med Kundeemne til kontanter-integrasjonen i Microsoft Dynamics 365 kan du dra nytte av funksjonaliteten i begge systemene. 

Se videoen: [Kundeemne for kontanter-integrasjon](https://www.youtube.com/watch?v=AVV9x5x-XCg)

Du finner mer informasjon om Kundeemne til kontanter-integrasjonen i dokumentasjonen for [Kundeemne til kontanter-løsningen](https://docs.microsoft.com/en-us/dynamics365/unified-operations/supply-chain/sales-marketing/prospect-to-cash).

Vi støtter også [Field Service-integrasjon](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order) og [PSA-integrasjon (Project Service Automation)](https://docs.microsoft.com/dynamics365/unified-operations/financials/project-management/psa-integration?toc=/fin-and-ops/toc.json) til Dynamics 365 for Finance and Operations.

## <a name="data-integrator-platform"></a>Dataintegratorplattform

Dataintegratoren (for administratorer) består av dataintegreringsplattformen, standardmaler fra appteamene våre (blant annet Dynamics 365 for Finance and Operations og Dynamics 365 for Sales) samt egendefinerte maler som er opprettet av kunder og partnere. Vi har skapt en programuavhengig plattform som kan skaleres over ulike kilder. Hovedpoenget er at du oppretter tilkoblinger (til integrasjonsendepunkter), velger en av de tilpasningsbare malene med forhåndsdefinerte tilordninger (som du kan tilpasse ytterligere), og oppretter og kjører dataintegreringsprosjektet.  

Integreringsmaler fungerer som en blåkopi med forhåndsdefinerte enheter og felttilordninger som muliggjør flyt av data fra kilde til mål. De gir også muligheten til å transformere dataene før du importerer dem. Mange ganger kan skjemaet mellom kilde- og målappene være svært annerledes, og en mal med forhåndsdefinerte enheter og felttilordninger fungerer som et godt utgangspunkt for et integreringsprosjekt.  

> [!div class="mx-imgBorder"]
> ![Dataintegreringsplattform](media/data-integrator/DIPlatform.PNG "Dataintegreringsplattform")

## <a name="how-to-set-up-a-data-integration-project"></a>Slik konfigurerer du et dataintegreringsprosjekt

De tre hovedtrinnene er som følger:

1. Opprett en tilkobling (angi legitimasjon til datakilder).

2. Opprett et tilkoblingssett (identifiser miljøer for tilkoblinger som du opprettet i forrige trinn).

3. Opprett et dataintegreringsprosjekt ved hjelp av en mal (opprett eller bruk forhåndsdefinerte tilordninger for en eller flere enheter).

Når du har opprettet integreringsprosjektet, kan du velge å kjøre prosjektet manuelt og dessuten angi tidsplanbasert oppdatering for fremtiden. Resten av denne artikkelen dekker disse tre trinnene.

### <a name="how-to-create-a-connection"></a>Slik oppretter du en tilkobling

Før du kan opprette et dataintegreringsprosjekt, må du klargjøre en tilkobling for hver system som du har tenkt å arbeide med i Microsoft PowerApps-portalen. Tenk på disse tilkoblingene som integrasjonspunktene.

**Slik oppretter du en tilkobling**

1. Gå til [administrasjonssenteret for PowerApps](https://admin.powerapps.com).

2. Under Data velger du **Tilkoblinger** og deretter **Ny tilkobling**.

3. Du kan velge en tilkobling fra listen over tilkoblinger, eller du kan søke etter den.

    > [!div class="mx-imgBorder"] 
    > ![Opprett tilkobling](media/data-integrator/CreateConnection780.png "Opprett tilkobling")

4. Når du har valgt tilkoblingen, velger du **Opprett**. Du blir bedt om å oppgi påloggingsinformasjon.

5. Når du har oppgitt legitimasjonen din, vises tilkoblingen under tilkoblingene dine.

    > [!div class="mx-imgBorder"] 
    > ![Tilkoblingsliste](media/data-integrator/CreateConnection1780.png "Tilkoblingsliste")

### <a name="how-to-create-a-connection-set"></a>Slik oppretter du et tilkoblingssett

Tilkoblingssett er en samling av to tilkoblinger, miljøer for tilkoblingene, informasjon om organisasjonstilordninger samt integrasjonsnøkler som kan brukes i alle prosjektene. Du kan begynne å bruke et tilkoblingssett for utvikling og deretter bytte til et annet for produksjon. En viktig type informasjon som er lagret i et tilkoblingssett, er tilordninger for organisasjonsenheter, for eksempel tilordninger mellom den juridiske enheten for Finance and Operations (eller firmaet) og organisasjons- eller bedriftsenhetene for Dynamics 365 for Sales. Du kan lagre flere organisasjonstilordninger i et tilkoblingssett.

**Slik oppretter du et tilkoblingssett**

1. Gå til [administrasjonssenteret for PowerApps](https://admin.powerapps.com).

2. Velg fanen **Dataintegrering** i venstre navigasjonsrute.

3. Velg fanen **Tilkoblingssett** og deretter **Nytt tilkoblingssett**.

4. Angi et navn for tilkoblingssettet.
  
    > [!div class="mx-imgBorder"] 
    > ![Opprett tilkoblingssettet](media/data-integrator/CreateConnectionSet1780.png "Opprett tilkoblingssettet")
  
5. Velg tilkoblingene du opprettet tidligere, og velg ønsket miljø.

6. Gjenta trinnene ved å velge neste tilkobling (tenk på disse som kilde og mål i vilkårlig rekkefølge).

7. Angi tilordningen mellom organisasjonen og forretningsenheten (hvis du integrerer mellom Finance and Operations- og Sales-systemer).
  
    > [!NOTE]
    > Du kan angi flere tilordninger for hvert tilkoblingssett.
  
8. Når du har fylt ut alle feltene, velger du **Opprett**.

9. Det nye tilkoblingssettet vises i listen over tilkoblingssett.
    
    > [!div class="mx-imgBorder"] 
    > ![Liste over tilkoblingssett](media/data-integrator/CreateConnectionSet2780.png "Liste over tilkoblingssett")

Tilkoblingssettet er klart til bruk i ulike integreringsprosjekter.

### <a name="how-to-create-a-data-integration-project"></a>Slik oppretter du et dataintegreringsprosjekt

Prosjekter muliggjør flyt av data mellom systemer. Et prosjekt inneholder tilordninger for en eller flere enheter. Tilordninger angir hvilke felt som er tilordnet hverandre.

**Slik oppretter du et dataintegreringsprosjekt**

1. Gå til [administrasjonssenteret for PowerApps](https://admin.powerapps.com).

2. Velg fanen **Dataintegrering** i navigasjonsruten til venstre.

3. I **Prosjekter**-fanen velger du **Nytt prosjekt**  øverst til høyre.

    > [!div class="mx-imgBorder"] 
    > ![Opprett prosjektet](media/data-integrator/CreateNewProject780.png "Opprett prosjektet")

4. Angi et navn for integreringsprosjektet.

5. Velg en av de tilgjengelige malene (eller [opprett din egen mal](#how-to-customize-or-create-your-own-template)). I dette tilfellet flytter vi Produkter-enheten fra Finance and Operations til Sales.

    > [!div class="mx-imgBorder"] 
    > ![Velg mal for å opprette nytt prosjekt](media/data-integrator/CreateNewProjectSelectTemplate780.png "Velg mal for å opprette nytt prosjekt")

6. Velg **Neste**, og velg et tilkoblingssett du opprettet tidligere (eller [opprett et nytt](#how-to-create-a-connection-set)).

7. Kontroller at du har valgt rett sett ved å bekrefte navnet på tilkoblingen og miljøet.

    > [!div class="mx-imgBorder"] 
    > ![Opprett et nytt tilkoblingssett](media/data-integrator/CreateNewProjectSelectConnectionSet780.png "Opprett et nytt tilkoblingssett")

8. Velg **Neste**, og velg deretter tilordningene for juridisk enhet til forretningsenhet.

    > [!div class="mx-imgBorder"] 
    > ![Opprett ny tilordning for juridisk enhet](media/data-integrator/CreateNewProjectLegalEntityMapping780.png "Opprett ny tilordning for juridisk enhet")

9. Se gjennom og godta personvernerklæringen og samtykket i det neste skjermbildet.

10. Opprett prosjektet og kjør det.

    > [!div class="mx-imgBorder"] 
    > ![Kjør prosjekt](media/data-integrator/RunProject780.png "Kjør prosjekt")

    I dette skjermbildet finner du flere faner – **Planlegging** og **Kjøringslogg** – samt noen knapper – **Legg til oppgave**, **Oppdater enheter** og **Avansert spørring** – som blir beskrevet senere i denne artikkelen.

### <a name="execution-history"></a>Kjøringslogg

<!--note from editor: Do you think most people reading this will know what "upsert" means?-->

Kjøringslogg viser loggen over alle prosjektkjøringer med prosjektnavn, tidsstempel for når prosjektet ble kjørt, samt status for kjøringen sammen med antall upserter og/eller feil.

-   Eksempel på prosjektkjøringslogg.

    > [!div class="mx-imgBorder"] 
    > ![Prosjektkjøringslogg](media/data-integrator/ExecutionHistorySuccessFailures4780.png "Prosjektkjøringslogg")

-   Eksempel på vellykket kjøring. Status vises som fullført med \# upserter. (Upsert er en logikk som enten oppdaterer eksisterende poster eller setter inn en ny post.)

    > [!div class="mx-imgBorder"] 
    > ![Kjøring fullført](media/data-integrator/ExecutionHistorySuccess2780.png "Kjøring fullført")

-   Ved kjøringsfeil kan du drille ned for å se årsaken.

    Her er et eksempel på en kjøringsfeil med prosjektvalideringsfeil. I dette tilfellet skyldes prosjektvalideringsfeilen manglende kildefelt i enhetstilordningene.

    > [!div class="mx-imgBorder"] 
    > ![Kjøringsloggfeil](media/data-integrator/ExecutionHistoryFailures3780.png "Kjøringsloggfeil")

-   Hvis prosjektkjøringen har status «FEIL», prøves kjøringen på nytt ved neste planlagte kjøring.

-   Hvis prosjektkjøringen har status «ADVARSEL», må du løse problemene i kilden. Kjøringen blir utført på nytt ved neste planlagte kjøring.

    I begge tilfeller kan du også velge å kjøre på nytt manuelt.

### <a name="how-to-set-up-a-schedule-based-refresh"></a>Slik konfigurerer du en tidsplanbasert oppdatering

Vi støtter for øyeblikket to typer kjørings-og skriveoperasjoner:

-   Manuell skriving (kjør og oppdater prosjektet manuelt)

-   Tidsplanbasert skriving (automatisk oppdatering)

Når du har opprettet et integreringsprosjekt, kan du velge å kjøre det manuelt eller konfigurere tidsplanbaserte skrivinger, der du kan angi automatiske oppdateringer for prosjektene dine.

**Slik konfigurerer du tidsplanbasert skriving**

1. Gå til [administrasjonssenteret for PowerApps](https://admin.powerapps.com).

2. Du kan planlegge prosjekter på to forskjellige måter.<br>

    Velg prosjektet og deretter **Planlegging**-fanen, eller start planleggeren fra prosjektlistesiden ved å klikke på ellipsen ved siden av prosjektnavnet.

    > [!div class="mx-imgBorder"] 
    > ![Tidsplanbasert skriving](media/data-integrator/Schedulebasedwrites780.png "Tidsplanbasert skriving")

3. Velg **Gjenta hver**. Når du har fylt ut alle feltene, velger du **Lagre tidsplan**.

    > [!div class="mx-imgBorder"] 
    > ![Tidsplanbasert skriving](media/data-integrator/Schedulebasedwrites1780.png "Tidsplanbasert skriving")

Du kan angi en frekvens ned til hvert minutt, eller du kan angi at skrivingen skal gjentas et visst antall timer, dager uker eller måneder. Vær oppmerksom på at neste oppdatering ikke starter før kjøringen av forrige prosjektoppgave er fullført.

Vær også oppmerksom på at under Varslinger kan du velge å motta varslinger på e-post. Da får du melding om jobbkjøringer som ble fullført med advarsler, eller som mislyktes på grunn av feil. Du kan angi flere mottakere, inkludert grupper, atskilt med komma.

> [!div class="mx-imgBorder"] 
> ![E-postvarsel](media/data-integrator/EmailNotification780.png "E-postvarsel")

## <a name="customizing-projects-templates-and-mappings"></a>Tilpasse prosjekter, maler og tilordninger 

Du bruker en mal til å opprette et dataintegreringsprosjekt. Maler legger til rette for dataflyt, noe som igjen hjelper en bedriftsbruker eller administrator med å få fart på integreringen av data fra kilde til mål og reduserer arbeidsmengden og kostnadene. Forretningsbrukere eller administratorer kan begynne med en standardmal publisert av Microsoft eller en partner, og deretter tilpasse malen ytterligere før prosjektet opprettes. Du kan deretter lagre prosjektet som en mal og dele den med organisasjonen og/eller opprette et nytt prosjekt. 

En mal gir deg kilde, mål og retning for dataflyten. Husk på dette når du tilpasser maler og/eller oppretter egne.  

Du kan tilpasse prosjekter og maler på følgende måter:

-   Tilpass felttilordninger.

-   Tilpass en mal ved å legge til en enhet etter ønske.

### <a name="how-to-customize-field-mappings"></a>Slik tilpasser du felttilordninger

**Slik oppretter du et tilkoblingssett**

1. Gå til [administrasjonssenteret for PowerApps](https://admin.powerapps.com).

2. Velg prosjektet du vil tilpasse felttilordninger for, og velg deretter pilen mellom kilde- og målfeltene.

    > [!div class="mx-imgBorder"] 
    > ![Felttilordning](media/data-integrator/FieldMapping780.png "Felttilordning")

3. Da går du til tilordningsskjermbildet, der du kan legge til en ny tilordning ved å velge **Legg til tilordning** øverst til høyre. Alternativt kan du velge **Tilpass eksisterende tilordninger** fra rullegardinlisten.

    > [!div class="mx-imgBorder"] 
    > ![Tilpass felttilordninger](media/data-integrator/FieldMappingCustomize780.png "Tilpass felttilordninger")

4. Når du har tilpasset felttilordningene, velger du **Lagre**.

### <a name="how-to-customize-or-create-your-own-template"></a>Slik tilpasser eller oppretter du en mal 

**Slik oppretter du din egen mal**

1. Gå til [administrasjonssenteret for PowerApps](https://admin.powerapps.com).

2. Identifiser kilde, mål og flytretning for den nye malen.

3. Opprett et prosjekt ved å velge en eksisterende mal som samsvarer med ditt valg av kilde, mål og flytretning.

<!--note from editor: Didn't we create the project in step 3? Step 4 tells us to create the project.-->

4. Opprett prosjektet når du har valgt riktig tilkobling.

5. Før du lagrer og/eller kjører prosjektet, velger du **Legg til oppgave** øverst til høyre.

    > [!div class="mx-imgBorder"] 
    > ![Tilpass malen](media/data-integrator/CustomizeTemplate780.png "Tilpass malen")

    Dialogboksen **Legg til oppgave** åpnes.

6. Gi oppgaven et meningsfylt navn, og legg til ønskede kilde- og målenheter.

    > [!div class="mx-imgBorder"] 
    > ![Legg til oppgave i maltilpassing](media/data-integrator/CustomizeTemplateAddtask75.png "Legg til oppgave i maltilpassing")

7. Rullegardinlisten viser deg alle kilde og målenhetene dine.

    > [!div class="mx-imgBorder"] 
    > ![Legg til oppgave i maltilpassing](media/data-integrator/CustomizeTemplateAddtask175.png "Legg til oppgave i maltilpassing")

    I dette tilfellet ble det opprettet en ny oppgave for å synkronisere brukerenheten fra SalesForce til brukerenheten i Common Data Service for apper.

    > [!div class="mx-imgBorder"] 
    > ![Legg til oppgave i maltilpassing](media/data-integrator/CustomizeTemplateAddtask275.png "Legg til oppgave i maltilpassing")

8. Når du har opprettet oppgaven, finner du den i listen. Du kan slette den opprinnelige oppgaven.

    > [!div class="mx-imgBorder"] 
    > ![Legg til oppgave i maltilpassing](media/data-integrator/CustomizeTemplateAddtask3780.png "Legg til oppgave i maltilpassing")

9. Du har akkurat opprettet en ny mal, i dette tilfellet en som henter brukerenhetsdata fra SalesForce til Common Data Service. Velg **Lagre** for å lagre tilpasningen.

10. Følg trinnene for å tilpasse felttilordninger for denne nye malen. Du kan kjøre dette prosjektet og/eller lagre prosjektet som en mal fra **Prosjektliste**-siden.

    > [!div class="mx-imgBorder"] 
    > ![Lagre som mal i maltilpassing](media/data-integrator/CustomizeTemplateSaveAsTemplate780.png "Lagre som mal i maltilpassing")

11. Angi et navn og beskrivelse, og/eller del malen med andre i organisasjonen din.

    > [!div class="mx-imgBorder"] 
    > ![Lagre som mal i maltilpassing](media/data-integrator/CustomizeTemplateSaveAsTemplate175.png "Lagre som mal i maltilpassing")

## <a name="advanced-data-transformation-and-filtering"></a>Avansert datatransformasjon og filtrering 

Med støtte for Power Query kan vi nå tilby avansert filtrering og datatransformasjon av kildedata. Med Power Query kan brukerne forme data etter behov, takket være en brukervennlig, kodefri brukeropplevelse. Du kan aktivere dette per prosjekt. 

### <a name="how-to-enable-advanced-query-and-filtering"></a>Slik aktiverer du avansert spørring og filtrering

**Slik konfigurerer du avansert filtrering og datatransformasjon**

1. Gå til [administrasjonssenteret for PowerApps](https://admin.powerapps.com).

2. Velg prosjektet der du vil aktivere avansert spørring, og velg deretter **Avansert spørring**.

    > [!div class="mx-imgBorder"] 
    > ![Velg avansert spørring](media/data-integrator/EnablePQ1780.png "Velg avansert spørring")

3. Du får en advarsel om at aktivering av avansert spørring er en enveisoperasjon som ikke kan angres. Velg **OK** for å fortsette, og velg deretter pilen for kilde- og måltilordning.

    > [!div class="mx-imgBorder"] 
    > ![Advarsel](media/data-integrator/EnablePQ275.png "Advarsel")

4. Nå vises den vanlige enhetstilordningssiden med en kobling til start av Avansert spørring og filtrering.

    > [!div class="mx-imgBorder"] 
    > ![Avansert spørring og filtrering](media/data-integrator/EnablePQ3780.png "Avansert spørring og filtrering")

5. Velg **koblingen** for å starte brukergrensesnittet for Avansert spørring og filtrering, der du kan se kildefeltdata i kolonner av Microsoft Excel-typen.

    > [!div class="mx-imgBorder"] 
    > ![Avansert spørring og filtrering](media/data-integrator/EnablePQ4780.png "Avansert spørring og filtrering")

6. I den øverste menyen finner du flere alternativer for transformering av data, blant annet **Legg til betinget kolonne**, **Dupliser kolonne** og **Trekk ut**.

    > [!div class="mx-imgBorder"] 
    > ![Legg til kolonne](media/data-integrator/EnablePQAddColumn75.png "Legg til kolonne")

7. Du kan også høyreklikke på en kolonne for å få flere alternativer, for eksempel **Fjern kolonner**, **Fjern duplikater** og **Del kolonne**.

    > [!div class="mx-imgBorder"] 
    > ![Høyreklikk på kolonnen](media/data-integrator/EnablePQAddColumn180.png "Høyreklikk på kolonnen")

8. Du kan også filtrere ved å klikke på hver kolonne og bruke filtre av Excel-typen.

    > [!div class="mx-imgBorder"] 
    > ![Aktiver filtrering](media/data-integrator/EnablePQFiltering80.png "Aktiver filtrering")

<!--note from editor: I don't see an "otherwise" in the screenshot. I see "else".-->

9. Standard verditransformeringer kan oppnås ved å bruke den betingede kolonnen. Dette gjør du i rullegardinlisten **Legg til kolonne**. Velg **Legg til betinget kolonne** og skriv inn navnet på den nye kolonnen. Fyll ut både **Then** og **Otherwise** med det som skal være standardverdien. Bruk vilkårlig felt og verdi for **If** og **equal to**.

    > [!div class="mx-imgBorder"] 
    > ![Legg til betinget kolonne](media/data-integrator/EnablePQDefaultValueTransforms2780.png "Legg til betinget kolonne")

10. Legg merke til **each**-setningsdelen i *fx*-redigeringsprogrammet øverst.

    > [!div class="mx-imgBorder"] 
    > ![fx-redigeringsprogram](media/data-integrator/EnablePQDefaultValueTransforms2780.png "fx-redigeringsprogram")

11. Ordne **each**-setningsdelen i *fx*-redigeringsprogrammet, og velg **OK**.

    > [!div class="mx-imgBorder"] 
    > ![Ordne each-setningsdelen](media/data-integrator/EnablePQDefaultValueTransforms5780.png "Ordne each-setningsdelen")

<!--note from editor: The sentence that starts with "Additionally" is confusing - not sure where the "same steps" fit in.-->

12. Hver gang du gjør en endring, tar du i bruk et trinn. Du kan se de brukte trinnene i ruten til høyre (rull ned til bunnen for å se det siste trinnet). Du kan angre et trinn hvis du må redigere noe. I tillegg kan du gå til Avansert redigering ved å høyreklikke på **QrySourceData** øverst i ruten til venstre for å vise M-språket som kjøres i bakgrunnen med de samme trinnene.

    > [!div class="mx-imgBorder"] 
    > ![Avansert redigering](media/data-integrator/EnablePQDefaultValueTransforms4780.png "Avansert redigering")

13. Velg **OK** for å lukke grensesnittet for avansert spørring og filtrering. På oppgavesiden for tilordning velger du deretter den nylig opprettede kolonnen som kilde for å opprette tilordningen henhold til dette.

    > [!div class="mx-imgBorder"] 
    > ![Velg ny kolonne](media/data-integrator/EnablePQDefaultValueTransforms6780.png "Velg ny kolonne")

Du finner mer informasjon om Power Query i [Power Query-dokumentasjonen](https://docs.microsoft.com/power-query/).
