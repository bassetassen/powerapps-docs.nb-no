---
title: Opprett en avhengige rullegardinlisten i en lerretsapp | Microsoft Docs
description: I PowerApps, kan du opprette en rullegardinliste som filtrerer en annen rullegardinlisten i en lerretsapp.
author: emcoope-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 02/28/2019
ms.author: emcoope
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: db511edd7e64f4d8ccd27cb59cae9a2c369e1a90
ms.sourcegitcommit: a06e3137e3cb36414f0d61825bbc687487ea6f8c
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/06/2019
ms.locfileid: "57804244"
---
# <a name="create-dependent-drop-down-lists-in-a-canvas-app"></a>Opprett avhengige rullegardinlister i en lerretsapp

Når du oppretter avhengige (eller gjennomgripende) rullegardinlister, Velg brukere et alternativ i en liste til filteralternativer i en annen liste. Mange organisasjoner opprette avhengige lister for å hjelpe brukere med å fylle ut skjemaer mer effektivt. For eksempel brukere kan velge et land eller område til å filtrere en liste over byer, eller brukere kan velge en kategori for å vise bare kodene i denne kategorien.

Som en anbefalt fremgangsmåte, kan du opprette en datakilde for verdiene i den "overordnede" og "underordnet" lister (for eksempel land/områder og byer) som er atskilt fra datakilden som brukere oppdatere ved hjelp av appen. Hvis du skal bruke denne fremgangsmåten, du kan bruke de samme overordnede og underordnede dataene i mer enn én app, og du kan oppdatere dataene uten å publisere appen eller apper som bruker dem på nytt. Du kan gjøre det samme resultatet ved hjelp av en samling eller statiske data, men det er ikke anbefalt for enterprise-scenarier.

For scenariet i dette emnet, kan du lagre ansatte Send problemer til en **hendelser** liste gjennom et skjema. Ansatte angi ikke bare plasseringen av butikk som hendelsen oppstod, men også avdeling i denne plasseringen. Ikke alle lokasjoner som har de samme avdelingene, så en **plasseringer** listen sikrer at ansatte ikke kan angi en avdeling for en plassering som ikke har denne avdelingen.

Dette emnet bruker SharePoint-lister som datakilder, men alle datakilder i tabellform fungerer på samme måte.

## <a name="create-data-sources"></a>Opprette datakilder

A **plasseringer** listen viser avdelinger for hver plassering.

| Location | Avdeling |
|----------------|------------------|
| Eganville      | Bakeren           |
| Eganville      | Deli             |
| Eganville      | Produsere          |
| Renfrew        | Bakeren           |
| Renfrew        | Deli             |
| Renfrew        | Produsere          |
| Renfrew        | Apotek         |
| Renfrew        | Blomstermotiv           |
| Pembroke       | Bakeren           |
| Pembroke       | Deli             |
| Pembroke       | Produsere          |
| Pembroke       | Blomstermotiv           |

En **hendelser** listen viser kontaktinformasjon og informasjon om hver hendelse. Opprette dato-kolonnen som en **dato** kolonne, men opprette de andre kolonnene som **enkelt linje med tekst** kolonner for å forenkle konfigurasjon og unngå [delegering](./delegation-overview.md) advarsler i PowerApps.

| Fornavn | Etternavn | Telefonnummer     | Location | Avdeling | Beskrivelse       | Date      |
|------------|-----------|------------------|----------------|------------|-------------------------|-----------|
| Tonya       | Cortez   | (206) 555 - 1022 | Eganville      | Produsere    | Jeg hadde et problem med...   | 2/12/2019 |
| Moses     | Laflamme     | (425) 555 - 1044 | Renfrew        | Blomstermotiv     | Jeg har oppstått et problem... | 2/13/2019 |

Egendefinerte SharePoint-lister inneholder som standard en **tittel** kolonnen at du kan ikke gi nytt navn til eller fjerne, og den må inneholde data før du kan lagre et element i listen. Å konfigurere kolonnen slik at den ikke krever data:

1. Velg tannhjulikonet nær hjørnet øverst til høyre, og velg deretter **listeinnstillinger**.
1. På den **innstillinger** velger **tittel** i listen over kolonner.
1. Under **krev at denne kolonnen inneholder informasjon**, og velg **Nei**.

