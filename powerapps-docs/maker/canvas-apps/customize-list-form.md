---
title: Å tilpasse et SharePoint-listeskjema | Microsoft Docs
description: Bruk PowerApps for å tilpasse skjemaet der brukerne oppretter og oppdaterer oppføringer i en SharePoint-liste.
author: tapanm-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 04/04/2019
ms.author: tapanm
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 60d4fb21bc2f298b1dd2ce37c3e25f5355e881cb
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71993146"
---
# <a name="customize-a-sharepoint-list-form-by-using-powerapps"></a>Å tilpasse et SharePoint-listeskjema ved bruk av PowerApps

Du kan enkelt tilpasse skjemaet fra en SharePoint-liste ved å åpne PowerApps i nettleseren. Du trenger ikke å skrive vanlig kode, som C#, eller laste ned en annen app, som InfoPath. Når du publiserer endringene, bygges skjemaet inn i SharePoint-listen. Det blir tilgjengelig for alle brukerne. I PowerApps kan du også se gjennom analyserapporter, enkelt opprette betinget formatering, og koble til andre datakilder.

Hvis du vil følge trinnene i dette emnet, oppretter du en enkel liste slik at du kan se hvordan tilpassingen fungerer, og deretter kan du ta i bruk de samme konseptene i din egen liste.

> [!NOTE]
> Hvis alternativet **Tilpass skjemaer** ikke er tilgjengelig eller ikke fungere som det skal for listen, kan det hende at den inneholder datatyper som [PowerApps ikke støtter](connections/connection-sharepoint-online.md#known-issues). Du kan heller ikke flytte skjemaet til en annen liste eller et annet [miljø](working-with-environments.md).

## <a name="create-a-list"></a>Opprett en liste

Opprett en liste på et SharePoint-område, og legg deretter til disse Kol onnene i denne listen:

- **Detaljer** (ja/nei)
- **Pris** (valuta)
- **Tilgjengelighet** (data uten tidspunkt)
- **Farge** (valg)

> [!div class="mx-imgBorder"]
> @no__t 0Select område innhold > Ny > liste, skriver du inn navnet på listen og velger Opprett. Velg Legg til kolonne for hver kolonne, angi liste typen (ja/nei, valuta, dato, valg), angi liste navnet (detaljer, pris, tilgjengelighet, farge), og velg Lagre. ](./media/customize-list-form/create-list.gif)

## <a name="open-the-form"></a>Åpne skjemaet

1. Velg **powerapps**på kommando linjen, og velg deretter **Tilpass skjema**.

    PowerApps Studio åpner i den samme nettleserfanen.

1. Hvis dialogboksen **Velkommen til PowerApps Studio** åpnes, velger du **Hopp over**.

> [!div class="mx-imgBorder"]
> ![In kommando linjen, Velg PowerApps, og velg deretter Tilpass skjema. PowerApps Studio åpner i den samme nettleserfanen. Hvis dialog boksen Velkommen til PowerApps Studio åpnes, velger du Hopp over. ](./media/customize-list-form/create-form.gif)

## <a name="move-and-remove-a-field"></a>Flytt og Fjern et felt

1. Dra **tilgjengelighet** -feltet til bunnen av listen over felt.

    Feltene vises i den rekkefølgen du angir.

1. Hold pekeren over **vedlegg** -feltet, Velg ellipsen (...) som vises, og velg deretter **Fjern**.

    Feltet du angir, forsvinner fra skjemaet.

> [!div class="mx-imgBorder"]
> @no__t – 0Drag tilgjengelighet-feltet nederst i listen over felt. Hold pekeren over vedlegg-feltet, Velg ellipsen (...) som vises, og velg deretter Fjern. ](./media/customize-list-form/move-remove-fields.gif)

## <a name="set-conditional-formatting"></a>Å angi betinget formatering

Du kan konfigurere feltene **Pris**, **Tilgjengelighet** og **Farger** slik at de bare vises hvis **Detaljer** er angitt til ja.

1. Utvid **Details_DataCard1**i det venstre navigasjons feltet, og Merk deg hvilket tall som vises ved slutten av **DataCardValue**.

1. Angi **synlig** -egenskapen for **farge**-, **tilgjengelighets**-og **pris** kortene til denne formelen (erstatning, ved behov, ved siden av det som du noterte i forrige trinn):

    **If (DataCardValue2. Value = True, True)**

1. Velg **Detaljer**-bryteren (ved å klikke eller trykke på den) flere ganger mens du holder nede ALT.

    De tre feltene som du konfigurerte, vises og forsvinner fra skjemaet.

> [!div class="mx-imgBorder"]
> @no__t – 0In venstre navigasjons felt noterer du tallet som vises på slutten av DataCardValue. Angi Visibility-egenskapen for farge-, tilgjengelighets-og pris kortene til denne formelen. Hold nede Alt-tasten, og velg detaljer-kontrollen flere ganger. ](./media/customize-list-form/conditional-format.gif)

## <a name="save-and-publish-the-form"></a>Lagre og publisere skjemaet

1. Åpne **Fil**-menyen, velg **Lagre**, og deretter velger du **Publiser til SharePoint** to ganger.

1. Velg tilbakepilen øverst til venstre, og velg deretter **Tilbake til SharePoint**.

> [!div class="mx-imgBorder"]
> @no__t fil-menyen, velg Lagre, og velg deretter Publiser til SharePoint to ganger. Velg tilbake-pilen i hjørnet øverst til venstre, og velg deretter tilbake til SharePoint. ](./media/customize-list-form/save-form.gif)

## <a name="further-customize-your-form"></a>Å tilpasse skjemaet ytterligere

1. Åpne listen, velg **ny** på kommando linjen, og velg deretter **Tilpass** nær toppen av skjemaet.

