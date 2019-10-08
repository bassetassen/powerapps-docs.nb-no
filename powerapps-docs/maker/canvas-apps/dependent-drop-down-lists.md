---
title: Opprett en avhengig rulle gardin liste i en lerret-app | Microsoft Docs
description: Opprett en rulle gardin liste i PowerApps som filtrerer en annen rulle gardin liste i en lerret-app.
author: emcoope-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 04/04/2019
ms.author: emcoope
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 57abde44541a2a1e40e3a8ffc55a89e37a8c6478
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71985765"
ms.PowerAppsDecimalTransform: true
---
# <a name="create-dependent-drop-down-lists-in-a-canvas-app"></a>Opprett en avhengig rulle gardin liste i en lerret-app

Når du oppretter avhengige (eller gjennom gripende) lister, velger brukerne et alternativ i en liste for å filtrere alternativer i en annen liste. Mange organisasjoner oppretter avhengige lister for å hjelpe brukere med å fylle ut skjemaer mer effektivt. Brukere kan for eksempel velge et land eller et område for å filtrere en liste over byer, eller brukerne kan velge en kategori for å vise bare kodene i denne kategorien.

Som en anbefalt Fremgangs måte kan du opprette en data kilde for verdiene i listene «overordnet» og «underordnet» (for eksempel land/områder og byer) som er atskilt fra data kilden som brukere oppdaterer ved hjelp av appen. Hvis du tar denne tilnærmingen, kan du bruke samme overordnede og underordnede data i mer enn én app, og du kan oppdatere dataene uten å publisere appen eller appene som bruker dem. Du kan oppnå samme resultat ved å bruke en samling eller statiske data, men det anbefales ikke for scenarioer i bedrifter.

For scenarioet i dette emnet, kan du lagre ansatte ved å sende problemer til en **hendelses** liste gjennom et skjema. Ansatte angir ikke bare plasseringen av lageret der hendelsen forekom, men også avdelingen i den plasseringen. Ikke alle lokasjoner har de samme avdelingene, så en **lokasjons** liste sikrer at ansatte ikke kan angi en avdeling for en plassering som ikke har den avdelingen.

Dette emnet bruker Microsoft SharePoint-lister som data kilder, men alle tabell data kilder fungerer på samme måte.

## <a name="create-data-sources"></a>Opprett data kilder

En **lokasjons** liste viser avdelingene på hver plassering.

| Location | Avdeling |
|----------------|------------------|
| Eganville      | Bakeri           |
| Eganville      | Deli             |
| Eganville      | Får          |
| Renfrew        | Bakeri           |
| Renfrew        | Deli             |
| Renfrew        | Får          |
| Renfrew        | Pharmacy         |
| Renfrew        | Blomster           |
| Pembroke       | Bakeri           |
| Pembroke       | Deli             |
| Pembroke       | Får          |
| Pembroke       | Blomster           |

En **hendelses** liste viser kontakt informasjon og informasjon om hver hendelse. Opprett dato Kol onnen som en **dato** -kolonne, men Opprett de andre Kol Onnene som **én linje med tekst** -kolonner for å forenkle konfigurasjonen og unngå [delegerings](./delegation-overview.md) advarsler i Microsoft PowerApps.

| For navn | Etter navn | Telefon nummer     | Location | Avdeling | Beskrivelse       | Date      |
|------------|-----------|------------------|----------------|------------|-------------------------|-----------|
| Tonya       | Cortez   | (206) 555-1022 | Eganville      | Får    | Det har oppstått et problem med...   | 2/12/2019 |
| Moses     | Laflamme     | (425) 555-1044 | Renfrew        | Blomster     | Det oppstod et problem... | 2/13/2019 |

Som standard inkluderer egen definerte SharePoint-lister en **Tittel** -kolonne som du ikke kan gi nytt navn til eller fjerne, og den må inneholde data før du kan lagre et element i listen. Slik konfigurerer du kolonnen slik at den ikke krever data:

1. Velg tann hjul ikonet nær hjørnet øverst til høyre, og velg deretter **liste innstillinger**.
1. Velg **Tittel** i listen over kolonner på **Innstillinger** -siden.
1. Velg **Nei**under **Krev at denne kolonnen inneholder informasjon**.

