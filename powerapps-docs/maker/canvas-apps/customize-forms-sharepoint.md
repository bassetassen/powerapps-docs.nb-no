---
title: Å tilpasse skjemaer | Microsoft Docs
description: Angi hvilke data som skal vises, i hvilken rekkefølge de skal vises og i hvilke kontroller.
author: AFTOwen
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 03/17/2018
ms.author: anneta
ms.openlocfilehash: aefe350c2294f9d8cbae32eee1db1f600c8a65da
ms.sourcegitcommit: 0e9af8cace2bdc04750f4c5a70a3c4af8e3d2292
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/22/2018
ms.locfileid: "39195109"
---
# <a name="customize-forms-in-powerapps"></a>Å tilpasse skjemaer i PowerApps
Tilpass en **visningsskjema**-kontroll og en **redigeringsskjema**-kontroll slik at de viser dataene som er viktigst i den mest intuitive rekkefølgen, for å hjelpe brukere å forstå og oppdatere dataene.

Hvert skjema består av ett eller flere kort, som viser data fra en bestemt kolonne i datakilden. Ved å følge trinnene i dette emnet kan du angi hvilke kort som skal vises i et skjema og flytte kortene opp og ned innenfor et skjema.

Hvis du ikke allerede er kjent med PowerApps, kan du se [Introduksjon til PowerApps](getting-started.md).

## <a name="prerequisites"></a>Forutsetninger
[Å genere en app](data-platform-create-app.md) fra Common Data Service, og deretter [tilpasse galleriet](customize-layout-sharepoint.md) i denne appen.

## <a name="show-and-hide-cards"></a>Å vise og skjule kort
1. Logg deg på [PowerApps](http://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).

    ![Hjemmesiden for PowerApps-området](./media/customize-forms-sharepoint/sign-in.png)


1. Åpne appen du har generert og tilpasset.

1. I det venstre navigasjonsfeltet skriver eller limer du inn **D** i søkefeltet for å filtrere listen over elementer, og deretter klikker eller trykker du på **DetailForm1** for å merke den.

    ![Slik velger du detaljskjermbilde](./media/customize-forms-sharepoint/select-detailform.png)

1. I den høyre ruten klikker du på **Kontoer** for å vise **Data**-ruten.

    ![Å vise datarute](./media/customize-forms-sharepoint/show-data-pane.png)

1. Fjern merket for **Primærkontakt**, **Beskrivelse** og **Adresse 1: Gate/vei 2** for å skjule disse feltene i **Data**-ruten.

    ![Liste over felt](./media/customize-forms-sharepoint/hide-fields.png)

1.  Merk av for **Adresse 1: Postnummer** i avmerkingsboksen i **Data**-ruten.

    ![Liste over felt](./media/customize-forms-sharepoint/show-field.png)

## <a name="reorder-the-cards"></a>Å endre rekkefølgen på kortene
1. Dra **Kontonavn**-feltet til toppen av listen over felt i **Data**-ruten.

    ![Å flytte kort](./media/customize-forms-sharepoint/move-card.png)

    Kortene i **DetailForm1** gjenspeiler den samme endringen.

    ![Omorganiserte kort](./media/customize-forms-sharepoint/reordered-card.png)

1. Endre rekkefølgen på de andre kortene i denne sekvensen:

    - Kontonavn
    - Adresse 1: Gate 1
    - Adresse 1: Poststed
    - Adresse 1: Postnummer
    - Antall ansatte
    - Årlig omsetning

1. I det venstre navigasjonsfeltet skriver eller limer du inn **Ed** i søkefeltet for å filtrere listen over elementer, og deretter klikker eller trykker du på **EditForm1** for å velge den.

1. Gjenta trinnene i fremgangsmåten ovenfor og i denne, slik at feltene i **EditForm1** samsvarer med dem i **DetailForm1**.

## <a name="run-the-app"></a>Å kjøre appen
1. I det venstre navigasjonsfeltet skriver eller limer du inn **Br** for å filtrere listen, og deretter klikker eller trykker du på **BrowseScreen1** for å merke den.

2. Åpne forhåndsvisningsmodus ved å trykke på F5 (eller ved å velge **Forhåndsvisning**-ikonet nær hjørnet øverst til høyre).

    ![Forhåndsvisningsikonet](./media/customize-forms-sharepoint/open-preview.png)

3. Klikk eller trykk på pluss-ikonet i hjørnet øverst til høyre for å legge til en post i **EditScreen1**.

    ![Å legge til post](./media/customize-forms-sharepoint/add-record.png)

4. Legg til de dataene du vil bruke, og klikk eller trykk på hakeikonet i øvre høyre hjørne for å lagre endringene og gå tilbake til **BrowseScreen1**.

    ![Å lagre poster](./media/customize-forms-sharepoint/save-record.png)

5. Klikk eller trykk på pilen til elementet du nettopp opprettet, for å vise detaljer om elementet i **DetailScreen1**.  

    ![Høyrepil](./media/customize-forms-sharepoint/right-arrow.png)

6. Klikk eller trykk på plussikonet i hjørnet øverst til høyre for å oppdatere posten i **EditScreen1**.

    ![Å redigere poster](./media/customize-forms-sharepoint/edit-record.png)

7. Endre informasjonen i ett eller flere felter. Klikk eller trykk deretter på haken i hjørnet øverst til høyre for å lagre endringene i SharePoint-listen og gå tilbake til **DetailScreen1**.  

    ![Å lagre endringer](./media/customize-forms-sharepoint/save-record.png)

8. Klikk eller trykk på papirkurv-ikonet nær hjørnet øverst til høyre for å slette posten du nettopp oppdaterte og gå tilbake til **BrowseScreen1**.

    ![Å slette poster](./media/customize-forms-sharepoint/delete-record.png)

9. Lukk Forhåndsvisningsmodus ved å trykke på ESC (eller ved å klikke eller trykke på lukkeikonet nær øvre venstre hjørne).

## <a name="next-steps"></a>Neste trinn
- [Å lagre og publisere](save-publish-app.md) appen.
- [Å tilpasse et kort](customize-card.md) i appen.