Etter denne endringen, kan du ignorere den **tittel** kolonnen, eller du kan [fjerne den](https://support.office.com/article/edit-a-list-column-in-sharepoint-online-77130c2e-76d1-4f80-af8b-4c6f47b264b8) fra standardvisningen hvis minst én annen kolonne vises.

## <a name="open-the-form"></a>Åpne skjemaet

1. Åpne den **hendelser** listen, og velg deretter **PowerApps** > **tilpasse skjemaer**.

    > [!div class="mx-imgBorder"]
    > ![Åpne listen hendelser, og velg deretter PowerApps > Tilpass skjemaer. ](./media/dependent-drop-down-lists/open-form.png "Åpne listen hendelser, og velg deretter PowerApps > Tilpass skjemaer.")

    En nettleserfane åpnes med standardskjema i PowerApps Studio.

1. (valgfritt) I den **felt** ruten, Hold pekeren over den **tittel** feltet, velg ellipsen (...) som vises, og velg deretter **fjerne**.

    Hvis du har lukket den **felt** ruten, kan du åpne den på nytt ved å velge **SharePointForm1** i det venstre navigasjonsfeltet og deretter velge **Rediger felt** på **Egenskaper** fanen i ruten til høyre.

1. (valgfritt) Gjenta forrige trinn for å fjerne den **vedlegg** feltet fra skjemaet.

    Skjemaet vises med bare feltene som du har lagt til.

    > [!div class="mx-imgBorder"]
    > ![Skjema-uten tittel og vedlegg felt](./media/dependent-drop-down-lists/default-form.png)

## <a name="replace-the-controls"></a>Erstatt kontrollene

1. I den **felt** ruten, velger du pil ned ved siden **plassering**.

    Hvis du har lukket den **felt** ruten, kan du åpne den på nytt ved å velge **SharePointForm1** i det venstre navigasjonsfeltet og deretter velge **Rediger felt** på **Egenskaper** fanen i ruten til høyre.

1. Åpne den **kontroll av typen** listen, og velg deretter **tillatt verdier**.

    > [!div class="mx-imgBorder"]
    > ![Tillatte verdier](./media/dependent-drop-down-lists/change-control.png)

    Inndata mekanismen endres til en **rullegardin** kontroll.

1. Gjenta disse trinnene for den **avdeling** kort.

## <a name="add-the-locations-list"></a>Legg til listen over plasseringer

1. Velg **Vis** > **datakilder** > **Legg til datakilde**.

1. Velg eller Opprett en SharePoint-tilkobling, og deretter angi området som inneholder den **plasseringer** listen.

1. Merk av for denne listen, og velg deretter **koble til**.

    > [!div class="mx-imgBorder"]
    > ![Data-ruten](./media/dependent-drop-down-lists/select-list.png)

    Listen over tilkoblinger viser de **hendelser** -listen som skjemaet er basert på, og den **plasseringer** listen, som identifiserer steder og avdelinger i skjemaet.

    > [!div class="mx-imgBorder"]
    > ![SharePoint-datakilder](./media/dependent-drop-down-lists/data-sources.png)

## <a name="unlock-the-cards"></a>Lås opp kortene

1. Velg den **plassering** kort, velg den **avansert** fanen i den høyre ruten, og velg deretter **Lås opp til å endre egenskapene**.

1. Gjenta det forrige trinnet for den **avdeling** kort.

## <a name="rename-the-controls"></a>Navngi kontrollene på nytt

Hvis du gir nytt navn til kontrollene, du kan identifisere dem enklere og eksemplene er enklere å følge. For å oppdage andre anbefalte fremgangsmåter, kan du se gjennom den [koding standarder og retningslinjer hvitboken](https://aka.ms/powerappscanvasguidelines).

1. I den **plassering** kort, velg den **rullegardin** kontroll.

1. Gi nytt navn til den valgte kontrollen nær toppen av den høyre ruten, ved å skrive eller lime inn **ddLocation**.

    > [!div class="mx-imgBorder"]
    > ![Gi nytt navn til en kontroll](./media/dependent-drop-down-lists/rename-control.png)

1. Gjenta de forrige to trinnene i den **avdeling** kort for å gi nytt navn til den **rullegardin** kontrollen til **ddDepartment**.

## <a name="configure-the-locations"></a>Konfigurer plasseringene

1. Angi den **elementer** -egenskapen for **ddlocation** til denne formelen:

    `Distinct(Locations, Location)`

1. (valgfritt) Mens du holder nede Alt-tasten, kan du åpne **ddLocation**, og Bekreft at listen viser de tre stedene.

## <a name="configure-the-departments"></a>Konfigurer avdelingene

1. Velg **ddDepartment** og deretter, på den **Egenskaper** fanen i den høyre ruten, velg **avhenger av.**

1. Under **overordnet kontroll**, forsikre deg om at **ddLocation** vises i listen øvre og **resultatet** vises i den nederste listen.

    > [!NOTE]
    > Hvis du ikke vil skal samsvare med på en streng, men på den faktiske ID-en til raden med data, velger du **ID** i stedet for **resultatet**.

1. Under **Matching feltet**, og velg **plasseringer** i øvre listen, velg **plassering** i den nederste listen, og velg deretter **Bruk**.

    > [!div class="mx-imgBorder"]
    > ![Avhengig av koblingen](./media/dependent-drop-down-lists/depends-on.png)

    Den **elementer** -egenskapen for **ddDepartment** er satt til denne formelen:

    `Filter(Locations, Location = ddLocation.Selected.Result)`

    Denne formelen filtrerer elementene i **ddDepartment** basert på hva brukeren velger i **ddLocation**. Slik konfigurasjon sikrer at "underordnet" listen over avdelinger gjenspeiler dataene for den "overordnede" plasseringen, som den **plasseringer** angir listen i SharePoint.

1. På den **Egenskaper** fanen i den høyre ruten, åpner du listen siden **verdien**, og velg deretter **avdeling**.

    Dette trinnet angir teksten som vises til alternativene fra den **avdeling** -kolonnen i den **plasseringer** listen i SharePoint.

    > [!div class="mx-imgBorder"]
    > ![Avdelingsverdien](./media/dependent-drop-down-lists/dept-value.png)

## <a name="test-the-form"></a>Teste skjemaet

Mens du holder nede Alt-tasten, åpner du listen over plasseringer, velger du ett, åpne listen over avdelinger, og deretter velger du en.

Listen over plasseringer og avdelinger gjenspeiler informasjonen i den **plasseringer** listen i SharePoint.

> [!div class="mx-imgBorder"]
> ![Åpne listen over plasseringer, endre valget fra Renfrew til Pembroke og åpne deretter listen over avdelinger](./media/dependent-drop-down-lists/dropdowns.gif)

## <a name="save-and-open-the-form-optional"></a>Lagre og åpne skjemaet (valgfritt)

1. Åpne den **filen** -menyen, og velg deretter **lagre** > **Publiser til SharePoint** > **Publiser til SharePoint**.

1. Velg tilbakepilen øverst til venstre, og velg deretter **Tilbake til SharePoint**.

1. Velg **Ny** i kommandolinjen for å åpne det egendefinerte skjemaet.

## <a name="faq"></a>VANLIGE SPØRSMÅL

**Jeg ser ikke alle data: kildene er helt tomt eller har feil data.**
Kontroller om du viser riktig felt for kontrollen i én av følgende måter:

- Velg en rullegardinlisten, og velg deretter den **verdien** -egenskapen i den **Egenskaper** fanen i ruten til høyre.

    > [!div class="mx-imgBorder"]
    > ![Endre rullegardin](./media/dependent-drop-down-lists/drop-down-display-field.png)

- Velg en kombinasjonsboks, og kontroller deretter at teksten er feltet som du vil vise.

    > [!div class="mx-imgBorder"]
    > ![Kombinasjonsboks for endring](./media/dependent-drop-down-lists/combo-box-display-field.png)

**Min rullegardinlisten underordnede inneholder dupliserte elementer.**
Denne symptom sannsynligvis på grunn av ved hjelp av en **oppslag** kolonnen i SharePoint eller en **valg** -funksjonen i PowerApps. Hvis du vil fjerne dupliseringen, bryte en **Distinct** funksjonen rundt den riktig returneringen av data. Mer informasjon: [DISTINCT-funksjonen](functions/function-distinct.md)

## <a name="known-limitations"></a>Kjente begrensninger

Denne konfigurasjonen er tilgjengelig på **rullegardin** kontroller, i tillegg til **kombinasjonsboks** og **listeboks** kontroller som muliggjør én valg om gangen. Du kan ikke bruke den **avhenger av på** konfigurasjon for noen av disse kontrollene hvis de tillater flere valg. Denne tilnærmingen er ikke anbefalt for å arbeide med alternativsett i Common Data Service for apper.

Den **avhenger av på** konfigurasjonen ikke støtter statiske data eller samlinger. Hvis du vil konfigurere avhengige rullegardinlister med disse kildene, kan du redigere uttrykket direkte i formellinjen. I tillegg PowerApps ikke støtter bruk av to valg-felt i SharePoint uten noen samsvarende tabell med data, og du kan ikke definere **Matching feltet** i dette Grensesnittet.