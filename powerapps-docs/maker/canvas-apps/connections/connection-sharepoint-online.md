---
title: Oversikt over SharePoint-tilkoblingen | Microsoft Docs
description: Se de tilgjengelige funksjonene, svarene og eksemplene for SharePoint
author: sarafankit
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 07/12/2017
ms.author: ankitsar
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 0a13d2602f06f436d4b805669b004f1ee63daeb9
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/24/2018
ms.locfileid: "42836739"
---
# <a name="connect-to-sharepoint-from-powerapps"></a>Koble til SharePoint fra PowerApps
![SharePoint](./media/connection-sharepoint-online/sharepointicon.png)

Koble til et SharePoint-område for å generere en app automatisk fra en liste, bygge en app fra grunnen av eller oppdatere en eksisterende app.

## <a name="known-issues"></a>Kjente problemer
Du kan legge til data fra en egendefinert liste, men ikke fra et bibliotek. I tillegg støttes ikke alle typer kolonner, og ikke alle typer kolonner støtter alle typer kort.

| Kolonnetype | Støtte | Standardkort |
| --- | --- | --- |
| Enkeltlinje med tekst |Ja |Å vise tekst |
| Flere linjer med tekst |Ja |Å vise tekst |
| Valg |Ja |Vis oppslag<br>Rediger oppslag<br>Vis flervalg<br>Rediger flervalg |
| Tall |Ja |Vis prosentandel<br>Vis vurdering<br>Å vise tekst |
| Valuta |Ja |Vis prosentandel<br>Vis vurdering<br>Vis tekst |
| Dato og klokkeslett |Ja |Å vise tekst |
| Oppslag |Ja |Vis oppslag<br>Rediger oppslag<br>Vis flervalg<br>Rediger flervalg |
| Boolsk (Ja/Nei) |Ja |Å vise tekst<br>Aktiver/deaktiver visning |
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
1. [Registrer deg](../../signup-for-powerapps.md) for PowerApps.

1. [Logg deg på](http://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) PowerApps ved å angi samme legitimasjon som du brukte til å registrere deg.

1. Nær venstre kant velger du **Apper**, og deretter velger du **Opprett en app** i banneret.

## <a name="create-an-app"></a>Å opprette en app
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

    Ikke alle typer lister vises som standard. PowerApps støtter egendefinerte lister, ikke malbaserte lister.  Hvis navnet på listen du vil bruke ikke vises, kan du bla til bunnen og deretter skrive inn listenavnet i boksen som inneholder **Skriv inn navn på egendefinert liste**.

    ![Egendefinert liste i SharePoint](./media/connection-sharepoint-online/custom-list.png)

    Datakildene blir lagt til appen.

    ![Listen over datakilder som er lagt til appen](./media/connection-sharepoint-online/data-sources-list.png)

## <a name="show-data-in-a-gallery"></a>Vise data i et galleri
Bruk formellinjen for å angi **Tekst**-egenskapen for én eller flere **Etikett**-kontroller i galleriet for å vise data fra noen av disse kolonnetypene i et galleri:

* Angi **ThisItem.[ColumnName].Value** for å vise data for **Valg-** eller **Oppslag-** kolonner.

    Angi for eksempel **ThisItem.Location.Value** hvis du har en **Valg**-kolonne ved navn **Lokasjon**, og angi **ThisItem.PostalCode.Value** hvis du har en **Oppslag**-kolonne ved navn **PostalCode**.

* Angi **ThisItem.[ColumnName].DisplayName** for å vise visningsnavnet for brukeren eller gruppen for **Person- eller gruppe**-kolonner.

    Angi for eksempel **ThisItem.Manager.DisplayName** for å vise visningsnavn fra en **Person- eller gruppe**-kolonne ved navn **Leder**.

    Du kan også vise forskjellig informasjon om brukere, for eksempel e-postadresser eller jobbtitler. Hvis du vil vise en fullstendig liste over alternativer, kan du angi **ThisItem.[ColumnName].** (med etterfølgende punktum).

    **Merk:** For en **CreatedBy**-kolonne angir du **ThisItem.Author.DisplayName** for å vise visningsnavnene på brukerne som opprettet elementer i listen. For en **ModifiedBy**-kolonne angir du **ThisItem.Editor.DisplayName** for å vise visningsnavnene på brukerne som endret elementer i listen.

* For en **Administrerte metadata**-kolonne angir du **ThisItem.[ColumnName].Label** for å vise data i denne kolonnen.

    For eksempel angir du **ThisItem.Languages.Label** hvis du har en **Administrerte metadata**-kolonne kalt **Språk**.

## <a name="next-steps"></a>Neste trinn
* Finn ut hvordan du kan [vise data fra en datakilde](../add-gallery.md).
* Finn ut hvordan du kan [vise detaljer og opprette eller oppdatere poster](../add-form.md).
* Se andre typer [datakilder](../connections-list.md) som du kan koble til.
