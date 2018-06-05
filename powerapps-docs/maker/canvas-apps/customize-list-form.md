---
title: Å tilpasse et SharePoint-listeskjema ved hjelp av PowerApps | Microsoft Docs
description: Å bruke PowerApps til å tilpasse et listeskjema i SharePoint.
services: ''
suite: powerapps
documentationcenter: na
author: skjerland
manager: anneta
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/05/2018
ms.author: sharik
ms.openlocfilehash: 62c3050ecee4d068d5417fe3846abb3495990d8b
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/22/2018
ms.locfileid: "30996142"
---
# <a name="customize-a-sharepoint-list-form-using-powerapps"></a>Å tilpasse et SharePoint-listeskjema ved hjelp av PowerApps

Du kan nå enkelt tilpasse alle SharePoint-listeskjemaer i PowerApps. Mye av det du har gjort med InfoPath for å tilpasse listeskjemaer i SharePoint, kan du nå gjøre innebygd i en nettleser med PowerApps. I tillegg gir PowerApps deg muligheten til å gjøre så mye mer!

PowerApps er direkte integrert med SharePoint – det er ikke nødvendig å laste ned en annen app til datamaskinen. Og med PowerApps kan du opprette rikholdig tilpassede skjemaer uten å måtte skrive inn noe kode. Så snart de er publisert, er skjemaene innebygd i SharePoint-listen, og er tilgjengelige for alle brukere av listen.

Og fordi PowerApps er sømløst integrert i SharePoint, er det ikke nødvendig å administrere skjemaer fra to steder: Tillatelser er arvet fra, og administreres via SharePoint. Det beste av alt er at når du integrerer PowerApps med SharePoint, får du tilgang til mange kraftige funksjoner, som analyserapporter, enkle pek-og-klikk-regler for betinget formatering og tilkoblinger til andre datakilder.

Klar til å begynne å tilpasse? La oss komme i gang!

## <a name="create-a-custom-list-form-app-in-powerapps"></a>Å opprette en app for egendefinerte listeskjemaer i PowerApps

> [!NOTE]
> Alternativet **Tilpass skjemaer** blir utilgjengelig, eller vil kanskje ikke fungere som det skal, hvis SharePoint-listen inneholder datatyper som PowerApps ikke støtter.

Trykk eller klikk på **PowerApps** på kommandolinjen i SharePoint-listen. Deretter trykker eller klikker du på **Å tilpasse skjemaer**. Dette tar deg til nettversjonen av PowerApps Studio i en nettleser, der PowerApps genererer en skjema-app for én skjerm, som vist i følgende eksempel.

![Skjema-app for én skjerm](./media/customize-list-form/list-form-app.png)

Hvis du vil gå tilbake til SharePoint-listen, kan du når som helst klikke eller trykke på **Tilbake til SharePoint** øverst til venstre i PowerApps Studio for nett.

## <a name="customize-the-list-form"></a>Å tilpasse listeskjemaet

PowerApps tilbyr mange måter å tilpasse skjemaet på. Her er noen eksempler:

