---
title: Oversikt over SharePoint-tilkoblingen | Microsoft Docs
description: Se de tilgjengelige funksjonene, svarene og eksemplene for SharePoint
author: NickWaggoner
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 07/12/2017
ms.author: niwaggon
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 0fbc97e6c2663210bea79cc7236ce784110a4950
ms.sourcegitcommit: c6ad6ba7814c5e7b12c3b7b76bf2e7718bf41b8c
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/19/2019
ms.locfileid: "58198617"
---
# <a name="connect-to-sharepoint-from-a-canvas-app"></a>Koble til SharePoint fra en lerretsapp

![SharePoint](./media/connection-sharepoint-online/sharepointicon.png)

Koble til et SharePoint-område til å generere en app automatisk fra en egendefinert liste, eller Opprett en tilkobling før du legger til data i en eksisterende app eller bygge en app fra grunnen av.

- Vise data fra en egendefinert liste i en SharePoint Online-området eller et lokalt område.
- Vis bilder og spill av video- eller filer i et bibliotek (bare SharePoint Online).

## <a name="generate-an-app"></a>Å generere en app

Hvis du vil behandle data i en egendefinert liste, kan PowerApps [generere en app med tre skjermer for deg automatisk](../app-from-sharepoint.md). Brukere kan bla gjennom listen på den første skjermen, vise detaljer for et element i den andre skjermen, og opprette eller oppdatere elementer i det tredje skjermbildet.