1. Tilpass skjemaet ditt på en rekke måter, for eksempel de som disse emnene beskriver:

    - Endre størrelsen, retningen eller begge deler (for eksempel for å [skjemaet bredere](set-aspect-ratio-portrait-landscape.md)).
    - [Tilpass ett eller flere kort](working-with-cards.md) (for eksempel endre et korts visnings tekst eller inn data kontroll).
    - Opprette et [oppslagsfelt](sharepoint-lookup-fields.md).

    Mer informasjon: [Forstå integrasjon med SharePoint-skjemaer](sharepoint-form-integration.md).

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

## <a name="q--a"></a>SPØRSMÅL & A

### <a name="forms-vs-apps"></a>Skjemaer kontra apper

**Q** Hvordan skiller et egen definert skjema seg fra en fritt stående app som jeg oppretter fra SharePoint eller PowerApps?

**AV** Hvis du tilpasser skjemaet for en SharePoint-liste, vises ikke skjemaet som en app i PowerApps Studio eller PowerApps Mobile. Du kan bare åpne skjemaet fra listen det ble opprettet fra.

**Q** Når skal jeg tilpasse et skjema for å behandle data i en SharePoint-liste, og når bør jeg opprette en fritt stående app?

**AV** Tilpass et skjema hvis du vil at brukerne skal kunne behandle data uten å forlate SharePoint (for eksempel i en skrive bords leser). Du oppretter en app hvis du ønsker at brukerne skal kunne behandle data utenfor SharePoint (for eksempel, på en mobil enhet).

**Q** Kan jeg tilpasse et skjema og opprette en app for den samme listen?

**AV** ja.

**Q** Kan jeg tilpasse en liste og opprette en App ved hjelp av de samme funksjonene?

**AV** ja.

**Q** Kan jeg tilpasse et skjema i et annet miljø enn standard miljøet i organisasjonen min?

**AV** nei.

### <a name="manage-your-custom-form"></a>Å behandle det egendefinerte skjemaet

**Q** Hvordan kan jeg enkelt dele skjemaet med andre?

**AV** Åpne skjemaet, velg **Kopier kobling**, og send deretter koblingen til hvem du vil bruke skjemaet til.

**Q** Kan jeg oppdatere skjemaet uten å gjøre endringene mine synlige for andre?

**AV** ja. Du kan endre skjemaet og lagre det så mange ganger du vil, men endringene vil ikke være synlige for andre før du velger **Publiser til SharePoint**.

**Q** Hvis jeg tilpasser et liste skjema og gjør en feil, kan jeg gå tilbake til en tidligere versjon?

**AV** ja.

1. Åpne listen, velg **PowerApps** på kommandolinjen, og velg deretter **Tilpass skjemaer**.

1. Velg **Fil** i PowerApps Studio, velg deretter **Se alle versjoner**. **Versjoner**-siden åpnes i en ny fane i nettleseren.

    > [!NOTE]
    > Hvis du ikke ser **Se alle versjoner**-knappen, velger du **Lagre**. Knappen skal nå vises.

1. Gå tilbake til **Lagre**-siden i den andre nettleserfanen uten å lukke **Versjoner**-siden eller nettleserfanen. Klikk eller trykk på pilen øverst i venstre navigasjonsrute, og deretter klikk eller trykk på **Tilbake til SharePoint** for å låse opp skjemaet og avslutte PowerApps Studio.

1. Gå tilbake til **Versjoner**-siden i den andre nettleserfanen, finn versjonen du ønsker å gjenopprette, og velg deretter **Gjenopprett**.

    > [!NOTE]
    > Hvis du får en feil melding om at gjenopprettingen mislyktes fordi skjemaet er låst av en annen bruker, må du vente til brukeren låser opp skjemaet, og deretter prøve på nytt.

**Q** Kan jeg flytte skjemaet fra én liste til en annen?

**AV** nei.

### <a name="administer-your-custom-form"></a>Å administrere det egendefinerte skjemaet

**Q** Hvordan dele skjemaet mitt?

**AV** Du trenger ikke å dele skjemaet – skjemaet arver tillatelser fra SharePoint-listen. Når du er ferdig med å tilpasse det, [publiserer du det bare tilbake til SharePoint](customize-list-form.md#save-and-publish-the-form) slik at andre kan bruke det.

**Q** Hvem kan tilpasse skjemaer?

**AV** Alle med SharePoint-tillatelser til å administrere, utforme eller redigere den tilknyttede listen.

**Q** Trenger jeg en PowerApps-lisens for å opprette eller bruke egen definerte liste skjemaer?

**AV** Du trenger en [Office 365-plan som inkluderer powerapps](https://docs.microsoft.com/power-platform/admin/pricing-billing-skus#licenses).

**Q** Hva skjer når gjeste brukere har tilgang til en liste som har et egen definert skjema?

**AV** Gjeste brukere får en feil melding hvis de prøver å få tilgang til et liste skjema som er tilpasset ved hjelp av PowerApps.

**Q** Som administrator kan jeg få en liste over alle tilpassede skjemaer i organisasjonen min?

**AV** Hvis du er leier administrator for PowerApps, eller hvis du har miljø administrator tillatelser i standard miljøet for PowerApps i organisasjonen, gjør du følgende:

1. Velg standardmiljøet for organisasjonen fra listen over miljøer i [Administrasjonssenteret for PowerApps](https://admin.powerapps.com).

1. Velg **Ressurser** øverst på siden for standardmiljø.

1. Se etter apper med en type **SharePoint-skjema** i listen over apper – dette er de tilpassede skjemaene.

    ![Liste over egendefinerte skjemaer](./media/customize-list-form/all-customized-forms.png)
