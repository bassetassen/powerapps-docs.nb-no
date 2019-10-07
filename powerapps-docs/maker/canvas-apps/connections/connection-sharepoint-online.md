---
title: Oversikt over SharePoint-tilkoblingen | Microsoft Docs
description: Se tilgjengelige funksjoner, svar og eksempler for SharePoint.
author: NickWaggoner
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 04/03/2019
ms.author: niwaggon
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: ae82166b9cc21de1e25f99f7606ce7b95b2152b9
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71993957"
---
# <a name="connect-to-sharepoint-from-a-canvas-app"></a>Koble til SharePoint fra en lerret-app

![Services](./media/connection-sharepoint-online/sharepointicon.png)

Koble til et SharePoint-område for å generere en app automatisk fra en egen definert liste, eller Opprett en tilkobling før du legger til data i en eksisterende app eller bygger en app fra grunnen av.

Avhengig av hvor dataene befinner seg, kan du ta én av eller begge disse metodene:

- Vis data fra en egen definert liste på et SharePoint Online-område eller et lokalt område.
- Vis bilder og spill av video-eller lyd filer i et bibliotek (bare SharePoint Online).

## <a name="generate-an-app"></a>Å generere en app

Hvis du vil administrere data i en egen definert liste, kan PowerApps [generere en tre skjerms app automatisk](../app-from-sharepoint.md). Brukere kan bla gjennom listen på den første skjermen, vise detaljer om et element på den andre skjermen, og opprette eller oppdatere elementer på den tredje skjermen.