* [Å endre størrelse og retning](set-aspect-ratio-portrait-landscape.md)
* [Å formatere teksten](controls/properties-text.md)
* [Å legge til bilder](add-images-pictures-audio-video.md) eller [diagrammer](use-line-pie-bar-chart.md)
* [Å legge til egendefinert datavalidering](functions/function-validate.md)
* [Å legge til regler](working-with-rules.md)
* [Å opprette flere visninger](https://powerapps.microsoft.com/blog/separate-custom-forms/)

La oss, for å illustrere det, si at skjemaet har et **AccountID**-felt som du ikke vil skal vises.

![Å velge AccountID-felt](./media/customize-list-form/select-card.png)

Å skjule feltet er lett i PowerApps – du fjerner ganske enkelt merket for **AccountID** i alternativene for skjematilpasning.

![Å fjerne merket for AccountID](./media/customize-list-form/checkbox.png)

Hvis du vil ha trinnvise instruksjoner om hvordan du kan skjule felt og gjøre andre endringer i skjemaet, kan du se [Å tilpasse skjemaer i PowerApps](customize-forms-sharepoint.md). Hvis du vil ha en fullstendig liste over ressurser, kan du se [Microsoft PowerApps-dokumenter](https://docs.microsoft.com/powerapps/).

## <a name="save-and-publish-the-list-form-back-to-sharepoint"></a>Å lagre og publisere listeskjemaet tilbake til SharePoint

1. Når du er ferdig, klikker eller trykker du på **Fil**, og deretter klikker eller trykker du på **Lagre**. Dette lagrer endringene til PowerApps-skjemaappen.

1. Hvis du vil publisere skjemaet tilbake til SharePoint slik at andre kan bruke det, klikker eller trykker du på **Publiser til SharePoint**. Du trenger ikke å bekymre deg om å dele skjemaet – skjemaet arver tillatelser fra SharePoint-listen.

    ![Å publisere til SharePoint](./media/customize-list-form/publish-to-sharepoint.png)  

## <a name="view-your-list-form-in-sharepoint"></a>Å vise listeskjemaet i SharePoint

1. Hvis du vil se det tilpassede skjemaet, klikker eller trykker du på **Tilbake til SharePoint**, og deretter klikker eller trykker du på et element i SharePoint-listen. Skjemaet åpnes linjebundet til høyre i nettleservinduet.

    ![Å åpne skjemaet linjebundet i SharePoint](./media/customize-list-form/list-form-open.png)

1. Hvis du vil [tilpasse skjemaet ytterligere](sharepoint-form-integration.md), klikker eller trykker du på **Tilpass**, og gjør deretter endringene. Når du er ferdig, må du huske å lagre endringene.

    ![Tilpasse-knappen](./media/customize-list-form/customize-button.png)

    Du kan tilpasse og lagre så mange ganger du vil, men endringene vil ikke være synlige i SharePoint før du klikker eller trykker på **Publiser til SharePoint**.

## <a name="toggle-between-using-the-default-sharepoint-form-and-the-custom-form"></a>Å veksle mellom å bruke standard-SharePoint-skjemaet og det egendefinerte skjemaet

1. Fra listen i SharePoint kan du klikke eller trykke på **Innstillinger**, og deretter klikke eller trykke på **Listeinnstillinger**. Klikk eller trykk så på **Skjemainnstillinger**.

1. Klikk eller trykk på én av følgende på **Skjemainnstillinger**-siden, og deretter klikker eller trykker du på **OK**.

    * **Å bruke standard-SharePoint-skjemaet** – SharePoint bruker standard-SharePoint-skjemaet for listen.

    * **Å bruke et egendefinert skjema som er opprettet i PowerApps** – SharePoint bruker skjemaet som du tilpasset i PowerApps. (Du kan eventuelt publisere skjemaet på nytt fra **Lagre**-siden i PowerApps Studio for nett.)

    Du kan veksle frem og tilbake mellom alternativer etter behov.

    ![Alternativer for skjemainnstillinger](./media/customize-list-form/form-settings.png)

## <a name="delete-the-custom-list-form"></a>Å slette det egendefinerte listeskjemaet

1. Fra listen i SharePoint kan du klikke eller trykke på **Innstillinger**, og deretter klikke eller trykke på **Listeinnstillinger**. Klikk eller trykk så på **Skjemainnstillinger**.

1. På **Skjemainnstillinger**-siden klikker eller trykker du på **Bruk standard-SharePoint-skjemaet**, og deretter klikker eller trykker du på **Slett standardskjema** under **Bruk et egendefinert skjema som er opprettet i PowerApps**. Dette vil slette det egendefinerte skjemaet som du opprettet i PowerApps, og skjemaet vil gå tilbake til å være et standard SharePoint-skjema.

    ![Å slette det egendefinerte skjemaet](./media/customize-list-form/use-default-sharepoint.png)

## <a name="top-questions-about-list-form-customization"></a>De vanligste spørsmålene om tilpasning av listeskjema

### <a name="customizing-forms-versus-creating-apps"></a>Tilpasning av skjemaer sammenlignet med å lage apper

**Spørsmål:** Hvordan skiller et tilpasset listeskjema seg fra en frittstående app som jeg oppretter fra SharePoint eller PowerApps?

**Svar:** Listeskjema-appen som du opprettet fra SharePoint er en spesiell type PowerApps-app som bare kan brukes i en SharePoint-liste. Disse listeskjema-appene vises ikke i applisten i PowerApps Studio for nett eller PowerApps Mobile, og du kan ikke kjøre dem andre steder enn i SharePoint-listen.

**Spørsmål:** Når bør jeg opprette et egendefinert listeskjema, og når bør jeg opprette en frittstående app?

**Svar:** Hvis du vil at brukerne skal få tilgang til skjemaet ved hjelp av SharePoint, og du ønsker å tilpasse hvordan de oppretter, viser eller redigerer listeelementer, foreslår vi at du oppretter et egendefinert listeskjema fra SharePoint. Hvis du vil opprette en fullstendig tilpasset opplevelse for brukerne som de kan bruke uavhengig av SharePoint-området, anbefaler vi du oppretter en frittstående app.

**Spørsmål:** Kan jeg tilpasse et listeskjema og opprette en frittstående app for den samme listen?

**Svar:** Ja. Frittstående apper og egendefinerte listeskjemaer er uavhengige av hverandre. Du kan tilpasse og administrere dem enkeltvis.

**Spørsmål:** Er tilpasningsfunksjonene for å tilpasse et listeskjema de samme som for å tilpasse en frittstående app?

**Svar:** Ja. Du kan [legge til og konfigurere kontroller](add-configure-controls.md), [koble til tilgjengelige datakilder](add-data-connection.md) eller [legge til dine egne datakilder](../canvas-apps/register-custom-api.md), akkurat som du kan med frittstående apper.

**Spørsmål:** Kan jeg opprette egendefinerte listeskjemaer i et annet miljø enn standardmiljøet i organisasjonen min?

**Svar:** Nei. For øyeblikket kan du bare opprette egendefinerte listeskjemaer i organisasjonens standard PowerApps-miljø. Du kan ikke opprette egendefinerte listeskjemaer i (eller overføre dem til) et annet miljø.

### <a name="managing-your-custom-list-form"></a>Å behandle det egendefinerte listeskjemaet

**Spørsmål:** Hvordan får jeg en direkte kobling til listeskjemaet mitt som jeg kan dele med andre?

**Svar:** Åpne skjemaet i SharePoint-listen, og klikk eller trykk deretter på **Kopier kobling**.

**Spørsmål:** Kan jeg oppdatere listeskjemaet uten å gjøre endringene mine synlige for andre?

**Svar:** Ja. Du kan tilpasse og lagre så mange ganger du vil, men endringene vil ikke være synlige for andre før du klikker eller trykker på **[Publiser til SharePoint](customize-list-form.md#save-and-publish-the-list-form-back-to-sharepoint)**.

**Spørsmål:** Kan jeg gå tilbake til en tidligere versjon hvis jeg gjør en feil når jeg tilpasser listeskjemaet?

**Svar:** Ja. Hvis du gjør endringer i skjemaet og lagrer disse endringene, og deretter finner ut at du har gjort en feil, kan du gjenopprette en tidligere versjon av skjemaet ved hjelp av PowerApps:

1. Trykk eller klikk på **PowerApps** på kommandolinjen i SharePoint-listen. Deretter trykker eller klikker du på **Å tilpasse skjemaer**.

1. Klikk eller trykk på **Fil** i PowerApps Studio for nett, og klikk eller trykk deretter på **Se alle versjoner** på **Lagre**-siden. **Versjoner**-siden åpnes i en ny fane i nettleseren.

    > [!NOTE]
    > Hvis du ikke ser **Se alle versjoner**-knappen, klikker eller trykker du på **Lagre**. Knappen skal nå vises.

1. Uten å lukke **Versjoner**-siden eller nettleserfanen, går du tilbake til **Lagre**-siden i den andre nettleserfanen, klikker eller trykker på pilen øverst i venstre navigasjonsrute, og deretter klikker eller trykker du på **Tilbake til SharePoint** for å låse opp skjemaet og avslutte PowerApps Studio for nett.

1. Gå tilbake til **Versjoner**-siden i den andre nettleserfanen, finn versjonen du ønsker å gjenopprette, og klikk deretter på **Gjenopprett**.

    > [!NOTE]
    > Hvis du får en feilmelding om at gjenopprettingen mislyktes fordi skjemaet er låst av en annen bruker, må du vente til brukeren låser opp skjemaet, og prøve på nytt.

**Spørsmål:** Kan jeg flytte det egendefinerte listeskjemaet fra én liste til en annen?

**Svar:** Nei. Denne funksjonaliteten støttes ikke.

### <a name="administering-custom-list-forms"></a>Administrasjon av egendefinerte listeskjemaer

**Spørsmål:** Hvordan kan jeg dele det egendefinerte listeskjemaet med andre?

**Svar:** Du trenger ikke å dele skjemaet – skjemaet arver tillatelser fra SharePoint-listen. Når du er ferdig med å tilpasse det, [publiserer du det bare tilbake til SharePoint](customize-list-form.md#save-and-publish-the-list-form-back-to-sharepoint) slik at andre kan bruke det.

**Spørsmål:** Hvem kan tilpasse listeskjemaer?

**Svar:** Alle med SharePoint-tillatelser til å administrere, utforme eller redigere den tilhørende listen.

**Spørsmål:** Trenger jeg en PowerApps-lisens for å opprette eller bruke egendefinerte listeskjemaer?

**Svar:** Hvis du har noen [Office 365-abonnementer som inkluderer PowerApps](../../administrator/pricing-billing-skus.md#licenses), kan du opprette eller bruke egendefinerte listeskjemaer.

**Spørsmål:** Hva skjer når gjestebrukere har tilgang til en liste som har et egendefinert skjema?

**Svar:** Gjestebrukere får en feilmelding hvis de prøver å få tilgang til et listeskjema som er blitt tilpasset ved hjelp av PowerApps.

**Spørsmål:** Hvordan får jeg som administrator en liste over alle tilpassede skjemaer i min organisasjon?

**Svar:** Hvis du er tenant-administrator for PowerApps eller har administratortillatelser i standardmiljøet for PowerApps i organisasjonen, gjør du følgende:

1. Gå til [Administrasjonssenteret for PowerApps](https://admin.powerapps.com), og velg standardmiljøet for organisasjonen fra listen over miljøer.

1. Øverst på siden for standardmiljø klikker eller trykker du på **Ressurser**.

1. Se etter apper med en **SharePoint-skjema**-apptype fra listen over apper – dette er de tilpassede skjemaene.

    ![Liste over egendefinerte skjemaer](./media/customize-list-form/all-customized-forms.png)