> [!NOTE]
> Hvis SharePoint-listen inneholder en **valg**, **oppslag**, eller **Person eller gruppe** kolonne, kan du se [Vis data i et galleri](connection-sharepoint-online.md#show-data-in-a-gallery) senere i dette emnet.

## <a name="create-a-connection"></a>Å opprette en kobling

1. [Logg deg på PowerApps](http://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc), og velg **Data** > **tilkoblinger** i navigasjonsruten til venstre, og velg deretter **ny tilkobling** nær den øverst til venstre.

    > [!div class="mx-imgBorder"]
    > ![Velg Data > tilkoblinger i navigasjonsfeltet til venstre, og velg deretter ny tilkobling nær hjørnet øverst til venstre.](./media/connection-sharepoint-online/new-connection.png)

1. I søkeboksen nær hjørnet øverst til høyre, Skriv eller Lim inn **SharePoint**, og velg deretter **SharePoint**.

    > [!div class="mx-imgBorder"]
    > ![I søkeboksen nær hjørnet øverst til høyre, Skriv eller Lim inn SharePoint, og velg deretter SharePoint.](./media/connection-sharepoint-online/select-sharepoint.png)

1. Følg ett av disse settene av trinnene:

    - Hvis du vil koble til SharePoint Online, velg **koble til direkte (skytjenester)**, og velg **Opprett**, og angi deretter legitimasjonen (Hvis du blir bedt om det).

        > [!div class="mx-imgBorder"]
        > ![For å koble til SharePoint Online, velger du koble til direkte (skytjenester)](./media/connection-sharepoint-online/select-online.png)

        Tilkoblingen er opprettet, og du kan legge til en data i en eksisterende app eller bygge en app fra grunnen av.

    - Hvis du vil koble til et lokalt område, velg **koble til med lokal datagateway**.

        > [!div class="mx-imgBorder"]
        > ![Hvis du vil koble til lokalt område, velg ** koble til med lokal datagateway)](./media/connection-sharepoint-online/select-onprem.png)

        Angi **Windows** som godkjenningstype, og deretter angir du legitimasjonen din. (Hvis legitimasjonen din inkluderer et domenenavn, angir du det som *domene/alias*.)

        > [!div class="mx-imgBorder"]
        > ![Angi legitimasjon](./media/connection-sharepoint-online/specify-creds.png)

        Under **Velg en gateway**, velg gatewayen du vil bruke, og velg deretter **Opprett**.

        > [!NOTE]
        > Hvis du ikke har en lokal datagateway installert, [installere en](../gateway-reference.md), og velg deretter ikonet for å oppdatere listen over gatewayer.

        > [!div class="mx-imgBorder"]
        > ![Velg gateway](./media/connection-sharepoint-online/choose-gateway.png)

        Tilkoblingen er opprettet, og du kan legge til en data i en eksisterende app eller bygge en app fra grunnen av.

## <a name="add-data-to-an-existing-app"></a>Legge til data i en eksisterende app

1. I PowerApps Studio, åpne appen som du vil oppdatere, velg den **Vis** fanen, og velg deretter **datakilder**.

    > [!div class="mx-imgBorder"]
    > ![På Vis-kategorien, og velg deretter datakilder](./media/connection-sharepoint-online/view-data-sources.png)

1. I den **Data** ruten velger **Legg til datakilde** > **SharePoint**.

1. Under **koble til et SharePoint-område**, velg en oppføring i den **nylig brukte områder** listen (eller Skriv eller Lim inn URL-adressen for området du vil bruke), og velg deretter **koble til**.

    > [!div class="mx-imgBorder"]
    > ![Velg område](./media/connection-sharepoint-online/select-sp-site.png)

1. Under **velger du en liste over**, Merk av for **dokumenter** eller én eller flere lister du vil bruke, og velg deretter **koble til**:

    > [!div class="mx-imgBorder"]
    > ![Under Velg en liste, velg avmerkingsboksen for dokumenter eller én eller flere lister du vil bruke, og velg deretter koble til](./media/connection-sharepoint-online/select-sp-tables.png)

    Ikke alle typer lister vises som standard. PowerApps støtter egendefinerte lister, ikke malbaserte lister.  Hvis navnet på listen du vil bruke ikke vises, kan du bla til bunnen og deretter skrive inn listenavnet i boksen som inneholder **Skriv inn navn på egendefinert liste**.

    > [!div class="mx-imgBorder"]
    > ![Skriv inn navnet på listen i boksen som inneholder Skriv inn et navn på egendefinert liste.](./media/connection-sharepoint-online/custom-list.png)

    Datakilden eller kilder er lagt til i appen.

## <a name="build-your-own-app-from-scratch"></a>Bygge din egen app fra grunnen av

Bruke begrepene i [opprette en app fra grunnen av](../get-started-create-from-blank.md) til SharePoint i stedet for Excel.

## <a name="show-list-columns-in-a-gallery"></a>Vis listen over kolonner i et galleri

Hvis listen over egendefinerte inneholder noen av disse typene kolonner, kan du vise dataene i en **galleriet** kontrollen ved hjelp av formellinjen for å angi den **tekst** -egenskapen for én eller flere **etikett** Kontroller i galleriet:

- Angi **ThisItem.[ColumnName].Value** for å vise data for **Valg-** eller **Oppslag-** kolonner.

    Angi for eksempel **ThisItem.Location.Value** hvis du har en **Valg**-kolonne ved navn **Lokasjon**, og angi **ThisItem.PostalCode.Value** hvis du har en **Oppslag**-kolonne ved navn **PostalCode**.

- Angi **ThisItem.[ColumnName].DisplayName** for å vise visningsnavnet for brukeren eller gruppen for **Person- eller gruppe**-kolonner.

    Angi for eksempel **ThisItem.Manager.DisplayName** for å vise visningsnavn fra en **Person- eller gruppe**-kolonne ved navn **Leder**.

    Du kan også vise forskjellig informasjon om brukere, for eksempel e-postadresser eller jobbtitler. Hvis du vil vise en fullstendig liste over alternativer, kan du angi **ThisItem.[ColumnName].** (med etterfølgende punktum).

    > [!NOTE]
    > For en **CreatedBy** kolonnen, angi **ThisItem.Author.DisplayName** til å vise visningsnavnene på brukerne som opprettet elementer i listen. For en **ModifiedBy**-kolonne angir du **ThisItem.Editor.DisplayName** for å vise visningsnavnene på brukerne som endret elementer i listen.

- For en **Administrerte metadata**-kolonne angir du **ThisItem.[ColumnName].Label** for å vise data i denne kolonnen.

    For eksempel angir du **ThisItem.Languages.Label** hvis du har en **Administrerte metadata**-kolonne kalt **Språk**.

## <a name="show-data-from-a-library"></a>Vise data fra et bibliotek

Hvis du har flere bilder i en SharePoint-bibliotek, kan du legge til en **rullegardin** kontrollen til appen din slik at brukere kan angi hvilken avbildning som skal vise. Du kan også bruke de samme prinsippene på andre kontroller, som **galleriet** kontroller og andre typer data, for eksempel videoer.

1. Hvis du ikke har allerede, [Opprett en tilkobling](#create-a-connection), og deretter [legge til data i en eksisterende app](#add-data-to-an-existing-app).

1. Legg til en **rullegardin** kontroll, og gi den navnet **ImageList**.

1. Angi den **elementer** -egenskapen for **ImageList** til **dokumenter**.

1. På den **Egenskaper** fanen i den høyre ruten, åpne det **verdien** listen, og velg deretter **navnet**.

    Filnavn på bildene i biblioteket ditt vises i **ImageList**.

    > [!div class="mx-imgBorder"]
    > ![Liste over bilder](./media/connection-sharepoint-online/dropdown-items.png)

1. Legg til en **bilde** kontroll, og angi dens **bilde** egenskapen til dette uttrykket:

    `ImageList.Selected.'Link to item'`

1. Trykk på F5, og velg deretter en annen verdi i **ImageList**.

    Bildet du har angitt, vises.

    > [!div class="mx-imgBorder"]
    > ![Eksempel på bilde](./media/connection-sharepoint-online/golden-honey.png)

Du kan [Last ned en eksempelapp](https://pwrappssamples.blob.core.windows.net/samples/spdoclib_blogapp.msapp) som demonstrerer en mer kompleks tilnærming til å vise data fra et SharePoint-bibliotek.

1. Når du laster ned appen, åpner du [PowerApps Studio](https://us.create.powerapps.com/studio/#), og velg **åpne** i navigasjonsruten til venstre, og velg deretter **Bla gjennom**.
1. I den **åpne** dialogboksen, finne og åpne filen du lastet ned, og deretter legge til et SharePoint-bibliotek som en datakilde ved å følge de to første prosedyrene i dette emnet.

> [!NOTE]
> Denne appen viser som standard [delegeringsadvarsler](../delegation-overview.md), men kan du ignorere dem hvis biblioteket inneholder færre enn 500 elementer.

I denne appen for én skjerm viser listen i hjørnet nederst til venstre alle filer i biblioteket.

- Du kan søke etter en fil ved å skrive eller lime inn én eller flere tegn i søkeboksen nær toppen.
- Hvis biblioteket inneholder mapper, kan du filtrere listen over filer ved å velge et filterikon i listen over mapper like under tittellinjen.

Når du finner filen du vil bruke, velger du den for å vise den i den **Video**, **bilde**, eller **lyd** kontrollen langs høyre side.

> [!div class="mx-imgBorder"]
> ![Eksempel på bilde](./media/connection-sharepoint-online/library-app.png)

## <a name="known-issues"></a>Kjente problemer

### <a name="lists"></a>Lister

PowerApps kan lese kolonnenavn som inneholder mellomrom, men mellomrommene erstattes med den heksadesimale escape-koden **"\_x0020\_"**. **«Kolonnenavn»** i SharePoint vil for eksempel vises som **«Column_x0020_Name»** i PowerApps når de vises i dataoppsettet eller brukes i en formel.

Ikke alle typer kolonner som støttes, og ikke alle typer kolonner støtter alle typer kort.

| Kolonnetype | Kundestøtte | Standardkort |
| --- | --- | --- |
| Enkeltlinje med tekst |ja |Å vise tekst |
| Flere linjer med tekst |ja |Å vise tekst |
| Valg |ja |Vis oppslag<br>Rediger oppslag<br>Vis flervalg<br>Rediger flervalg |
| Tall |ja |Vis prosentandel<br>Vis vurdering<br>Å vise tekst |
| Valuta |ja |Vis prosentandel<br>Vis vurdering<br>Vis tekst |
| Dato og klokkeslett |ja |Å vise tekst |
| Oppslag |ja |Vis oppslag<br>Rediger oppslag<br>Vis flervalg<br>Rediger flervalg |
| Boolsk (Ja/Nei) |ja |Å vise tekst<br>Aktiver/deaktiver visning |
| Person eller gruppe |ja |Vis oppslag<br>Rediger oppslag<br>Vis flervalg<br>Rediger flervalg |
| Hyperkobling |ja |Vis nettadresse<br>Vis tekst |
| Bilde |Ja (skrivebeskyttet) |Vis bilde<br>Vis tekst |
| Vedlegg |Ja (skrivebeskyttet) |Vis vedlegg|
| Beregnet |Ja (skrivebeskyttet) | |
| Resultat av oppgaven |nei | |
| Eksterne data |nei | |
| Administrerte metadata |Ja (skrivebeskyttet) | |
| Vurdering |nei | |

### <a name="libraries"></a>Biblioteker

- Du kan ikke laste opp filer fra PowerApps til et bibliotek.
- Du kan ikke vise PDF-filer fra et bibliotek i en kontroll for PDF-visningsprogram.
- PowerApps Mobile støtter ikke den **Last ned** funksjonen.
- Hvis brukerne vil kjøre appen i PowerApps Mobil- eller Windows 10-appen, kan du bruke den **Start** funksjonen til å vise biblioteket innhold i et galleri.

## <a name="next-steps"></a>Neste trinn

- Finn ut hvordan du kan [vise data fra en datakilde](../add-gallery.md).
- Finn ut hvordan du kan [vise detaljer og opprette eller oppdatere poster](../add-form.md).
- Se andre typer [datakilder](../connections-list.md) som du kan koble til.
