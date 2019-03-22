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
ms.openlocfilehash: 166fea9e02ebdaa490b400274c971f0c7268ec76
ms.sourcegitcommit: e64344548d607767e495a6b9526900bb5975226a
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/21/2019
ms.locfileid: "58330290"
---
# <a name="install-and-configure-the-expense-report-sample-for-canvas-apps-in-powerapps"></a>Installer og konfigurer utgiftsrapporteksemplet for lerretsapper i PowerApps

Trinnvise instruksjoner for installering og konfigurering av utgiftsrapporteksemplet. Du kan også forhåndsvise eksempelappen [her](https://aka.ms/previewmyexpenses).

Estimert tid det tar å fullføre disse trinnene: **10–15 minutter**

> [!TIP]
> Se [denne videoen](https://youtu.be/kJXZPILfbwU) for en demonstrasjon av hvordan du bruker eksempelappen for utgiftsrapport. 

Spor utgiftsrapporter fra sending til godkjennelse. Legg sammen elementer som individuelle utgifter og send for godkjennelse når det er klart. Denne appen krever litt konfigurasjon for å tilpasses dine behov.

![Åpningsskjerm for utgiftsrapport i PowerApps](./media/expense-report-install/expense-report-powerapp.png)

> [!TIP]
> Se [denne](https://youtu.be/h6E9cdrOvMU) videoen for å se hvordan du bruker eksemplet for utgiftsrapport for PowerApps.

## <a name="prerequisites"></a>Forutsetninger

- [Registrer deg](../signup-for-powerapps.md) for PowerApps.

## <a name="create-the-expenses-sharepoint-list"></a>Å opprette Utgifter-listen for SharePoint

Denne listen inneholder utgiftsrapporten.

1. Åpne en nettleser og gå til https://admin.microsoft.com.
2. Logge på med en konto som har tillatelse til å opprette lister.
3. Gå til områdesamlingen der du vil lagre Utgifter-listen.
4. Klikk på **tannhjulikonet** i øverste høyre del av nettsiden.
5. Klikk på **Legg til en app**.
6. Angi **Egendefinert** i **Finn en app**-tekstboksen.
7. Klikk på **søkeikonet**.
8. Klikk på **Egendefinert liste**-appen.
9. Angi **Utgifter** i tekstboksen **Navn**.

    > [!IMPORTANT]
    > Hvis du velger et annet navn for listen, må du sørge for at du skriver det ned, for du må angi det på nytt for utgifter hver gang du ser det i løpet av installasjons- og konfigurasjonsprosessen.

10. Klikk på **Opprett**.

### <a name="create-cost-center-column"></a>Å opprette Kostsenter-kolonnen

1. Klikk på **Utgifter**-listen.
2. Klikk på **tannhjulikonet** i øverste høyre del av nettsiden.
3. Klikk på **Listeinnstillinger**.
4. Klikk på **Opprett kolonne**.
5. Angi **Kostsenter** i tekstboksen **Kolonnenavn**.
6. Velg **Valg** i alternativknapplisten **Informasjonstypen i denne kolonnen er**.
7. Angi følgende verdier i tekstboksen til **Skriv inn hvert valg på en egen linje**, hver av dem på en egen linje: 
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
7. Angi følgende verdier i tekstboksen til **Skriv inn hvert valg på en egen linje**, hver av dem på en egen linje: 
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
2. Angi **DateSubmitted** i **Kolonnenavn**-tekstboksen.
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

## <a name="create-the-line-items-sharepoint-list"></a>Å opprette Linjeelement-listen for SharePoint

Denne listen inneholder linjeelementene som er knyttet til utgiftsrapporten.

1. Gå til den samme områdesamlingen der du lagret Utgifter-listen.
2. Klikk på **tannhjulikonet** i øverste høyre del av nettsiden.
3. Klikk på **Legg til en app**.
4. Angi **Egendefinert** i **Finn en app**-tekstboksen.
5. Klikk på **søkeikonet**.
6. Klikk på **Egendefinert liste**-appen.
7. Angi **LineItems** i tekstboksen **Navn**.

    > [!IMPORTANT] 
    > Hvis du velger et annet navn for listen, må du sørge for at du skriver det ned, for du må angi det på nytt for utgifter hva gang du ser det i løpet av installasjons- og konfigurasjonsprosessen.

8. Klikk på **Opprett**.
 
### <a name="create-category-column"></a>Å opprette kategori-kolonne

1. Klikk på **LineItems**-listen.
2. Klikk på **tannhjulikonet** i øverste høyre del av nettsiden.
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

## <a name="download-the-expense-report-powerapp"></a>Å laste ned utgiftsrapporten for SharePoint

1.  Gå til følgende kobling i en nettleser:

    [http://pappsfeprodwestuscontent.blob.core.windows.net/sampleapps/myexpenses/docs/MyExpenses(SP_List).zip](http://pappsfeprodwestuscontent.blob.core.windows.net/sampleapps/myexpenses/docs/MyExpenses(SP_List).zip).

2.  Last ned eksemplet for utgiftsrapport for PowerApps, og lagre den til datamaskinen.

## <a name="create-connections"></a>Å opprette tilkoblinger

1.  Gå til [web.powerapps.com](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) i en nettleser.
2.  Logg deg på ved å angi samme legitimasjon som du brukte til å registrere deg.
3.  I menyen til venstre velger du **Tilkoblinger**.

### <a name="create-approvals-connection"></a>Å opprette Godkjenninger-tilkobling

1.  Klikk på **+ Ny tilkobling**.
2.  Angi **Godkjennelser** i **Søk**-tekstboksen.
3.  Velg **Godkjennelser** i listen.
4.  Klikk på **Opprett**.
    
### <a name="create-office-365-outlook-connection"></a>Å opprette Office 365 Outlook-tilkobling

1.  Klikk på **+ Ny tilkobling**.
2.  Angi **Office 365 Outlook** i **Søk**-tekstboksen.
3.  Velg **Office 365 Outlook** i listen.
4.  Klikk på **Opprett**.
5.  I popup-vinduet velger du kontoen du logget på med.

### <a name="create-sharepoint-connection"></a>Å legge til en SharePoint-tilkobling

1.  Klikk på **+ Ny tilkobling**.
2.  Angi **SharePoint** i **Søk**-tekstboksen.
3.  Velg **SharePoint** i listen.
4.  Klikk på **Opprett**.
5.  I popup-vinduet velger du kontoen du logget på med.

## <a name="import-the-expense-report-powerapp"></a>Å importere utgiftsrapporten for SharePoint

1. Gå til https://web.powerapps.com i en nettleser.
2. Logg deg på ved å angi samme legitimasjon som du brukte til å registrere deg.
3. I menyen til venstre velger du **Apper**. 
4. Klikk på **importer pakke (forhåndsvisning)**.
    
   ![Et skjermbilde for Importer pakke](./media/expense-report-install/import-package.png)

5. Klikk på **Last opp**-knappen, og velg den PowerApp-pakken som du lastet ned i forrige trinn.
6. For ressurstypene **App** og **Flyt** kan du angi **IMPORT AV OPPSETT** til **Opprett som ny**.
7. Angi **IMPORT AV OPPSETT** til **Velg under import** for **SharePoint-** og **Outlook**-tilkoblinger.
    
   ![Å importere Innstillinger-skjermen](./media/expense-report-install/import-settings.png)

8. Klikk på det **røde ikonet** for å velge **SharePoint-tilkoblingen**.
9. Klikk på elementet med brukernavnet ditt i listen med tilkoblinger.

   ![Å importere Innstillinger-skjermen](./media/expense-report-install/import-settings-sharepoint.png)

10. Klikk på **Lagre**.
11. Klikk på det **røde ikonet** for **tilkoblingen for godkjenning**.
12. Klikk på elementet med brukernavnet ditt i listen med tilkoblinger.

    ![Å importere Innstillinger-skjermen](./media/expense-report-install/import-settings-approvals.png)

13. Klikk på **Lagre**.
14. Klikk på det **røde ikonet** for å velge **Office 365 Outlook-tilkoblingen**.
15. Klikk på elementet med brukernavnet ditt i listen med tilkoblinger.

    ![Å importere Innstillinger-skjermen](./media/expense-report-install/import-settings-office365outlook.png)

16. Klikk på **Lagre**.

    > [!TIP] 
    > Når du er ferdig, vil det se ut som dette:

    ![Å importere Innstillinger-skjermen](./media/expense-report-install/import-settings-done.png)

17. Klikk på **Importer**, og vent til prosessen er fullført.

    ![Å importere Innstillinger-skjermen](./media/expense-report-install/import-done.png)

## <a name="configure-the-powerapp-to-use-the-sharepoint-lists"></a>Konfigurer PowerApp for å bruke SharePoint-lister

1. Klikk på **Apper** i nettleseren.
2. Klikk på **ellipsen** ved siden av utgiftsrapporten for PowerApp.
3. Klikk på **Rediger på nettet**.
4. Klikk på **Tillat**.

### <a name="delete-connections"></a>Å slette tilkoblinger
1. Klikk på **Vis**.
2. Klikk på **Datakilder**.
3. Klikk på **ellipsen** i **Data**-ruten ved siden av **Kundestøtte**.
4. Klikk på **Fjern**.
5. Klikk på **ellipsen** i **Data**-ruten ved siden av **LineItems**.
6. Klikk på **Fjern**.

### <a name="expenses-list"></a>Utgifter-listen

1. Klikk på **Vis**.
2. Klikk på **Datakilder**.
3. Klikk på **+ Legg til datakilde** i **Data**-ruten.
4. Klikk på **+ Ny tilkobling**.
5. Velg **SharePoint**.
6. Klikk på **Opprett**.
7. Velg SharePoint-området der du opprettet kundestøttelisten, i listen **Nylig brukte områder**.

    > [!TIP] 
    > Hvis området ikke vises i listen, skriver du inn nettadressen til SharePoint-området i tekstboksen, og klikker på **Gå til**.

8. Angi **Kundestøtte** i **Søk**-tekstboksen øverst i listen.
9. Merk av for **Utgifter**-listen.
10. Klikk på **Koble til**.

### <a name="lineitems-list"></a>LineItems-listen

1. Klikk på **Vis**.
2. Klikk på **Datakilder**.
3. Klikk på **+ Legg til datakilde** i **Data**-ruten.
4. Klikk på **+ Ny tilkobling**.
5. Velg **SharePoint**.
6. Klikk på **Opprett**.
7. Velg SharePoint-området der du opprettet LineItems-listen, i listen **Nylig brukte områder**.

    > [!TIP] 
    > Hvis området ikke vises i listen, skriver du inn nettadressen til SharePoint-området i tekstboksen, og klikker på **Gå til**.

8. Angi **LineItems** i **Søk**-tekstboksen øverst i listen.
9. Merk av for **LineItems**.
10. Klikk på **Koble til**.
11. Klikk på **Fil**.
12. Klikk på **Lagre**.
13. Klikk på **Publiser**.
14. Klikk på **Publiser denne versjonen**.

## <a name="modify-the-flow"></a>Å endre flyten

1.  På menyen til venstre klikker du på **Flyter**.
2.  Logg deg på ved å angi samme legitimasjon som du brukte til å registrere deg, dersom du blir bedt om å logge deg på.
3.  Velg **Mine flyter** i menyen øverst.
4.  Klikk på **blyantikonet** ved siden av **ApproveExpense**-flyten.
 
    ![Å redigere Flyt-skjermen](./media/expense-report-install/edit-flow.png)

5.  Utvid **Hent elementer**-handlingen. 
6.  Endre **områdeadressen** og **listenavnet** for å samsvare med Utgifter-listen du opprettet i SharePoint.
    
    ![Å redigere Flyt-skjermen](./media/expense-report-install/edit-flow-getitems.png)

    > [!TIP] 
    > Du trenger ikke å skrive det inn manuelt, du kan velge det i rullegardinlistene.

7.  Utvid **Betingelse**.
8.  Utvid **Hvis ja**-delen.
9.  Utvid handlingen **Endre elementstatus til Godkjent**.
10. Endre **områdeadressen** og **listenavnet** for å samsvare med Utgifter-listen du opprettet i SharePoint.

    ![Å redigere Flyt-skjermen](./media/expense-report-install/edit-flow-condition-ifyes.png) 

    > [!TIP] 
    > Du trenger ikke å skrive det inn manuelt, du kan velge det i rullegardinlistene.

11. Utvid **Hvis nei**-delen.
12. Utvid handlingen **Endre elementstatus til Åpen**.
13. Endre **områdeadressen** og **listenavnet** for å samsvare med Utgifter-listen du opprettet i SharePoint. 

    ![Å redigere Flyt-skjermen](./media/expense-report-install/edit-flow-condition-ifno.png)

    > [!TIP] 
    > Du trenger ikke å skrive det inn manuelt, du kan velge det i rullegardinlistene.

14. Klikk på **Oppdater flyt**.

## <a name="play-the-powerapp"></a>Å spille av PowerApp

1. Klikk på **Apper** i nettleseren.
2. Klikk på **ellipsen** ved siden av utgiftsrapporten for PowerApp.
3. Klikk på **Åpne**.


## <a name="next-steps"></a>Neste trinn
- [Å tilpasse et SharePoint-listeskjema](https://docs.microsoft.com/powerapps/maker/canvas-apps/customize-list-form)
- [Å legge til og konfigurere en kontroll](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-configure-controls)
- [Å redigere og behandle tillatelser for en SharePoint-liste eller et bibliotek](https://support.office.com/en-us/article/edit-and-manage-permissions-for-a-sharepoint-list-or-library-02d770f3-59eb-4910-a608-5f84cc297782)