> [!NOTE]
> Hvis SharePoint-listen inneholder en **valg**-, **oppslags**-eller en/ **gruppe** -kolonne, kan du se [Vis data i et galleri](connection-sharepoint-online.md#show-list-columns-in-a-gallery) senere i dette emnet.

## <a name="create-a-connection"></a>Å opprette en kobling

1. [Logg deg på powerapps](http://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc), velg **data** > -**tilkoblinger** i navigasjons feltet til venstre, og velg deretter **ny tilkobling** nær hjørnet øverst til venstre.

    > [!div class="mx-imgBorder"]
    > ![Select data > tilkoblinger i det venstre navigasjons feltet, og velg deretter ny tilkobling nær hjørnet øverst til venstre. ](./media/connection-sharepoint-online/new-connection.png)

1. Skriv eller lim inn **SharePoint**i søke boksen nær hjørnet øverst til høyre, og velg deretter **SharePoint**.

    > [!div class="mx-imgBorder"]
    > @no__t – 0In søke boksen nær hjørnet øverst til høyre, skriv eller lim inn SharePoint, og velg deretter SharePoint. ](./media/connection-sharepoint-online/select-sharepoint.png)

1. Utfør ett av disse trinnene:

    - Hvis du vil koble til SharePoint Online, velger du **Koble til direkte (Sky tjenester)** , velg **Opprett**, og angi deretter legitimasjon (Hvis du blir bedt om det).

        > [!div class="mx-imgBorder"]
        > ![To koble til SharePoint Online, Velg koble til direkte (Sky tjenester) ](./media/connection-sharepoint-online/select-online.png)

        Tilkoblingen opprettes, og du kan legge til en data til en eksisterende app eller bygge en app fra grunnen av.

    - Hvis du vil koble til et lokalt område, velger du **Koble til med lokal datagateway**.

        > [!div class="mx-imgBorder"]
        > ![To koble til lokalt område, velger du * * koble til med lokal datagateway) ](./media/connection-sharepoint-online/select-onprem.png)

        Angi **Windows** som godkjenningstype, og deretter angir du legitimasjonen din. (Hvis legitimasjonen din inkluderer et domenenavn, angir du det som *domene/alias*.)

        > [!div class="mx-imgBorder"]
        > ![Specify legitimasjon @ no__t-1

        Velg gatewayen du vil bruke under **Velg en gateway**, og velg deretter **Opprett**.

        > [!NOTE]
        > Hvis du ikke har en lokal datagateway installert, installerer du [den](../gateway-reference.md), og deretter velger du ikonet for å oppdatere listen over gatewayer.

        > [!div class="mx-imgBorder"]
        > ![Choose gateway @ no__t-1

        Tilkoblingen opprettes, og du kan legge til en data til en eksisterende app eller bygge en app fra grunnen av.

## <a name="add-data-to-an-existing-app"></a>Å legge til data i en eksisterende app

1. Åpne appen du vil oppdatere i PowerApps Studio, velg **Vis** -fanen, og velg deretter **data kilder**.

    > [!div class="mx-imgBorder"]
    > @no__t – 0On Vis-fanen, og velg deretter data kilder @ no__t-1

1. I **data** -ruten velger du **Legg til data kilde** > **SharePoint**.

1. Velg en oppføring i listen over **nylig brukte områder** under **Koble til et SharePoint-område**(eller skriv eller lim inn Netta dressen for området du vil bruke), og velg deretter **Koble til**.

    > [!div class="mx-imgBorder"]
    > ![Select område @ no__t-1

1. Merk av for **dokumenter** eller én eller flere lister du vil bruke under **Velg en liste**, og velg deretter **Koble til**:

    > [!div class="mx-imgBorder"]
    > ![Under Velg en liste, Merk av i avmerkings boksen for dokumenter eller én eller flere lister du vil bruke, og velg deretter koble til @ no__t-1

    Ikke alle typer lister vises som standard. PowerApps støtter egendefinerte lister, ikke malbaserte lister. Hvis navnet på listen du vil bruke, ikke vises, ruller du ned til bunnen, og deretter skriver du inn navnet på listen i boksen som inneholder **angi egen definert tabell navn**.

    > [!div class="mx-imgBorder"]
    > @no__t – 0Type navnet på listen i boksen som inneholder angi et egen definert navn på listen. ](./media/connection-sharepoint-online/custom-list.png)

    Data kilden eller-kildene legges til i appen.

## <a name="build-your-own-app-from-scratch"></a>Å bygge din egen app fra grunnen av

Bruk begrepene i [Opprett en app fra bunnen](../get-started-create-from-blank.md) til SharePoint i stedet for Excel.

## <a name="show-list-columns-in-a-gallery"></a>Vis liste Kol onner i et galleri

Hvis den egen definerte listen inneholder noen av disse Kol onne typene, kan du vise dataene i en **Galleri** -kontroll ved hjelp av formel linjen for å angi **tekst** -egenskapen for én eller flere **etikett** kontroller i galleriet:

- Angi ThisItem for en **valg** -eller **oppslagskolonne** **.** _ColumnName_ **. Verdi** for å vise data i kolonnen.

    Angi for eksempel **ThisItem.Location.Value** hvis du har en **Valg**-kolonne ved navn **Lokasjon**, og angi **ThisItem.PostalCode.Value** hvis du har en **Oppslag**-kolonne ved navn **PostalCode**.

- For en **person-eller gruppe** -kolonne angir du **ThisItem.** _ColumnName_ **. DisplayName** for å vise visnings navnet for brukeren eller gruppen.

    Angi for eksempel **ThisItem.Manager.DisplayName** for å vise visningsnavn fra en **Person- eller gruppe**-kolonne ved navn **Leder**.

    Du kan også vise forskjellig informasjon om brukere, for eksempel e-postadresser eller jobbtitler. Hvis du vil vise en fullstendig liste over alternativer, kan du angi **ThisItem.** _ColumnName_ **.** (inkludert den etterfølgende perioden).

    > [!NOTE]
    > For en **CreatedBy** -kolonne angir du **ThisItem. author. DisplayName** for å vise visnings navnene på brukerne som opprettet elementer i listen. For en **ModifiedBy**-kolonne angir du **ThisItem.Editor.DisplayName** for å vise visningsnavnene på brukerne som endret elementer i listen.

- Angi ThisItem for en kolonne for **forvaltede metadata** **.** _ColumnName_ **. Etikett** for å vise data i kolonnen.

    For eksempel angir du **ThisItem.Languages.Label** hvis du har en **Administrerte metadata**-kolonne kalt **Språk**.

## <a name="show-data-from-a-library"></a>Vis data fra et bibliotek

Hvis du har flere bilder i et SharePoint-bibliotek, kan du legge til en **rulle gardin** -kontroll i appen, slik at brukerne kan angi hvilket bilde som skal vises. Du kan også bruke de samme prinsippene på andre kontroller, for eksempel **Galleri** kontroller og andre typer data, for eksempel videoer.

1. Hvis du ikke allerede har gjort det, kan du [opprette en tilkobling](#create-a-connection)og deretter [legge til data i en eksisterende app](#add-data-to-an-existing-app).

1. Legg til en **rulle gardin** -kontroll, og gi den navnet **ImageList**.

1. Angi **elementer** -egenskapen for **ImageList** til **dokumenter**.

1. Åpne **verdi** listen på **Egenskaper** -fanen i ruten til høyre, og velg deretter **navn**.

    Fil navnene for bildene i biblioteket vises i **ImageList**.

    > [!div class="mx-imgBorder"]
    > @no__t – 0List av bilder @ no__t-1

1. Legg til en **bilde** -kontroll, og angi **bilde** -egenskapen til dette uttrykket:

    `ImageList.Selected.'Link to item'`

1. Trykk på F5, og velg deretter en annen verdi i **ImageList**.

    Bildet du har angitt, vises.

    > [!div class="mx-imgBorder"]
    > @no__t 0Sample-bilde @ no__t-1

Du kan [laste ned en eksempel-app](https://pwrappssamples.blob.core.windows.net/samples/spdoclib_blogapp.msapp) som demonstrerer en mer komplisert tilnærming til visning av data fra et SharePoint-bibliotek.

1. Når du har lastet ned appen, åpner du [PowerApps Studio](https://us.create.powerapps.com/studio/#), velger **Åpne** i det venstre navigasjons feltet, og deretter velger du **Bla gjennom**.
1. Finn og åpne filen du lastet ned i dialog boksen **Åpne** , og legg deretter til et SharePoint-bibliotek som en data kilde ved å følge de to første prosedyrene i dette emnet.

> [!NOTE]
> Som standard viser denne appen [delegerings advarsler](../delegation-overview.md), men du kan ignorere dem Hvis biblioteket inneholder færre enn 500 elementer.

I denne ene stående appen viser listen nederst i venstre hjørne alle filene i biblioteket.

- Du kan søke etter en fil ved å skrive eller lime inn ett eller flere tegn i søke boksen nær toppen.
- Hvis biblioteket inneholder mapper, kan du filtrere listen over filer ved å velge et filter ikon i listen over mapper like under tittel linjen.

Når du finner filen du ønsker, kan du velge den for å vise den i **video**-, **bilde**-eller **lyd** -kontrollen langs høyre side.

> [!div class="mx-imgBorder"]
> @no__t 0Sample-bilde @ no__t-1

## <a name="known-issues"></a>Kjente problemer

### <a name="lists"></a>Lister

PowerApps kan lese Kol onne navn som inneholder mellomrom, men mellomrommene erstattes av den heksadesimale Escape **-koden \_x0020 @ no__t-2**. **«Kolonnenavn»** i SharePoint vil for eksempel vises som **«Column_x0020_Name»** i PowerApps når de vises i dataoppsettet eller brukes i en formel.

Ikke alle typer kolonner støttes, og ikke alle typer kolonner støtter alle typer kort.

| Kolonnetype | Kundestøtte | Standardkort |
| --- | --- | --- |
| Enkeltlinje med tekst |ja |Å vise tekst |
| Flere linjer med tekst |ja |Å vise tekst |
| Valg |ja |Vis oppslag<br>Rediger oppslag<br>Vis flervalg<br>Rediger flervalg |
| Tall |ja |Vis prosentandel<br>Vis vurdering<br>Å vise tekst |
| Trianguleringsvalutaen |ja |Vis prosentandel<br>Vis vurdering<br>Vis tekst |
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
- Du kan ikke vise PDF-filer fra et bibliotek i en PDF-visnings kontroll.
- PowerApps Mobile støtter ikke **Download** -funksjonen.
- Hvis brukerne kjører appen i PowerApps-mobil eller Windows 10-appen, bruker du **Start** -funksjonen til å vise bibliotek innhold i et galleri.

## <a name="next-steps"></a>Neste trinn

- Finn ut hvordan du kan [vise data fra en datakilde](../add-gallery.md).
- Finn ut hvordan du kan [vise detaljer og opprette eller oppdatere poster](../add-form.md).
- Se andre typer [datakilder](../connections-list.md) som du kan koble til.
