---
title: Å tilpasse et SharePoint-listeskjema | Microsoft Docs
description: Bruk PowerApps for å tilpasse skjemaet der brukerne oppretter og oppdaterer oppføringer i en SharePoint-liste.
author: AFTOwen
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 12/17/2018
ms.author: anneta
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 711d8029f0f8353efcdff5bea8cbb1402884502f
ms.sourcegitcommit: 647e183c070c2159b790c7813a7be1d60b2551bd
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/01/2019
ms.locfileid: "58765483"
---
# <a name="customize-a-sharepoint-list-form-by-using-powerapps"></a>Å tilpasse et SharePoint-listeskjema ved bruk av PowerApps

Du kan enkelt tilpasse skjemaet fra en SharePoint-liste ved å åpne PowerApps i nettleseren. Du trenger ikke å skrive vanlig kode, som C#, eller laste ned en annen app, som InfoPath. Når du publiserer endringene, bygges skjemaet inn i SharePoint-listen. Det blir tilgjengelig for alle brukerne. I PowerApps kan du også se gjennom analyserapporter, enkelt opprette betinget formatering, og koble til andre datakilder.

Hvis du vil følge trinnene i dette emnet, oppretter du en enkel liste slik at du kan se hvordan tilpassingen fungerer, og deretter kan du ta i bruk de samme konseptene i din egen liste.

