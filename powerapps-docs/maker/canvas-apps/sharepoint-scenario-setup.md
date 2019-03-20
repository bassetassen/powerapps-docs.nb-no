---
title: Å konfigurere lister for SharePoint Online-integrasjon med PowerApps, Microsoft Flow og Power BI | Microsoft Docs
description: I denne oppgaven vil vi konfigurere SharePoint-lister, som skal brukes som en datakilde for apper, flyter, rapporter og instrumentbord.
author: NickWaggoner
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 12/19/2017
ms.author: niwaggon
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 7be4a0574c1a81684188eaede4b6e80b02e7b7cc
ms.sourcegitcommit: 90245baddce9d92c3ce85b0537c1ac1cf26bf55a
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 01/26/2019
ms.locfileid: "57799184"
---
# <a name="set-up-lists-for-sharepoint-online-integration-with-powerapps-microsoft-flow-and-power-bi"></a>Å konfigurere lister for SharePoint Online-integrasjon med PowerApps, Microsoft Flow og Power BI
> [!NOTE]
> Denne artikkelen er en del av en opplæringsserie om hvordan du bruker PowerApps, Microsoft Flow og Power BI, med SharePoint Online. Sørg for å lese [innføringen for serien](sharepoint-scenario-intro.md) for å få forståelse av det store bildet, i tillegg til relaterte nedlastinger.

