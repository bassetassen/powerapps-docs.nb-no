---
title: Installer og konfigurer brukerstøtteeksemplet for lerretsapper | Microsoft Docs
description: Trinnvise instruksjoner for installering og konfigurering av brukerstøtteeksemplet for lerretsapper i PowerApps.
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
ms.openlocfilehash: 2c367aa57294e52fc22f538f88b361c90c3afb99
ms.sourcegitcommit: e64344548d607767e495a6b9526900bb5975226a
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/21/2019
ms.locfileid: "58330244"
---
# <a name="install-and-configure-the-help-desk-sample-in-powerapps"></a>Installer og konfigurer brukerstøtteeksemplet i PowerApps

Trinnvise instruksjoner for installering og konfigurering av brukerstøtteeksemplet for lerretsapper i PowerApps.

Estimert tid det tar å fullføre disse trinnene: **10–15 minutter**

> [!TIP]
> Hvis du vil se en demonstrasjon av prosessen, kan du ta en titt på denne [videoen](https://youtu.be/z4cdtD6hB_4).

## <a name="overview-of-the-sample"></a>Oversikt over eksemplet

Teknisk støtte tilbyr en brukervennlig opplevelse for å la brukere etablere kontakt med teknikere. Finn svar raskt på de viktigste spørsmålene, spor fremgang for åpne kundesaker, og se gjennom detaljer for tidligere forespørsler. Denne appen krever litt konfigurasjon for å tilpasses dine behov.

![Å åpne skjermbildet i Teknisk støtte for PowerApp](./media/help-desk-install/Login-screen.png)

> [!TIP]
> Se denne [videoen](https://youtu.be/sl5fXwwnvzI) for å se hvordan du bruker eksemplet for Teknisk støtte for PowerApp.

## <a name="prerequisites"></a>Forutsetninger

- [Registrer deg](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) for PowerApps.
- Må ha en gyldig SharePoint Online-lisens og tillatelse til å opprette lister.

## <a name="create-the-helpdesk-sharepoint-list"></a>Å opprette kundestøttelisten for SharePoint

Denne listen lagrer forespørsler til teknisk støtte.

1. Åpne en nettleser og gå til https://admin.microsoft.com.
2. Logg på med en konto som har tillatelse til å opprette SharePoint-lister.
3. Gå til områdesamlingen der du vil lagre listen til kundestøtte.
4. Klikk på **tannhjulikonet** i øverste høyre del av nettsiden.
5. Klikk på **Legg til en app**.
6. Angi **Egendefinert** i **Finn en app**-tekstboksen.
7. Klikk på **søkeikonet**.
8. Klikk på **Egendefinert liste**-appen.
9. I tekstboksen **Navn** kan du angi **Kundestøtte**.

    > [!IMPORTANT]
    > Hvis du velger et annet navn for listen, må du sørge for at du skriver det ned, for du må angi det på nytt for kundestøtte hva gang du ser det i løpet av installasjons- og konfigurasjonsprosessen.

10. Klikk på **Opprett**.

### <a name="create-description-column"></a>Å opprette beskrivende kolonne

1. Velg ellipsen ved siden av listen for brukerstøtte, og klikk deretter på **Innstillinger**.
2. Klikk på **Opprett kolonne**.
3. Angi **Beskrivelse** på **Kolonnenavn**-tekstboksen.
4. Velg **Flere linjer med tekst** i alternativknapplisten **Informasjonstypen i denne kolonnen er**.
5. Velg **Ja** i alternativknapplisten **Krev at denne kolonnen inneholder informasjon**.
6. Velg **Ren tekst** i alternativknapplisten **Angi type tekst som skal være tillatt**.
7. Klikk på **OK**.

### <a name="create-category-column"></a>Å opprette kategori-kolonne

1. Klikk på **Opprett kolonne**.
2. Angi **Kategori** i tekstboksen **Kolonnenavn**.
3. Velg **Valg** i alternativknapplisten **Informasjonstypen i denne kolonnen er**.
4. Angi følgende verdier i tekstboksen til **Skriv inn hvert valg på en egen linje**, hver av dem på en egen linje: 
    - Problem med BÆRBAR DATAMASKIN / PC-utstyr
    - Problem med BÆRBAR DATAMASKIN / programvare for PC
5. Velg **Ingen** i alternativknapplisten **Fremtving unike verdier**.
6. Velg **Rullegardinmeny** i alternativknapplisten **Vis valg med**.
7. Skriv **Problem med bærbar datamaskin / PC-utstyr** i tekstboksen **Standardverdi**.
8. Klikk på **OK**.

### <a name="create-percentcomplete-column"></a>Opprett PercentComplete-kolonne

1. Klikk på **Opprett kolonne**.
2. I tekstboksen **Kolonnenavn** angir du **PercentComplete**.
3. Velg **Tall (1, 10, 100)** i alternativknapplisten **Informasjonstypen i denne kolonnen er**.
4. Velg **Nei** i alternativknapplisten **Krev at denne kolonnen inneholder informasjon**.
5. Klikk på **OK**.

### <a name="create-priority-column"></a>Å opprette prioritetskolonne

1. Klikk på **Opprett kolonne**.
2. I tekstboksen **Kolonnenavn** angir du **Prioritet**.
3. Velg **Valg** i alternativknapplisten **Informasjonstypen i denne kolonnen er**.
4. Angi følgende verdier i tekstboksen til **Skriv inn hvert valg på en egen linje**, hver av dem på en egen linje: 
    - HØY
    - MIDDELS
    - LAV
5. Velg **Ingen** i alternativknapplisten **Fremtving unike verdier**.
6. Velg **Rullegardinmeny** i alternativknapplisten **Vis valg med**.
7. Angi **LAV** i tekstboksen **Standardverdi**.
8. Klikk på **OK**.

### <a name="create-taskstatus-column"></a>Å opprette TaskStatus-kolonne

1. Klikk på **Opprett kolonne**.
2. I tekstboksen **Kolonnenavn** angir du **Kolonnenavn**.
3. Velg **Valg** i alternativknapplisten **Informasjonstypen i denne kolonnen er**.
4. Angi følgende verdier i tekstboksen til **Skriv inn hvert valg på en egen linje**, hver av dem på en egen linje: 
    - IKKE PÅBEGYNT
    - PÅGÅR
    - FULLFØRT
    - UTSATT
    - VENTER PÅ CSR
5. Velg **Ingen** i alternativknapplisten **Fremtving unike verdier**.
6. Velg **Rullegardinmeny** i alternativknapplisten **Vis valg med**.
7. Angi **IKKE PÅBEGYNT** i tekstboksen **Standardverdi**.
8. Klikk på **OK**.

### <a name="create-assignedto-column"></a>Å opprette en AssignedTo-kolonne

1. Klikk på **Opprett kolonne**.
2. I tekstboksen **Kolonnenavn** angir du **AssignedTo**.
3. Velg **Person eller gruppe** i alternativknapplisten **Informasjonstypen i denne kolonnen er**.
4. Velg **Nei** i alternativknapplisten **Krev at denne kolonnen inneholder informasjon**.
5. Velg **NEI** i alternativknapplisten **Tillat flere valg**.
6. Klikk på **OK**.

### <a name="edit-title-column"></a>Å redigere Tittel-kolonne

1. Klikk på koblingen **Tittel**-kolonne.
2. Velg **Nei** i alternativknapplisten **Krev at denne kolonnen inneholder informasjon**.
3. Klikk på **OK**.

## <a name="download-the-help-desk-powerapp"></a>Å laste ned Teknisk støtte for PowerApp

1.  [Last ned](http://pappsfeprodwestuscontent.blob.core.windows.net/sampleapps/helpdesk/docs/HelpDesk(SP_List).zip) PowerApps-pakken, og lagre den til datamaskinen.

## <a name="create-connections"></a>Å opprette tilkoblinger

1.  Gå til [web.powerapps.com](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) i en nettleser.
2.  Logg deg på ved å angi samme legitimasjon som du brukte til å registrere deg.
3.  I menyen til venstre velger du **Data**, og deretter **Tilkoblinger**.
    
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

### <a name="create-office-365-users-connection"></a>Å opprette tilkobling for Office 365-brukere

1.  Klikk på **+ Ny tilkobling**.
2.  Angi **Office 365-brukere** i **Søk**-tekstboksen.
3.  Velg **Office 365-brukere** i listen.
4.  Klikk på **Opprett**.
5.  I popup-vinduet velger du kontoen du logget på med.

## <a name="import-the-help-desk-powerapp"></a>Å importere Teknisk støtte for PowerApp

1. Gå til https://web.powerapps.com i en nettleser.
2. Logg deg på ved å angi samme legitimasjon som du brukte til å registrere deg.
3. I menyen til venstre velger du **Apper**. 
4. Klikk på **importer pakke (forhåndsvisning)**.
    
   ![Et skjermbilde for Importer pakke](./media/help-desk-install/import-package.png)

5. Klikk på **Last opp**-knappen, og velg den PowerApp-pakken som du lastet ned i forrige trinn.
6. For ressurstypene **App** og **Flyt** kan du angi **IMPORT AV OPPSETT** til **Opprett som ny**.
7. Angi **IMPORT AV OPPSETT** til **Velg under import** for **SharePoint-** og **Outlook**-tilkoblinger.
    
   ![Å importere Innstillinger-skjermen](./media/help-desk-install/import-settings.png)

8. Klikk på det **røde ikonet** for å velge **SharePoint-tilkoblingen**.
9. Klikk på elementet med brukernavnet ditt i listen med tilkoblinger.

   ![Å importere Innstillinger-skjermen](./media/help-desk-install/import-settings-sharepoint.png)

10. Klikk på **Lagre**.
11. Klikk på det **røde ikonet** for å velge **Office 365 Outlook-tilkoblingen**.
12. Klikk på elementet med brukernavnet ditt i listen med tilkoblinger.

    ![Å importere Innstillinger-skjermen](./media/help-desk-install/import-settings-office365outlook.png)

13. Klikk på **Lagre**.

    > [!TIP] 
    > Når du er ferdig, vil det se ut som dette.

    ![Å importere Innstillinger-skjermen](./media/help-desk-install/import-settings-done.png)

14. Klikk på **Importer**, og vent til prosessen er fullført.

    ![Å importere Innstillinger-skjermen](./media/help-desk-install/import-done.png)

## <a name="configure-the-powerapp-to-use-the-sharepoint-list"></a>Konfigurer PowerApp for å bruke SharePoint-listen

1. Under neste trinn klikker du på **Åpne app**.
2. Klikk på **Tillat** når du blir spurt om tillatelse.

### <a name="delete-connections"></a>Å slette tilkoblinger

1. Klikk på **Vis**.
2. Klikk på **Datakilder**.
3. I **Data**-ruten klikker du på **ellipsen** ved siden av SharePoint-tilkoblingen **Kundestøtte**.
4. Klikk på **Fjern**.

### <a name="helpdesk-list"></a>Kundestøtte-liste

1. Klikk på **Vis**.
2. Klikk på **Datakilder**.
3. I **Data**-ruten klikker du på **+ Legg til datakilde**.
4. Velg **SharePoint**.
5. Klikk på **Opprett**.
6. I **Nylig brukte områder**-listen velger du SharePoint-området der du opprettet kundestøttelisten.

    > [!TIP] 
    > Hvis området ikke vises i listen, skriver du inn nettadressen til SharePoint-området i tekstboksen, og klikker på **Gå til**.

7. I **Søk**-tekstboksen øverst i listen angir du **Kundestøtte**.
8. Merk av i avmerkingsboksen ved siden **Kundestøttelisten**.
9. Klikk på **Koble til**.

### <a name="update-admin-list"></a>Å oppdatere administratorliste

1. Velg **LoginScreen**.
2. Velg **OnStart** i rullegardinlisten.
3. Utvid formelvinduet, og finn **AdminList**-samlingen.
4. Erstatt <strong>user@microsoft.com</strong> med kundestøtteadministrator(er).

    ![Å oppdatere administratorliste](./media/help-desk-install/Change-admin.png)
    
   > [!TIP]
   > Hvis du har mer enn én administrator, bruker du semikolon til å avgrense administratorer.  Eksempel: "admin1@microsoft.com","admin2@microsoft.com".
   > For å sikre at adressene i AdminList samsvarer med formatet PowerApps forventer, velger du Vis > Variabler > Global > MyProfile og ser på e-postkolonnen for å vise det forventede e-postformatet.

5. Klikk på **Fil**.
6. Klikk på **Lagre**.
7. Klikk på **Publiser**.
8. Klikk på **Publiser denne versjonen**.

## <a name="modify-the-flow"></a>Å endre flyten

1.  På menyen til venstre klikker du på **Flyter**.
2.  Logg deg på ved å angi samme legitimasjon som du brukte til å registrere deg, dersom du blir bedt om å logge deg på.
3.  Velg **Mine flyter** i menyen øverst.
4.  Klikk på **blyantikonet** ved siden av **HelpDeskFlow**-flyten. 
 
    ![Å redigere Flyt-skjermen](./media/help-desk-install/edit-flow.png)

5.  Utvid **Hent elementer**-handlingen. 
6.  Endre **områdeadressen** og **listenavnet** for å samsvare med kundestøttelisten du opprettet i SharePoint.
    
    ![Å redigere Flyt-skjermen](./media/help-desk-install/edit-flow-getitems.png)

    > [!TIP] 
    > Du trenger ikke å skrive det inn manuelt, du kan velge det i rullegardinlistene.

7.  Utvid **bryteren**.
8.  Utvid **IKKE PÅBEGYNT**-saken.
9.  Utvid handlingen **Tilfelle ikke påbegynt**.
10. Endre **Til** slik at det samsvarer med e-postadressen for kundestøtteadministrasjonen.

    ![Å redigere Flyt-skjermen](./media/help-desk-install/edit-flow-condition-send-email.png) 

11. Klikk på **Oppdater flyt**.

## <a name="play-the-powerapp"></a>Å spille av PowerApp

1. I nettleseren klikker du på **Apper**.
2. Klikk på **ellipsen** ved siden av Teknisk støtte for PowerApp.
3. Klikk på **Åpne**. 

> [!TIP]
> Se denne [videoen](https://youtu.be/sl5fXwwnvzI) for å se hvordan du bruker eksemplet for Teknisk støtte for PowerApp.


## <a name="next-steps"></a>Neste trinn
- [Å tilpasse et SharePoint-listeskjema](https://docs.microsoft.com/powerapps/maker/canvas-apps/customize-list-form)
- [Å legge til og konfigurere en kontroll](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-configure-controls)
- [Å redigere og behandle tillatelser for en SharePoint-liste eller et bibliotek](https://support.office.com/en-us/article/edit-and-manage-permissions-for-a-sharepoint-list-or-library-02d770f3-59eb-4910-a608-5f84cc297782)
 