> [!NOTE]
> Hvis alternativet **Tilpass skjemaer** ikke er tilgjengelig eller ikke fungere som det skal for listen, kan det hende at den inneholder datatyper som [PowerApps ikke støtter](connections/connection-sharepoint-online.md#known-issues). Du kan heller ikke flytte skjemaet til en annen liste eller et annet [miljø](working-with-environments.md).

## <a name="create-a-list"></a>Opprett en liste

Opprett en liste på et SharePoint-område, og deretter legge til disse kolonnene i denne listen:

- **Detaljer** (ja/nei)
- **Pris** (valuta)
- **Tilgjengelighet** (data uten tidspunkt)
- **Farge** (valg)

> [!div class="mx-imgBorder"]
> ![Velg områdeinnhold > Ny > liste, type listenavnet og velg Opprett. For hver kolonne, kan du velge Legg til kolonne, må du angi hvilken liste (Ja/Nei, valuta, dato, valg), angi navnet på (detaljer, pris, tilgjengelighet, farge), og velg Lagre.](./media/customize-list-form/create-list.gif)

## <a name="open-the-form"></a>Åpne skjemaet

1. Velg i kommandolinjen, **PowerApps**, og velg deretter **tilpasse skjemaet**.

    PowerApps Studio åpner i den samme nettleserfanen.

1. Hvis dialogboksen **Velkommen til PowerApps Studio** åpnes, velger du **Hopp over**.

> [!div class="mx-imgBorder"]
> ![Velg PowerApps i kommandolinjen, og velg deretter Tilpass skjemaet. PowerApps Studio åpner i den samme nettleserfanen. Hvis dialogboksen Velkommen til PowerApps Studio-dialogboksen åpnes, velger du Hopp over.](./media/customize-list-form/create-form.gif)

## <a name="move-and-remove-a-field"></a>Flytte og fjerne et felt

1. Dra den **tilgjengelighet** feltet nederst i listen over felt.

    Feltene vises i rekkefølgen du angir.

1. Hold pekeren over den **vedlegg** feltet, velg ellipsen (...) som vises, og velg deretter **fjerne**.

    Feltet som du angir forsvinner fra skjemaet.

> [!div class="mx-imgBorder"]
> ![Dra feltet tilgjengelighet til bunnen av listen over felt. Hold pekeren over vedlegg-feltet, velg ellipsen (...) som vises, og velg deretter Fjern.](./media/customize-list-form/move-remove-fields.gif)

## <a name="set-conditional-formatting"></a>Å angi betinget formatering

Du kan konfigurere feltene **Pris**, **Tilgjengelighet** og **Farger** slik at de bare vises hvis **Detaljer** er angitt til ja.

1. I navigasjonsfeltet til venstre, utvider **Details_DataCard1**, og Legg merke til tallet som vises på slutten av **DataCardValue**.

1. Angi den **synlighet** -egenskapen for den **farge**, **tilgjengelighet**, og **pris** kort til denne formelen (erstatter, om nødvendig den tall med det som du noterte ned i forrige trinn):

    **Hvis (DataCardValue2.Value = true, true)**

1. Velg **Detaljer**-bryteren (ved å klikke eller trykke på den) flere ganger mens du holder nede ALT.

    De tre feltene som du konfigurerte, vises og forsvinner fra skjemaet.

> [!div class="mx-imgBorder"]
> ![I navigasjonsfeltet til venstre, Vær oppmerksom på tallet som vises på slutten av DataCardValue. Angi Visibility-egenskapen til fargen, tilgjengelighet og pris kort til denne formelen. Hold nede Alt-tasten, og velg detaljer-kontrollen flere ganger.](./media/customize-list-form/conditional-format.gif)

## <a name="save-and-publish-the-form"></a>Lagre og publisere skjemaet

1. Åpne **Fil**-menyen, velg **Lagre**, og deretter velger du **Publiser til SharePoint** to ganger.

1. Velg tilbakepilen øverst til venstre, og velg deretter **Tilbake til SharePoint**.

> [!div class="mx-imgBorder"]
> ![Åpne fil-menyen, velg Lagre, og velg deretter Publiser til SharePoint to ganger. Velg tilbake-pilen i hjørnet øverst til venstre, og velg deretter tilbake til SharePoint.](./media/customize-list-form/save-form.gif)

## <a name="further-customize-your-form"></a>Tilpasse skjemaet ytterligere

1. Åpne listen, velg **ny** i kommandolinjen, og velg deretter **Tilpass** nær toppen av skjemaet.

1. Tilpasse skjemaet på en rekke måter, blant annet slike som disse emnene beskriver:

    - Endre størrelsen, retningen eller begge deler (for eksempel for å [skjemaet bredere](set-aspect-ratio-portrait-landscape.md)).
    - [Tilpasse én eller flere kort](working-with-cards.md) (for eksempel endre et kort Vis tekst eller inndata-kontroll).
    - Opprette et [oppslagsfelt](sharepoint-lookup-fields.md).

    Mer informasjon: [Forstå integrasjon for SharePoint-skjemaer](sharepoint-form-integration.md)

## <a name="use-the-default-form"></a>Å bruke standardskjemaet

1. Åpne Innstillinger-siden fra SharePoint-listen (ved å velge tannhjulikonet øverst til høyre), og deretter velger du **Listeinnstillinger**.

2. Velg **Skjemainnstillinger** under **Generelle innstillinger**.

3. Velg én av disse alternativene på **Skjemainnstillinger**-siden, og velg deretter **OK**.

    - **Å bruke standard SharePoint-skjema** – Når en bruker åpner listen og velger **Ny** i kommandolinjen, vises standardskjemaet for listen.

    - **Å bruke et egendefinert skjema i PowerApps** – Når en bruker åpner listen og velger **Ny** i kommandolinjen, vises standardskjemaet. (Som et alternativ kan du publisere skjemaet på nytt i PowerApps.)

    Du kan veksle frem og tilbake mellom alternativer etter behov.

    ![Alternativer for skjemainnstillinger](./media/customize-list-form/form-settings.png)

## <a name="delete-the-custom-form"></a>Å slette det egendefinerte skjemaet

1. Åpne Innstillinger-siden fra SharePoint-listen (ved å velge tannhjulikonet øverst til høyre), og deretter velger du **Listeinnstillinger**.

1. Velg **Skjemainnstillinger** under **Generelle innstillinger**.

1. Velg **Bruk standard SharePoint-skjema** på **Skjemainnstillinger**-siden, og velg deretter **Slett egendefinert skjema**.

    ![Å slette det egendefinerte skjemaet](./media/customize-list-form/use-default-sharepoint.png)

## <a name="q--a"></a>Q & A

### <a name="forms-vs-apps"></a>Skjemaer kontra apper

**SPØRSMÅL:** Hvordan skiller et egendefinert skjema seg fra en frittstående app som jeg oppretter fra SharePoint eller PowerApps?

**A:** Hvis du tilpasser skjemaet for en SharePoint-liste, vises ikke skjemaet som en app i PowerApps Studio eller PowerApps Mobile. Du kan bare åpne skjemaet fra listen det ble opprettet fra.

**SPØRSMÅL:** Når bør jeg tilpasse et skjema for å behandle data i en SharePoint-liste, og når bør jeg opprette en frittstående app?

**A:** Tilpasse et skjema hvis du vil at brukerne skal kunne behandle data uten å forlate SharePoint (for eksempel i en videoavspilling). Du oppretter en app hvis du ønsker at brukerne skal kunne behandle data utenfor SharePoint (for eksempel, på en mobil enhet).

**SPØRSMÅL:** Kan jeg tilpasse et skjema og opprette en app for den samme listen?

**A:** ja.

**SPØRSMÅL:** Kan jeg tilpasse en liste og opprette en app ved hjelp av de samme funksjonene?

**A:** ja.

**SPØRSMÅL:** Kan jeg tilpasse et skjema i et annet miljø enn standardmiljøet i organisasjonen Min?

**A:** nei.

### <a name="manage-your-custom-form"></a>Å behandle det egendefinerte skjemaet

**SPØRSMÅL:** Hvordan kan jeg enkelt dele skjemaet med andre?

**A:** Åpne skjemaet, velg **Kopier kobling**, og send koblingen du vil bruke skjemaet for alle.

**SPØRSMÅL:** Kan jeg oppdatere skjemaet uten å gjøre endringene mine synlige for andre?

**A:** ja. Du kan endre skjemaet og lagre det så mange ganger du vil, men endringene vil ikke være synlige for andre før du velger **Publiser til SharePoint**.

**SPØRSMÅL:** Hvis jeg tilpasse et listeskjema og gjør en feil, kan jeg gå tilbake til en tidligere versjon?

**A:** ja.

1. Åpne listen, velg **PowerApps** på kommandolinjen, og velg deretter **Tilpass skjemaer**.

1. Velg **Fil** i PowerApps Studio, velg deretter **Se alle versjoner**. **Versjoner**-siden åpnes i en ny fane i nettleseren.

    > [!NOTE]
    > Hvis du ikke ser **Se alle versjoner**-knappen, velger du **Lagre**. Knappen skal nå vises.

1. Gå tilbake til **Lagre**-siden i den andre nettleserfanen uten å lukke **Versjoner**-siden eller nettleserfanen. Klikk eller trykk på pilen øverst i venstre navigasjonsrute, og deretter klikk eller trykk på **Tilbake til SharePoint** for å låse opp skjemaet og avslutte PowerApps Studio.

1. Gå tilbake til **Versjoner**-siden i den andre nettleserfanen, finn versjonen du ønsker å gjenopprette, og velg deretter **Gjenopprett**.

    > [!NOTE]
    > Hvis du får en feilmelding om at gjenopprettingen mislyktes fordi skjemaet er låst av en annen bruker, må du vente til brukeren låser opp skjemaet, og prøve på nytt.

**SPØRSMÅL:** Kan jeg flytte skjemaet fra én liste til en annen?

**A:** nei.

### <a name="administer-your-custom-form"></a>Å administrere det egendefinerte skjemaet

**SPØRSMÅL:** Hvordan kan jeg dele skjemaet?

**A:** Du trenger ikke å dele skjemaet – skjemaet arver tillatelser fra SharePoint-listen. Når du er ferdig med å tilpasse det, [publiserer du det bare tilbake til SharePoint](customize-list-form.md#save-and-publish-the-form) slik at andre kan bruke det.

**SPØRSMÅL:** Hvem kan tilpasse skjemaer?

**A:** Alle med SharePoint-tillatelser til å administrere, utforme eller redigere den tilhørende listen.

**SPØRSMÅL:** Trenger jeg en PowerApps-lisens til å opprette eller bruke egendefinerte listeskjemaer?

**A:** Du trenger en [Office 365-abonnementer som inkluderer PowerApps](https://docs.microsoft.com/power-platform/admin/pricing-billing-skus.md#licenses).

**SPØRSMÅL:** Hva skjer når gjestebrukere har tilgang til en liste som har et egendefinert skjema?

**A:** Gjestebrukere får en feilmelding hvis de prøver å få tilgang til et listeskjema som er blitt tilpasset ved hjelp av PowerApps.

**SPØRSMÅL:** Som administrator, hvordan kan jeg få en liste over alle tilpassede skjemaer i Min organisasjon?

**A:** Hvis du er tenant-administrator for PowerApps, eller du har administratortillatelser i standardmiljøet for PowerApps i organisasjonen, gjør du følgende:

1. Velg standardmiljøet for organisasjonen fra listen over miljøer i [Administrasjonssenteret for PowerApps](https://admin.powerapps.com).

1. Velg **Ressurser** øverst på siden for standardmiljø.

1. Se etter apper med en **SharePoint-skjema**-apptype fra listen over apper – dette er de tilpassede skjemaene.

    ![Liste over egendefinerte skjemaer](./media/customize-list-form/all-customized-forms.png)