SharePoint har massevis av funksjoner for deling og samarbeid, men vi fokuserer på én funksjon for dette scenarioet: [SharePoint-lister](https://support.office.com/article/Introduction-to-lists-0A1C3ACE-DEF0-44AF-B225-CFA8D92C52D7). En liste er bare en samling av data som du kan dele med gruppemedlemmer og andre områdebrukere. Vil vi gå gjennom lister som brukes i dette scenarioet, og deretter kan du opprette dem i ditt eget SharePoint Online-område.

## <a name="step-1-understand-the-lists"></a>Trinn 1: Forstå listene
Den første listen er **Prosjektforespørsler**, der en prosjektanmoder legger til en forespørsel. Prosjektgodkjenneren vurderer forespørselen og godkjenner, eller avviser den.

| **Listekolonne** | **Datatype** | **Notater** |
| --- | --- | --- |
| Tittel |Enkelt linje med tekst |Standardkolonnen, brukt til prosjektnavn |
| Beskrivelse |Enkeltlinje med tekst | |
| ProjectType |Enkelt linje med tekst |Verdier: ny maskinvare, oppgradert maskinvare, ny programvare, oppgradert programvare |
| RequestDate |Date | |
| Anmoder |Enkelt linje med tekst | |
| EstimatedDays |Tall |Aktiverer sammenligning av anmoderens estimat, med prosjektlederens estimatet til faktisk |
| Godkjent |Enkelt linje med tekst |Verdier: venter, ja, ingen |

> [!NOTE]
> Vi bruker også **ID**-kolonnen, som er generert av SharePoint og skjult som standard. Vi bruker grunnleggende datatyper for enkelhets skyld, men en ekte app kan bruke mer komplekse typer, som for eksempel **Person eller gruppe** for **Anmoder**-kolonnen. Hvis du vil ha informasjon om datatyper som støttes av PowerApps, kan du se [Koble til fra Microsoft PowerApps til SharePoint](connections/connection-sharepoint-online.md#known-issues).

Den andre listen er **Prosjektdetaljer**, som sporer detaljer for alle godkjente prosjekter, slik som hvilket prosjekt lederen er tilordnet.

| **Listekolonne** | **Datatype** | **Notater** |
| --- | --- | --- |
| Tittel |Enkelt linje med tekst |Standardkolonnen, brukt til prosjektnavn |
| RequestID |Tall |Samsvarer med verdien i **ID**-kolonnen i **Prosjektforespørsler**-listen |
| ApprovedDate |Date | |
| Status |Enkeltlinje med tekst |Verdier: ikke startet, pågår, fullført |
| ProjectedStartDate |Date |Når prosjektlederen estimerer at prosjektet skal starte |
| ProjectedEndDate |Date |Når prosjektlederen estimerer at prosjektet skal avsluttes |
| ProjectedDays |Tall |Arbeidsdager – vil vanligvis bli beregnet, men er ikke det i dette scenarioet |
| ActualDays |Tall |For fullførte prosjekter |
| PMAssigned |Enkelt linje med tekst |Prosjektleder |

## <a name="step-2-create-and-review-the-lists"></a>Trinn 2: Opprette og se gjennom lister
Hvis du vil fortsette med scenarioet, må du opprette de to SharePoint-listene og fylle dem med eksempeldata. Vi viser deg hvordan du gjør dette ved å opprette listen og lime inn eksempeldata i den. Kontroller at du har Excel-filer fra [Nedlastingspakken](https://aka.ms/o4ia0f).

> [!NOTE]
> Bruk Internet Explorer for dette trinnet.

### <a name="create-the-lists"></a>Å opprette listene

1. Klikk eller trykk på **Ny** og deretter **Liste** på SharePoint-området i Internet Explorer.
   
    ![Å opprette en ny SharePoint-liste](./media/sharepoint-scenario-setup/01-01-01-new-list.png)

2. Skriv inn navnet «Prosjektforespørsler», og klikk eller trykk deretter på **Opprett**.
   
    ![Å angi navn for ny liste](./media/sharepoint-scenario-setup/01-01-02-create-list.png)
   
    Listen for **Prosjektforespørselen** er opprettet, med **Tittel**-feltet som standard.
   
    ![Liste for prosjektforespørsler](./media/sharepoint-scenario-setup/01-01-03-initial-list.png)

### <a name="add-columns-to-the-list"></a>Å legge til kolonner i listen

1. Klikk eller trykk på ![Nytt elementikon](./media/sharepoint-scenario-setup/icon-new.png), og deretter **Enkelt linje med tekst**.
   
    ![Å legge til en enkelt linje med tekst-felt](./media/sharepoint-scenario-setup/01-01-04-add-column.png)

2. Skriv inn navnet «Beskrivelse», og klikk eller trykk deretter på **Lagre**.
   
3. Gjenta trinn **1** og **2** for de andre kolonnene i listen:
   
   1. **Enkelt linje med tekst** > "ProjectType"
   2. **Dato** > "RequestDate"
   3. **Enkelt linje med tekst** > "Requestor"
   4. **Antall** > "EstimatedDays"
   5. **Enkelt linje med tekst** > "Approved"

### <a name="copy-data-into-the-list"></a>Å kopiere data inn i listen
1. Klikk eller trykk på **Hurtigrediger**.
   
    ![Hurtigredigering for liste](./media/sharepoint-scenario-setup/01-01-06-quick-edit.png)
2. Merk cellene i rutenettet.
   
    ![Liste med alle kolonner](./media/sharepoint-scenario-setup/01-01-07-empty-grid.png)
3. Åpne project-requests.xlsx-arbeidsboken, og velg alle dataene (ikke overskriftene).
   
    ![Excel-tabell for prosjektforespørsler](./media/sharepoint-scenario-setup/01-01-08-excel-table.png)
4. Kopiere dataene og lim det inn i rutenettet i SharePoint, og klikk eller trykk deretter på **Fullført**.
   
    ![Fullført liste med data](./media/sharepoint-scenario-setup/01-01-09-full-grid.png)
5. Gjenta listeopprettingen og kopier prosessen for listen for «prosjektdetaljer», ved hjelp av project-details.xlsx-arbeidsboken. Referer til tabellen for Prosjektdetaljer i [trinn 1: Forstå listene](#step-1-understand-the-lists) for kolonnenavnene og datatypene.

## <a name="step-3-update-connections-to-samples---optional"></a>Trinn 3: Oppdatere tilkoblinger til eksempler – valgfritt
Som nevnt i innføringen til denne opplæringsserien, inkluderte vi to eksempelapper og en rapport i [Nedlastingspakken](https://aka.ms/o4ia0f). Du kan fullføre dette scenarioet uten å bruke disse eksemplene, men hvis du vil bruke eksemplene, må du oppdatere tilkoblingene til SharePoint-listene. Du oppdatere dem slik at de bruker *dine* lister som en datakilde, i stedet for våre.

### <a name="update-connections-for-the-sample-apps"></a>Å oppdatere tilkoblinger for eksempelappene

1. Klikk eller trykk på **Åpne** i den venstre ruten i [PowerApps Studio](https://create.powerapps.com/studio/). 

2. Klikk eller trykk på **Bla gjennom**, og åpne deretter **project-management-app.msapp**-filen du lastet ned.

3. Klikk eller trykk på **Tillat**, slik at PowerApps kan bruke SharePoint.

4. Klikk eller trykk på **Datakilder** på **Vis**-fanen på båndet.

    ![PowerApps-datakilder](./media/sharepoint-scenario-setup/01-03-01-data-sources.png)
5. Klikk eller trykk på ellipsen (**. . .**) ved siden av **Prosjektdetaljer** i **Data**panelet, og klikk eller trykk deretter på **Fjern**.
   
    ![Å fjerne datakilde for prosjektdetaljer](./media/sharepoint-scenario-setup/01-03-02-remove.png)
6. Klikk eller trykk på **Legg til datakilde**.
   
    ![Å legge til en datakilde](./media/sharepoint-scenario-setup/01-03-03-add.png)

7. Vi viser deg to måter å koble til listen på, avhengig av om PowerApps allerede opprettet en SharePoint-tilkobling for deg: 

    * Hvis du allerede ser en SharePoint-tilkobling, klikker eller trykker du på denne tilkoblingen.

        ![Eksisterende tilkobling](./media/sharepoint-scenario-setup/01-03-03aa-existing-connection.png)

    * Hvis du ikke ser en SharePoint-tilkobling, klikker eller trykker du på **Ny tilkobling**.

        ![Ny tilkobling](./media/sharepoint-scenario-setup/01-03-03a-new-connection.png)

        Klikk eller trykk på **SharePoint**, og klikk eller trykk på **Opprett**.
   
        ![SharePoint-tilkobling](./media/sharepoint-scenario-setup/01-03-03b-sharepoint.png)

8. Angi nettadressen for SharePoint Online-området som inneholder listen du har opprettet, og klikk eller trykk deretter på **Gå**.
   
    ![Sharepoint-nettadresse](./media/sharepoint-scenario-setup/01-03-03c-sharepoint-url.png)
9. Velg **Prosjektdetaljer**-listen, og klikk eller trykk deretter på **Koble til**.
   
    ![Liste for prosjektdetaljer](./media/sharepoint-scenario-setup/01-03-03d-project-details.png)
   
    **Data**-panelet viser nå tilkoblingen som du har opprettet.
   
    ![Datakilder](./media/sharepoint-scenario-setup/01-03-03e-data-sources.png)

10. Klikk eller trykk på ellipsen (**. . .**) ved siden av **Prosjektdetaljer**, og klikk eller trykk deretter på **Oppdater**.
    
    ![Å oppdatere datakilde for prosjektdetaljer](./media/sharepoint-scenario-setup/01-03-02-remove.png)

11. Klikk på ![Kjør app-ikonet](./media/sharepoint-scenario-setup/icon-run-arrow.png) øverst til høyre for å kjøre appen, og kontroller at tilkoblingen fungerer.

12. Klikk eller trykk på **Fil**, og lagre deretter appen i skyen. 

12. Gjenta trinnene i denne delen for **project-requests-app.msapp**, ved bruk av listen for **prosjektforespørsler**.

### <a name="update-connections-for-the-sample-report"></a>Å oppdatere tilkoblinger for eksempelrapporten
1. Åpne **project-analysis.pbix** i Power BI Desktop.

2. Klikk eller trykk på **Rediger spørringer** på **Hjem**-fanen på båndet, og deretter **Innstillinger for datakilde**.
   
    ![Å redigere spørringer](./media/sharepoint-scenario-setup/01-03-04-edit-queries.png)

3. Klikk eller trykk på **Endre kilde**.
   
    ![Innstillinger for datakilde](./media/sharepoint-scenario-setup/01-03-05-settings.png)

4. Angi nettadressen for SharePoint Online-området, og klikk eller trykk deretter **OK**, så **Lukk**.
   
    ![Nettadresse for SharePoint-liste](./media/sharepoint-scenario-setup/01-03-06-list-url.png)

5. Power BI Desktop viser et banner under båndet, slik at du kan bruke endringene og hente inn data fra den nye kilden. Klikk eller trykk på **Bruk endringer**.
   
    ![Å bruke spørringsendringer](./media/sharepoint-scenario-setup/01-03-07-apply.png)

6. Logg på med en Microsoft-konto (kontoen du bruker til å få tilgang til SharePoint Online), og klikk eller trykk deretter på **Koble til**.
   
    ![Å koble til SharePoint Online](./media/sharepoint-scenario-setup/01-03-08-connect.png)

## <a name="next-steps"></a>Neste trinn
Det neste trinnet i denne opplæringsserien er å [generere en app til å håndtere prosjektforespørsler](sharepoint-scenario-generate-app.md).

