---
title: Installer og konfigurer utgiftsrapporteksemplet for lerretsapper | Microsoft Docs
description: Trinnvise instruksjoner for installering og konfigurering av utgiftsrapporteksemplet for lerretsapper i PowerApps.
author: mr-dang-msft
manager: kvivek
ms.service: powerapps
ms.topic: sample
ms.custom: canvas
ms.reviewer: anneta
ms.date: 04/08/2018
ms.author: brdang
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 4640c1f3fcab1382ec70573cea2ac259cf8b2a30
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/23/2019
ms.locfileid: "61561064"
---
# <a name="install-and-configure-the-expense-report-sample-for-canvas-apps-in-powerapps"></a>Installer og konfigurer utgiftsrapporteksemplet for lerretsapper i PowerApps

Trinnvise instruksjoner for installering og konfigurering av utgiftsrapporteksemplet. Du kan også forhåndsvise eksempelappen [her](https://aka.ms/previewmyexpenses).

Estimert tid det tar å fullføre disse trinnene: **10–15 minutter**

> [!TIP]
> Se [denne videoen](https://youtu.be/kJXZPILfbwU) for en demonstrasjon av hvordan du bruker eksempelappen for utgiftsrapport. 

Spor utgiftsrapporter fra sending til godkjennelse. Legg sammen elementer som individuelle utgifter og send for godkjennelse når det er klart. Denne appen krever litt konfigurasjon for å tilpasses dine behov.

![Åpningsskjerm for utgiftsrapport i PowerApps](./media/expense-report-install/expense-report-powerapp.png)

> [!TIP]
> Se [denne](https://youtu.be/h6E9cdrOvMU) videoen for å se hvordan du bruker eksemplet for utgiftsrapport.

## <a name="prerequisites"></a>Forutsetninger

- [Registrer deg](../signup-for-powerapps.md) for PowerApps.

## <a name="create-the-expenses-list"></a>Opprett Utgifter-listen

Denne listen inneholder utgiftsrapporten.

1. Åpne en nettleser og gå til https://admin.microsoft.com.
2. Logge på med en konto som har tillatelse til å opprette lister.
3. Gå til områdesamlingen der du vil lagre Utgifter-listen.
4. Klikk på tannhjulikonet øverst til høyre på nettsiden.
5. Klikk på **Legg til en app**.
6. Angi **Egendefinert** i **Finn en app**-tekstboksen.
7. Klikk på **søkeikonet**.
8. Klikk på **Egendefinert liste**-appen.
9. Angi **Utgifter** i tekstboksen **Navn**.

    > [!IMPORTANT]
    > Hvis du velger et annet navn for listen, sørg for å skrive det ned, fordi du må angi det som erstatning for Utgifter hver gang du ser det i løpet av installasjons- og konfigurasjonsprosessen.

10. Klikk på **Opprett**.

### <a name="create-cost-center-column"></a>Å opprette Kostsenter-kolonnen

1. Klikk på **Utgifter**-listen.
2. Klikk på tannhjulikonet øverst til høyre på nettsiden.
3. Klikk på **Listeinnstillinger**.
4. Klikk på **Opprett kolonne**.
5. Angi **Kostsenter** i tekstboksen **Kolonnenavn**.
6. Velg **Valg** i alternativknapplisten **Informasjonstypen i denne kolonnen er**.
7. Angi følgende verdier i tekstboksen **Skriv hvert valg på en egen linje**, hver av dem på en egen linje: 
    - Microsoft
    - Contoso
8. Angi **Microsoft** i tekstboksen **Standardverdi**.
9. Klikk på **OK**.

### <a name="create-comments-column"></a>Å opprette Kommentarer-kolonnen

1. Klikk på **Opprett kolonne**.
2. Angi **Kommentarer** i tekstboksen **Kolonnenavn**.
3. Velg **Flere linjer med tekst** i alternativknapplisten **Informasjonstypen i denne kolonnen er**.
4. Klikk på **OK**.

### <a name="create-status-column"></a>Å opprette Status-kolonnen

1. Klikk på **Utgifter**-listen.
2. Klikk på **tannhjulikonet** i øverste høyre del av nettsiden.
3. Klikk på **Listeinnstillinger**.
4. Klikk på **Opprett kolonne**.
5. Angi **Status** i tekstboksen **Kolonnenavn**.
6. Velg **Valg** i alternativknapplisten **Informasjonstypen i denne kolonnen er**.
7. Angi følgende verdier i tekstboksen **Skriv hvert valg på en egen linje**, hver av dem på en egen linje: 
    - Åpne
    - Venter
    - Godkjent
8. Angi **Åpen** i tekstboksen **Standardverdi**.
9. Klikk på **OK**.

### <a name="create-approvername-column"></a>Å opprette ApproverName-kolonnen

1. Klikk på **Opprett kolonne**.
2. Angi **ApproverName** i tekstboksen **Kolonnenavn**.
3. Velg **Person eller gruppe** i alternativknapplisten **Informasjonstypen i denne kolonnen er**.
4. Velg **Ja** i alternativknapplisten **Krev at denne kolonnen inneholder informasjon**.
5. Klikk på **OK**.

### <a name="create-datesubmitted-column"></a>Opprette DateSubmitted-kolonnen

1. Klikk på **Opprett kolonne**.
2. Angi **DateSubmitted** i tekstboksen **Kolonnenavn**.
3. Velg **dato og tidspunkt** i alternativknapplisten **Informasjonstypen i denne kolonnen er**.
4. Velg **Ja** i alternativknapplisten **Krev at denne kolonnen inneholder informasjon**.
5. Klikk på **OK**.

### <a name="create-startdate-column"></a>Å opprette StartDate-kolonnen

1. Klikk på **Opprett kolonne**.
2. Angi **StartDate** i tekstboksen **Kolonnenavn**.
3. Velg **dato og tidspunkt** i alternativknapplisten **Informasjonstypen i denne kolonnen er**.
4. Velg **Ja** i alternativknapplisten **Krev at denne kolonnen inneholder informasjon**.
5. Klikk på **OK**.

### <a name="create-enddate-column"></a>Å opprette EndDate-kolonnen

1. Klikk på **Opprett kolonne**.
2. Angi **EndDate** i tekstboksen **Kolonnenavn**.
3. Velg **dato og tidspunkt** i alternativknapplisten **Informasjonstypen i denne kolonnen er**.
4. Velg **Ja** i alternativknapplisten **Krev at denne kolonnen inneholder informasjon**.
5. Klikk på **OK**.

## <a name="create-the-lineitems-list"></a>Klikk på listen LineItems

Denne listen lagrer linjeelementene som er knyttet til hver utgiftsrapport.

1. Gå til den samme områdesamlingen der du opprettet Utgifter-listen.
2. Klikk på tannhjulikonet øverst til høyre på nettsiden.
3. Klikk på **Legg til en app**.
4. Angi **Egendefinert** i **Finn en app**-tekstboksen.
5. Klikk på **søkeikonet**.
6. Klikk på **Egendefinert liste**-appen.
7. Angi **LineItems** i tekstboksen **Navn**.

    > [!IMPORTANT] 
    > Hvis du velger et annet navn for listen, sørg for å skrive det ned, fordi du må angi det som erstatning for LineItems hver gang du ser det i løpet av installasjons- og konfigurasjonsprosessen.

8. Klikk på **Opprett**.
 
### <a name="create-category-column"></a>Å opprette kategori-kolonne

1. Klikk på **LineItems**-listen.
2. Klikk på tannhjulikonet øverst til høyre på nettsiden.
3. Klikk på **Listeinnstillinger**.
4. Klikk på **Opprett kolonne**.
5. Angi **Kategori** i tekstboksen **Kolonnenavn**.
6. Velg **Valg** i alternativknapplisten **Informasjonstypen i denne kolonnen er**.
7. Angi følgende verdier i tekstboksen til **Skriv inn hvert valg på en egen linje**, hver av dem på en egen linje: 
    - Mat og drikkevarer
    - Transport
    - Forretningsbehov
8. Angi **Mat og drikkevarer** i tekstboksen **Standardverdi**.
9. Klikk på **OK**.

### <a name="create-cost-column"></a>Å opprette Kostnad-kolonnen

1. Klikk på **Opprett kolonne**.
2. Angi **Kostnad** i tekstboksen **Kolonnenavn**.
3. Velg **Tall (1, 10, 100)** i alternativknapplisten **Informasjonstypen i denne kolonnen er**.
4. Velg **Ja** i alternativknapplisten **Krev at denne kolonnen inneholder informasjon**.
5. Klikk på **OK**.

### <a name="create-date-column"></a>Å opprette dato-kolonnen

1. Klikk på **Opprett kolonne**.
2. Angi **Dato** i tekstboksen **Kolonnenavn**.
3. Velg **dato og tidspunkt** i alternativknapplisten **Informasjonstypen i denne kolonnen er**.
4. Velg **Ja** i alternativknapplisten **Krev at denne kolonnen inneholder informasjon**.
5. Klikk på **OK**.

### <a name="create-description-column"></a>Å opprette beskrivende kolonne

1. Klikk på **Opprett kolonne**.
2. Angi **Beskrivelse** på **Kolonnenavn**-tekstboksen.
3. Velg **Flere linjer med tekst** i alternativknapplisten **Informasjonstypen i denne kolonnen er**.
4. Velg **Ja** i alternativknapplisten **Krev at denne kolonnen inneholder informasjon**.
5. Velg **Ren tekst** i alternativknapplisten **Angi type tekst som skal være tillatt**.
6. Klikk på **OK**.

### <a name="create-reportid-column"></a>Å opprette ReportID-kolonnen

1. Klikk på **Opprett kolonne**.
2. Angi **ReportID** i tekstboksen **Kolonnenavn**.
3. Velg **Oppslag (informasjon som allerede er på området)** i alternativknapplisten **Informasjonstypen i denne kolonnen er**.
4. Velg **Ja** i alternativknapplisten **Krev at denne kolonnen inneholder informasjon**.
5. Velg **Utgifter**-listen du opprettet, i rullegardinlisten **Hent informasjon fra**.
6. Velg **ID** i rullegardinlisten **I denne kolonnen**.
7. Klikk på **OK**.

### <a name="edit-title-column"></a>Å redigere Tittel-kolonne

1. Klikk på koblingen **Tittel**-kolonne.
2. Velg **Nei** i alternativknapplisten **Krev at denne kolonnen inneholder informasjon**.
3. Klikk på **OK**.

## <a name="download-the-expense-report-app"></a>Last ned Utgiftsrapport-appen

1. Gå til følgende kobling i en nettleser:

    [http://pappsfeprodwestuscontent.blob.core.windows.net/sampleapps/myexpenses/docs/MyExpenses(SP_List).zip](http://pappsfeprodwestuscontent.blob.core.windows.net/sampleapps/myexpenses/docs/MyExpenses(SP_List).zip).

2. Last ned eksemplet for utgiftsrapport for PowerApps, og lagre det på datamaskinen.

## <a name="create-connections"></a>Å opprette tilkoblinger

1.  Gå til [web.powerapps.com](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) i en nettleser.
2.  Logg deg på ved å angi samme legitimasjon som du brukte til å registrere deg.
3.  I menyen til venstre velger du **Tilkoblinger**.

### <a name="create-an-approvals-connection"></a>Oppretting av Godkjenninger-tilkobling

1.  Klikk på **+ Ny tilkobling**.
2.  Angi **Godkjennelser** i **Søk**-tekstboksen.
3.  Velg **Godkjennelser** i listen.
4.  Klikk på **Opprett**.
    
### <a name="create-an-office-365-outlook-connection"></a>Oppretting av en Office 365 Outlook-tilkobling

1.  Klikk på **+ Ny tilkobling**.
2.  Angi **Office 365 Outlook** i **Søk**-tekstboksen.
3.  Velg **Office 365 Outlook** i listen.
4.  Klikk på **Opprett**.
5.  I popup-vinduet velger du kontoen du logget på med.

### <a name="create-a-sharepoint-connection"></a>Oppretting av en SharePoint-tilkobling

1.  Klikk på **+ Ny tilkobling**.
2.  Angi **SharePoint** i **Søk**-tekstboksen.
3.  Velg **SharePoint** i listen.
4.  Klikk på **Opprett**.
5.  I popup-vinduet velger du kontoen du logget på med.

## <a name="import-the-app"></a>Import av filen

1. Gå til https://web.powerapps.com i en nettleser.
1. Logg deg på ved å angi samme legitimasjon som du brukte til å registrere deg.
1. Velg **Apper** i venstre navigasjonsfelt, og velg deretter **Importer pakke (forhåndsversjon)**.

    ![Et skjermbilde for Importer pakke](./media/expense-report-install/import-package.png)

1. Velg **Last opp**, og velg deretter pakken du lastet ned tidligere.
1. For ressurstypene **App** og **Flyt** kan du angi **IMPORT AV OPPSETT** til **Opprett som ny**.
1. Angi **IMPORT AV OPPSETT** til **Velg under import** for **SharePoint-** og **Outlook**-tilkoblinger.

    ![Å importere Innstillinger-skjermen](./media/expense-report-install/import-settings.png)

1. Klikk på det røde ikonet for **SharePoint-tilkobling**.
1. Klikk på tilkoblingslisten og velg elementet med ditt brukernavn.

    ![Å importere Innstillinger-skjermen](./media/expense-report-install/import-settings-sharepoint.png)

1. Velg **Lagre**.
1. Velg det røde ikonet for **Godkjenning-tilkobling**.
1. Klikk på tilkoblingslisten og velg elementet med ditt brukernavn.

    ![Å importere Innstillinger-skjermen](./media/expense-report-install/import-settings-approvals.png)

1. Velg **Lagre**.
1. Klikk på det røde ikonet for **Tilkobling til Office 365 Outlook**.
1. Klikk på tilkoblingslisten og velg elementet med ditt brukernavn.

    ![Å importere Innstillinger-skjermen](./media/expense-report-install/import-settings-office365outlook.png)

1. Velg **Lagre**.

    > [!TIP] 
    > Når du er ferdig, vil det se slik ut:

    ![Å importere Innstillinger-skjermen](./media/expense-report-install/import-settings-done.png)

1. Klikk på **Importer**, og vent til prosessen er fullført.

    ![Å importere Innstillinger-skjermen](./media/expense-report-install/import-done.png)

## <a name="configure-the-app-to-use-the-sharepoint-lists"></a>Konfigurer appen til å bruke SharePoint-listene

1. Klikk på **Apper** i nettleseren.
2. Klikk på ellipsene (...) ved siden av Utgiftsrapport-appen.
3. Velg **Rediger på nettet** > **Tillat**.

### <a name="delete-connections"></a>Å slette tilkoblinger
1. Velg **Datakilder** på **Vis**-fanen.
1. Velg ellipsene (...) ved siden **Utgifter** i **Data**-ruten, og velg deretter **Fjern**.
1. Gjenta forrige trinn for å fjerne datakilden **LineItems**.

### <a name="expenses-list"></a>Utgifter-listen

1. Velg **Datakilder** på **Vis**-fanen.
1. Velg **Legg til datakilde** > **Ny tilkobling** > **SharePoint** > **Opprett**, i **Data**-ruten.
1. Velg SharePoint-området der du opprettet Utgifter-listen, i listen **Nylig brukte områder**.

    > [!TIP] 
    > Hvis området ikke vises i listen, skriv eller lim inn adressen til SharePoint-området i tekstboksen, og velg **Gå til**.

1. Skriv eller lim inn **Utgifter** i **Søk**-boksen øverst i listen.
1. Merk av i boksen ved siden **Utgifter**, og velg deretter **Koble til**.

### <a name="lineitems-list"></a>LineItems-listen

1. Velg **Datakilder** på **Vis**-fanen.
1. Velg **SharePoint** i **Data**-ruten.
1. Velg SharePoint-området der du opprettet LineItems-listen, i listen **Nylig brukte områder**.

    > [!TIP] 
    > Hvis området ikke vises i listen, skriv eller lim inn adressen til SharePoint-området i tekstboksen, og velg **Gå til**.

1. Skriv eller lim inn **Linjeelementer** i **Søk**-boksen øverst i listen.
1. Merk av i boksen ved siden **LineItems**, og velg deretter **Koble til**.
1. Velg **Fil** > **Lagre** > **Publiser** > **Publiser denne versjonen**.

## <a name="modify-the-flow"></a>Endring av flyten

1. Velg **Flyter** i venstre navigasjonsfelt.
1. Hvis du blir bedt om å logge på, oppgi samme legitimasjon som du brukte til å registrere deg.
1. Velg **Mine flyter** nær toppen av skjermen.
1. Klikk på blyantikonet ved siden av **ApproveExpense**-flyten.

    ![Å redigere Flyt-skjermen](./media/expense-report-install/edit-flow.png)

1. Utvid **Hent elementer**-handlingen. 
1. Endre **Områdeadresse** og **Listenavn** for å samsvare med Utgifter-listen du opprettet i SharePoint.

    ![Å redigere Flyt-skjermen](./media/expense-report-install/edit-flow-getitems.png)

    > [!TIP] 
    > Du trenger ikke å skrive det inn manuelt, du kan velge det i rullegardinlistene.

1. Utvid **Betingelse**.
1. Utvid **Hvis ja**-delen.
1. Utvid handlingen **Endre elementstatus til Godkjent**.
1. Endre **Områdeadresse** og **Listenavn** for å samsvare med Utgifter-listen du opprettet i SharePoint.

    ![Å redigere Flyt-skjermen](./media/expense-report-install/edit-flow-condition-ifyes.png) 

    > [!TIP] 
    > Du trenger ikke å skrive det inn manuelt, du kan velge det i rullegardinlistene.

1. Utvid **Hvis nei**-delen.
1. Utvid handlingen **Endre elementstatus til Åpen**.
1. Endre **Områdeadresse** og **Listenavn** for å samsvare med Utgifter-listen du opprettet i SharePoint. 

    ![Å redigere Flyt-skjermen](./media/expense-report-install/edit-flow-condition-ifno.png)

    > [!TIP] 
    > Du trenger ikke å skrive det inn manuelt, du kan velge det i rullegardinlistene.

14. Velg **Oppdater flyt**.

## <a name="play-the-app"></a>Spill av appen

1. Klikk på **Apper** i nettleseren.
1. Klikk på ellipsene (...) ved siden av utgiftsrapporten, og velg deretter **Åpne**.

## <a name="next-steps"></a>Neste trinn
- [Å tilpasse et SharePoint-listeskjema](https://docs.microsoft.com/powerapps/maker/canvas-apps/customize-list-form)
- [Å legge til og konfigurere en kontroll](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-configure-controls)
- [Å redigere og behandle tillatelser for en SharePoint-liste eller et bibliotek](https://support.office.com/article/edit-and-manage-permissions-for-a-sharepoint-list-or-library-02d770f3-59eb-4910-a608-5f84cc297782)