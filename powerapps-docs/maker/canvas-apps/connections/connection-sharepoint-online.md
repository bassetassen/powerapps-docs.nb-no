---
title: Oversikt over SharePoint-tilkoblingen | Microsoft Docs
description: Se de tilgjengelige funksjonene, svarene og eksemplene for SharePoint
services: ''
suite: powerapps
documentationcenter: ''
author: sarafankit
manager: anneta
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 07/12/2017
ms.author: sharik
ms.openlocfilehash: f79809b2eb74d4cea2ee9719a3a76e8149a533dc
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/22/2018
ms.locfileid: "30996087"
---
# <a name="connect-to-sharepoint-from-powerapps"></a>Koble til SharePoint fra PowerApps
![SharePoint](./media/connection-sharepoint-online/sharepointicon.png)

Koble til et SharePoint-område for å generere en app automatisk fra en liste, bygge en app fra grunnen av eller oppdatere en eksisterende app.

## <a name="known-issues"></a>Kjente problemer
Du kan legge til data fra en egendefinert liste, men ikke fra et bibliotek. I tillegg støttes ikke alle typer kolonner, og ikke alle typer kolonner støtter alle typer kort.

| Kolonnetype | Støtte | Standardkort |
| --- | --- | --- |
| Enkeltlinje med tekst |Ja |Vis tekst |
| Flere linjer med tekst |Ja |Vis tekst |
| Valg |Ja |Vis oppslag<br>Rediger oppslag<br>Vis flervalg<br>Rediger flervalg |
| Tall |Ja |Vis prosentandel<br>Vis vurdering<br>Vis tekst |
| Valuta |Ja |Vis prosentandel<br>Vis vurdering<br>Vis tekst |
| Dato og klokkeslett |Ja |Vis tekst |
| Oppslag |Ja |Vis oppslag<br>Rediger oppslag<br>Vis flervalg<br>Rediger flervalg |
| Boolsk (Ja/Nei) |Ja |Vis tekst<br>Aktiver/deaktiver visning |
| Person eller gruppe |Ja |Vis oppslag<br>Rediger oppslag<br>Vis flervalg<br>Rediger flervalg |
| Hyperkobling |Ja |Vis nettadresse<br>Vis tekst |
| Bilde |Ja (skrivebeskyttet) |Vis bilde<br>Vis tekst |
| Vedlegg |Ja (skrivebeskyttet) |Vis vedlegg|
| Beregnet |Ja (skrivebeskyttet) | |
| Resultat av oppgaven |Nei | |
| Eksterne data |Nei | |
| Administrerte metadata |Ja (skrivebeskyttet) | |
| Vurdering |Nei | |

Kolonner som inneholder mellomrom kan leses av PowerApps, men mellomrommene erstattes med den heksadesimale escape-koden **«\_x0020\_»**. **«Kolonnenavn»** i SharePoint vil for eksempel vises som **«Column_x0020_Name»** i PowerApps når de vises i dataoppsettet eller brukes i en formel.

## <a name="prerequisites"></a>Forutsetninger
Åpne PowerApps ved å følge *ett av* disse trinnene:

* [Registrer deg](../../signup-for-powerapps.md) for PowerApps, [installer PowerApps Studio for Windows](http://aka.ms/powerappsinstall), åpne det og logg deg deretter på ved å angi samme legitimasjon som du brukte til å registrere deg.

* [Åpne PowerApps Studio for nett](https://create.powerapps.com/api/start) i en nettleser.

    Hvis du vil ha en liste over støttede nettlesere og begrensinger i forhåndsvisningsutgivelsen av PowerApps Studio for nett, kan du se [Opprette eller redigere apper i en nettleser](../create-app-browser.md).

## <a name="create-an-app"></a>Opprette en app
* [Generer en app automatisk](../app-from-sharepoint.md) basert på dataene i en SharePoint-liste.

    Appen har som standard tre skjermer: én for å bla gjennom poster, én for å vise detaljer om en enkelt post, og én for å opprette eller oppdatere en post. Når appen er generert, vil du trolig ønske å tilpasse [skjermbildet for nettleseren](../customize-layout-sharepoint.md) og [detaljene og redigere skjermer](../customize-forms-sharepoint.md) for å imøtegå dine behov.

    **Merk:** Hvis SharePoint-listen inneholder en **Valg-**, **Oppslag-** eller **Person- eller gruppe-** kolonne, kan du se [Vis data i et galleri](connection-sharepoint-online.md#show-data-in-a-gallery)senere i dette emnet.

* Bygg din egen app fra grunnen av ved å [koble til SharePoint](../connect-to-sharepoint.md), se gjennom konsepter i [Lage en app fra grunnen av](../get-started-create-from-blank.md) og bruke dem i SharePoint i stedet for Excel.

## <a name="add-a-sharepoint-list-to-an-existing-app"></a>Legge til en SharePoint-liste i en eksisterende app
1. Åpne appen som du vil oppdatere i PowerApps Studio.

2. Klikk eller trykk på**Datakilder** på **Vis**-fanen på båndet

3. Klikk eller trykk på **Legg til datakilde** i ruten til høyre.

    ![Legge til en datakilde](./media/connection-sharepoint-online/add-data-source.png)

4. Klikk eller trykk på **Ny tilkobling**, klikk eller trykk på **SharePoint**, og klikk eller trykk deretter på **Koble til**.

    ![Legge til en SharePoint-tilkobling](./media/connection-sharepoint-online/add-sharepoint.png)

5. Angi type SharePoint-område du vil koble til:

    ![Angi type tilkobling](./media/connection-sharepoint-online/choose-type.png)

   * Klikk eller trykk på **Koble til direkte (skytjenester)** for å koble til SharePoint Online.

   * Klikk eller trykk på **Koble til med lokal datagateway** for å koble til et lokalt SharePoint-område.

       Angi **Windows** som godkjenningstype, og deretter angir du legitimasjonen din. (Hvis legitimasjonen din inkluderer et domenenavn, angir du det som *domene/alias*.)

       ![Angi legitimasjon](./media/connection-sharepoint-online/specify-creds.png)

       **Merk:** Hvis du ikke har en lokal datagateway installert, kan du [installere en](../gateway-reference.md), og deretter klikker eller trykker du på ikonet for å oppdatere listen over gatewayer.

       Klikk eller trykk på gatewayen du vil bruke under **Velg en gateway**.

       ![Velge gateway](./media/connection-sharepoint-online/choose-gateway.png)

6. Klikk eller trykk på **Koble til**.

7. Under **Koble til et SharePoint-område** klikker eller trykker du på en oppføring i **Nylig brukte områder**-listen (eller skriv eller lim inn nettadressen for området du ønsker å bruke), og deretter klikker eller trykker du på **Gå til**.

    ![Velge et SharePoint-område](./media/connection-sharepoint-online/select-sp-site.png)

8. Merk av for én eller flere lister du ønsker å bruke under **Velg en liste**, og deretter klikker eller trykker du på **Koble til**:  

    ![Velge tabellene i SharePoint](./media/connection-sharepoint-online/select-sp-tables.png)

    Ikke alle typer lister vises som standard. Hvis navnet på listen du vil bruke ikke vises, kan du bla til bunnen og deretter skrive inn listenavnet i boksen som inneholder **Skriv inn navn på egendefinert liste**.

    ![Egendefinert liste i SharePoint](./media/connection-sharepoint-online/custom-list.png)

    Datakildene blir lagt til appen.

    ![Listen over datakilder som er lagt til appen](./media/connection-sharepoint-online/data-sources-list.png)

## <a name="show-data-in-a-gallery"></a>Vis data i et galleri
Bruk formellinjen for å angi **Tekst**-egenskapen for én eller flere **Etikett**-kontroller i galleriet for å vise data fra noen av disse kolonnetypene i et galleri:

* Angi **ThisItem.[ColumnName].Value** for å vise data for **Valg-** eller **Oppslag-** kolonner.

    Angi for eksempel **ThisItem.Location.Value** hvis du har en **Valg**-kolonne ved navn **Location**, og angi **ThisItem.PostalCode.Value** hvis du har en **Oppslag**-kolonne ved navn **PostalCode**.

* Angi **ThisItem.[ColumnName].DisplayName** for å vise visningsnavnet for brukeren eller gruppen for **Person- eller gruppe**-kolonner.

    Angi for eksempel **ThisItem.Manager.DisplayName** for å vise visningsnavn fra en **Person- eller gruppe**-kolonne ved navn **Leder**.

    Du kan også vise forskjellig informasjon om brukere, for eksempel e-postadresser eller jobbtitler. Hvis du vil vise en fullstendig liste over alternativer, kan du angi **ThisItem. [ ColumnName].** (med etterfølgende punktum).

    **Merk:** For en **CreatedBy**-kolonne angir du **ThisItem.Author.DisplayName** for å vise visningsnavnene på brukerne som opprettet elementer i listen. For en **ModifiedBy**-kolonne angir du **ThisItem.Editor.DisplayName** for å vise visningsnavnene på brukerne som endret elementer i listen.

* For en **Administrerte metadata**-liste angir du **ThisItem.[ColumnName].Label** for å vise data i denne kolonnen.

    For eksempel angir du **ThisItem.Languages.Label** hvis du har en **Administrerte metadata**-kolonne kalt **Språk**.

## <a name="next-steps"></a>Neste trinn
* Finn ut hvordan du kan [vise data fra en datakilde](../add-gallery.md).
* Finn ut hvordan du kan [vise detaljer og opprette eller oppdatere poster](../add-form.md).
* Se andre typer [datakilder](../connections-list.md) som du kan koble til.
