---
title: Å tilpasse et SharePoint-listeskjema | Microsoft Docs
description: Bruk PowerApps for å tilpasse skjemaet der brukerne oppretter og oppdaterer oppføringer i en SharePoint-liste.
author: AFTOwen
ms.service: powerapps
ms.topic: conceptual
ms.component: canvas
ms.date: 06/11/2018
ms.author: anneta
ms.openlocfilehash: 1ab7b6bc5f8e2617fc3d66bcdac40b930805d14d
ms.sourcegitcommit: 79b8842fb0f766a0476dae9a537a342c8d81d3b3
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/07/2018
ms.locfileid: "37900104"
---
# <a name="customize-a-sharepoint-list-form-by-using-powerapps"></a>Å tilpasse et SharePoint-listeskjema ved bruk av PowerApps

Du kan enkelt tilpasse skjemaet fra en SharePoint-liste ved å åpne PowerApps i nettleseren. Du trenger ikke å skrive vanlig kode, som C#, eller laste ned en annen app, som InfoPath. Når du publiserer endringene, bygges skjemaet inn i SharePoint-listen. Det blir tilgjengelig for alle brukerne. I PowerApps kan du også se gjennom analyserapporter, enkelt opprette betinget formatering, og koble til andre datakilder.

Hvis du vil følge trinnene i dette emnet, oppretter du en enkel liste slik at du kan se hvordan tilpassingen fungerer, og deretter kan du ta i bruk de samme konseptene i din egen liste.