Når endringen er endret, kan du ignorere **Tittel** -kolonnen, eller du kan [fjerne den](https://support.office.com/article/edit-a-list-column-in-sharepoint-online-77130c2e-76d1-4f80-af8b-4c6f47b264b8) fra standard visningen hvis minst én annen kolonne vises.

## <a name="open-the-form"></a>Åpne skjemaet

1. Åpne **hendelses** listen, og velg deretter **powerapps**@no__t – 2**Tilpass skjemaer**.

    > [!div class="mx-imgBorder"]
    > ![Åpne hendelses listen, og velg deretter powerapps > tilpasse skjemaer.](./media/dependent-drop-down-lists/open-form.png "Åpne hendelses listen, og velg deretter powerapps > tilpasse skjemaer.")

    En nett leser kategori åpnes med standard skjemaet i PowerApps Studio.

1. valg fritt Hold pekeren over **Tittel** -feltet i **felt** -ruten, Velg ellipsen (...) som vises, og velg deretter **Fjern**.

    Hvis du har lukket **felt** -ruten, kan du åpne den igjen ved å velge **SharePointForm1** i det venstre navigasjons feltet, og deretter velge **Rediger felt** på **Egenskaper** -fanen i ruten til høyre.

1. valg fritt Gjenta det forrige trinnet for å fjerne **vedlegg** -feltet fra-skjemaet.

    Skjemaet vises med bare feltene du har lagt til.

    > [!div class="mx-imgBorder"]
    > ![Form uten tittel-og Vedleggs felt @ no__t-1

## <a name="replace-the-controls"></a>Erstatt kontrollene

1. Velg pilen ved siden av **plassering**i **felt** -ruten.

    Hvis du har lukket **felt** -ruten, kan du åpne den igjen ved å velge **SharePointForm1** i det venstre navigasjons feltet, og deretter velge **Rediger felt** på **Egenskaper** -fanen i ruten til høyre.

1. Åpne **kontroll type** -listen, og velg deretter **tillatte verdier**.

    > [!div class="mx-imgBorder"]
    > ![Allowed-verdier @ no__t-1

    Inn data mekanismen endres til en **rulle** gardin-kontroll.

1. Gjenta disse trinnene for **avdelings** kortet.

## <a name="add-the-locations-list"></a>Legg til listen over plasseringer

1. Velg **vis** > **data kilder** > **Legg til data kilde**.

1. Velg eller Opprett en SharePoint-tilkobling, og angi deretter området som inneholder listen over **plasseringer** .

1. Merk av i avmerkings boksen for listen, og velg deretter **Koble til**.

    > [!div class="mx-imgBorder"]
    > @no__t 0Data-rute @ no__t-1

    Listen over tilkoblinger viser **hendelses** listen, som skjemaet er basert på, og **lokasjoner** -listen, som vil identifisere steder og avdelinger i skjemaet.

    > [!div class="mx-imgBorder"]
    > 0SharePoint data kilder @ no__t-1 @no__t

## <a name="unlock-the-cards"></a>Lås opp kortene

1. Velg **lokasjons** kortet, velg **Avansert** -fanen i ruten til høyre, og velg deretter **Lås opp for å endre egenskaper**.

1. Gjenta det forrige trinnet for **avdelings** kortet.

## <a name="rename-the-controls"></a>Gi nytt navn til kontrollene

Hvis du gir nytt navn til kontrollene, kan du identifisere dem enklere, og eksemplene er enklere å følge. Hvis du vil finne andre anbefalte Fremgangs måter, kan du se gjennom [kode standarder og retnings linjer](https://aka.ms/powerappscanvasguidelines).

1. Velg **rulle** gardin-kontrollen på **Lokasjon** -kortet.

1. Nesten øverst i ruten til høyre, gi nytt navn til den valgte kontrollen ved å skrive eller lime inn **ddLocation**.

    > [!div class="mx-imgBorder"]
    > @no__t – 0Rename en kontroll @ no__t-1

1. Gjenta de forrige to trinnene i **avdeling** -kortet for å gi nytt navn til **rulle gardin** -kontrollen til **ddDepartment**.

## <a name="configure-the-locations"></a>Konfigurer stedene

1. Angi **elementer** -egenskapen for **ddlocation** til denne formelen:

    `Distinct(Locations; Location)`

1. valg fritt Mens du holder nede Alt-tasten, åpner du **ddLocation**og bekrefter at listen viser de tre stedene.

## <a name="configure-the-departments"></a>Konfigurere avdelingene

1. Velg **ddDepartment**, og velg deretter i **Egenskaper** -fanen i ruten til høyre, **avhengig av.**

1. Sørg for at **ddLocation** vises i den øvre **listen, under** **overordnet kontroll**, i den nederste listen.

    > [!NOTE]
    > Hvis du ikke vil ha treff på en streng, men på den faktiske ID-en for raden med data, velger du **ID** i stedet for **resultat**.

1. Velg **plasseringer** i den øvre listen under **samsvarende felt**, velg **plassering** i den nedre listen, og velg deretter **Bruk**.

    > [!div class="mx-imgBorder"]
    > ![Depends på kobling @ no__t-1

    **Items** -egenskapen for **ddDepartment** er satt til denne formelen:

    `Filter(Locations; Location = ddLocation.Selected.Result)`

    Denne formelen filtrerer elementene i **ddDepartment** basert på hva brukeren velger i **ddLocation**. En slik konfigurasjon sikrer at den underordnede listen over avdelinger gjenspeiler dataene for den overordnede plasseringen, da **lokasjoner** -listen i SharePoint angir.

1. Åpne listen ved siden av **verdi**i **Egenskaper** -fanen i ruten til høyre, og velg deretter **avdeling**.

    Dette trinnet angir visnings teksten til alternativene fra **avdeling** -kolonnen i **lokasjoner** -listen i SharePoint.

    > [!div class="mx-imgBorder"]
    > ![Department-verdi @ no__t-1

## <a name="test-the-form"></a>Test skjemaet

Mens du holder nede Alt-tasten, åpner du listen over plasseringer, velger en, åpner listen over avdelinger, og deretter velger du en.

Listene over lokasjoner og avdelinger gjenspeiler informasjonen i **lokasjoner** -listen i SharePoint.

> [!div class="mx-imgBorder"]
> ![Open listen over plasseringer, endre utvalget fra Renfrew til Pembroke, og åpne deretter listen over avdelinger @ no__t-1

## <a name="save-and-open-the-form-optional"></a>Lagre og åpne skjemaet (valg fritt)

1. Åpne **fil** -menyen, og velg deretter **Lagre** > **Publiser til SharePoint** > **Publiser til SharePoint**.

1. Velg tilbakepilen øverst til venstre, og velg deretter **Tilbake til SharePoint**.

1. Velg **Ny** i kommandolinjen for å åpne det egendefinerte skjemaet.

## <a name="faq"></a>VANLIG

**Jeg kan ikke se noen data: kildene er tomme eller har feil data.**
Bekreft om du viser riktig felt for kontrollen din på én av følgende måter:

- Velg en rulle gardin liste, og velg deretter **verdi** -egenskapen i **Egenskaper** -fanen i ruten til høyre.

    > [!div class="mx-imgBorder"]
    > @no__t – 0Change-rullegardinliste @ no__t-1

- Velg en kombinasjons boks, og kontroller at den primære teksten er feltet som du vil vise.

    > [!div class="mx-imgBorder"]
    > kombinasjons boks for ![Change @ no__t-1

**Den underordnede rulle gardin listen inneholder like elementer.**
Dette symptomet er sannsynligvis på grunn av bruk av en **oppslagskolonne** i SharePoint eller en **valg** funksjon i powerapps. Hvis du vil fjerne dupliseringen, kan du bryte en **DISTINCT** -funksjon på riktig måte som returnerer data. Mer informasjon: [DISTINCT-funksjonen](functions/function-distinct.md).

## <a name="known-limitations"></a>Kjente begrensninger

Denne konfigurasjonen er tilgjengelig på **rulle** gardin-kontroller, samt **kombinasjons boks** -og **liste boks** kontroller som tillater ett valg om gangen. Du kan ikke bruke **avhengig** av konfigurasjonen for noen av disse kontrollene hvis de tillater flere valg. Denne Fremgangs måten anbefales ikke for å arbeide med alternativ sett i Common Data Service.

**Avhengig** av konfigurasjonen støtter ikke statiske data eller samlinger. Hvis du vil konfigurere en avhengig rulle gardin liste med disse kildene, redigerer du uttrykket direkte på formel linjen. I tillegg støtter ikke PowerApps å bruke to valgs felt i SharePoint uten samsvarende tabell med data, og du kan ikke definere **samsvarende felt** i dette bruker grensesnittet.