> [!NOTE]
> Hvis alternativet **Tilpass skjemaer** ikke er tilgjengelig eller ikke fungere som det skal for listen, kan det hende at den inneholder datatyper som [PowerApps ikke støtter](connections/connection-sharepoint-online.md#known-issues). Du kan heller ikke flytte skjemaet til en annen liste eller et annet [miljø](working-with-environments.md).

## <a name="prerequisites"></a>Forutsetninger

Opprett en liste som inneholder disse kolonnene på et SharePoint-område:

- **ProductName** (enkelt linje med tekst)
- **Detaljer** (ja/nei)
- **Pris** (valuta)
- **Tilgjengelighet** (data uten tidspunkt)
- **Farge** (valg)

## <a name="open-the-form-in-powerapps"></a>Å åpne skjemaet i PowerApps

1. Åpne listen du opprettet, og velg deretter **Ny** i kommandolinjen.

    Skjemaet åpnes og viser feltene du har lagt til, i tillegg til **Tittel** og **Vedlegg**.

1. Velg **Tilpasse** nær toppen av skjemaet.

    PowerApps Studio åpner i den samme nettleserfanen.

1. Hvis dialogboksen **Velkommen til PowerApps Studio** åpnes, velger du **Hopp over**.

## <a name="hide-extra-fields"></a>Å skjule ekstra felter

PowerApps viser skjemaet ditt midt på skjermen, men det inneholder noen felter som du muligens ikke ønsker å vise.

- Fjern merket for disse feltene i **Data**-ruten.

  - **Tittel**
  - **Endret**
  - **Opprettet**
  - **Opprettet av**
  - **Endret av**
  - **ID**

    De feltene forsvinner fra visningen, og bare feltene du opprettet vises.

    ![Feltliste](./media/customize-list-form/field-list.png)

## <a name="set-conditional-formatting"></a>Å angi betinget formatering

Du kan konfigurere feltene **Pris**, **Tilgjengelighet** og **Farger** slik at de bare vises hvis **Detaljer** er angitt til ja.

1. Velg **Pris**-kortet ved å klikke eller trykke på det.

    ![Å velge Tilgjengelighet-kortet](./media/customize-list-form/select-card.png)

1. Velg **Synlig** i egenskapslisten.

    ![Å velge Synlig-egenskapen](./media/customize-list-form/select-property.png)

1. Skriv eller lim inn denne formelen i formellinjen:

    **If(DataCardValue3.Value = true, true)**

    ![Å angi verdien til Synlig-egenskapen](./media/customize-list-form/build-formula.png)

1. Gjenta de tre siste trinnene med **Tilgjengelighet**- og **Farge**-kortet.

1. Velg **Detaljer**-bryteren (ved å klikke eller trykke på den) flere ganger mens du holder nede ALT.

    De tre feltene som du konfigurerte, vises og forsvinner fra skjemaet.

1. (valgfritt) Du kan tilpasse skjemaet på en rekke måter, inkludert disse:

    - Endre størrelsen, retningen eller begge deler (for eksempel for å [skjemaet bredere](set-aspect-ratio-portrait-landscape.md)).
    - Legge til en kontroll slik at brukerne kan [laste opp vedlegg](controls/properties-text.md).
    - Opprette et [oppslagsfelt](sharepoint-lookup-fields.md).

## <a name="save-publish-and-show-the-form"></a>Å lagre, publisere og vise skjemaet

1. Åpne **Fil**-menyen, velg **Lagre**, og deretter velger du **Publiser til SharePoint** to ganger.

1. Velg tilbakepilen øverst til venstre, og velg deretter **Tilbake til SharePoint**.

1. Velg **Ny** i kommandolinjen for å åpne det egendefinerte skjemaet.

1. Velg **Detaljer**-bryteren flere ganger for å skule og vise de tre siste feltene.

Hvis du vil [tilpasse skjemaet enda mer](sharepoint-form-integration.md), åpner du det, velger **Tilpasse** nær toppen av skjemaet, og deretter utfører, lagrer og publiserer du endringene.

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

## <a name="q--a"></a>Spørsmål og svar

### <a name="forms-vs-apps"></a>Skjemaer kontra apper

**Spørsmål:** Hvordan skiller et egendefinert skjema seg fra en frittstående app som jeg oppretter fra SharePoint eller PowerApps?

**Svar:** Hvis du tilpasser skjemaet for en SharePoint-liste, vises ikke skjemaet som en app i PowerApps Studio eller PowerApps Mobil. Du kan bare åpne skjemaet fra listen det ble opprettet fra.

**Spørsmål:** Når bør jeg tilpasse et skjema for å behandle data i en sharePoint-liste, og når bør jeg opprette en frittstående app?

**Svar** Tilpass et skjema hvis du ønsker at brukerne skal kunne behandle data uten å forlate SharePoint (for eksempel, i en nettleser på en stasjonær datamaskin). Du oppretter en app hvis du ønsker at brukerne skal kunne behandle data utenfor SharePoint (for eksempel, på en mobil enhet).

**Spørsmål:** Kan jeg tilpasse et skjema og opprette en app for den samme listen?

**Svar:** Ja.

**Spørsmål:** Kan jeg tilpasse en liste og opprette en app ved bruk av de samme funksjonene?

**Svar:** Ja.

**Spørsmål:** Kan jeg tilpasse et skjema i et annet miljø enn standardmiljøet i organisasjonen min?

**Svar:** Nei.

### <a name="manage-your-custom-form"></a>Å behandle det egendefinerte skjemaet

**Spørsmål:** Hvordan kan jeg enkelt dele skjemaet med andre?

**Svar** Åpne skjemaet, velg **Kopier kobling**, og deretter kan du sende koblingen til de du ønsker skal bruke skjemaet.

**Spørsmål:** Kan jeg oppdatere skjemaet uten å gjøre endringene mine synlige for andre?

**Svar:** Ja. Du kan endre skjemaet og lagre det så mange ganger du vil, men endringene vil ikke være synlige for andre før du velger **Publiser til SharePoint**.

**Spørsmål:** Kan jeg gå tilbake til en tidligere versjon hvis jeg gjør en feil når jeg tilpasser listeskjemaet?

**Svar:** Ja.

1. Åpne listen, velg **PowerApps** på kommandolinjen, og velg deretter **Tilpass skjemaer**.

1. Velg **Fil** i PowerApps Studio, velg deretter **Se alle versjoner**. **Versjoner**-siden åpnes i en ny fane i nettleseren.

    > [!NOTE]
    > Hvis du ikke ser **Se alle versjoner**-knappen, velger du **Lagre**. Knappen skal nå vises.

1. Gå tilbake til **Lagre**-siden i den andre nettleserfanen uten å lukke **Versjoner**-siden eller nettleserfanen. Klikk eller trykk på pilen øverst i venstre navigasjonsrute, og deretter klikk eller trykk på **Tilbake til SharePoint** for å låse opp skjemaet og avslutte PowerApps Studio.

1. Gå tilbake til **Versjoner**-siden i den andre nettleserfanen, finn versjonen du ønsker å gjenopprette, og velg deretter **Gjenopprett**.

    > [!NOTE]
    > Hvis du får en feilmelding om at gjenopprettingen mislyktes fordi skjemaet er låst av en annen bruker, må du vente til brukeren låser opp skjemaet, og prøve på nytt.

**Spørsmål:** Kan jeg flytte skjemaet fra én liste til en annen?

**Svar:** Nei.

### <a name="administer-your-custom-form"></a>Å administrere det egendefinerte skjemaet

**Spørsmål:** Hvordan deler jeg skjemaet mitt?

**Svar:** Du trenger ikke å dele skjemaet – skjemaet arver tillatelser fra SharePoint-listen. Når du er ferdig med å tilpasse det, [publiserer du det bare tilbake til SharePoint](customize-list-form.md#save-and-publish-the-list-form-back-to-sharepoint) slik at andre kan bruke det.

**Spørsmål:** Hvem kan tilpasse skjemaer?

**Svar:** Alle med SharePoint-tillatelser til å administrere, utforme eller redigere den tilhørende listen.

**Spørsmål:** Trenger jeg en PowerApps-lisens for å opprette eller bruke egendefinerte listeskjemaer?

**Svar:** Du trenger et [Office 365-abonnement som inkluderer PowerApps](../../administrator/pricing-billing-skus.md#licenses).

**Spørsmål:** Hva skjer når gjestebrukere har tilgang til en liste som har et egendefinert skjema?

**Svar:** Gjestebrukere får en feilmelding hvis de prøver å få tilgang til et listeskjema som er blitt tilpasset ved hjelp av PowerApps.

**Spørsmål:** Hvordan får jeg som administrator en liste over alle tilpassede skjemaer i min organisasjon?

**Svar:** Hvis du er tenant-administrator for PowerApps eller har administratortillatelser i standardmiljøet for PowerApps i organisasjonen, gjør du følgende:

1. Velg standardmiljøet for organisasjonen fra listen over miljøer i [Administrasjonssenteret for PowerApps](https://admin.powerapps.com).

1. Velg **Ressurser** øverst på siden for standardmiljø.

1. Se etter apper med en **SharePoint-skjema**-apptype fra listen over apper – dette er de tilpassede skjemaene.

    ![Liste over egendefinerte skjemaer](./media/customize-list-form/all-customized-forms.png)
