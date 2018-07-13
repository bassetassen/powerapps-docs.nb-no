---
title: Å starte en flyt i en app i Microsoft Docs
description: Opprett en flyt som utfører én eller flere oppgaver etter en hendelse som forekommer i en app, for eksempel at en bruker velger en knapp.
documentationcenter: ''
author: stepsic-microsoft-com
manager: kfile
editor: ''
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: canvas
ms.date: 06/05/2017
ms.author: sharik
ms.openlocfilehash: 7079dc6194361cc700ccaad6c02ca0bcf8a9f9d6
ms.sourcegitcommit: 79b8842fb0f766a0476dae9a537a342c8d81d3b3
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/07/2018
ms.locfileid: "37895918"
---
# <a name="start-a-flow-in-an-app"></a>Å starte en flyt i en app
Du kan bruke Microsoft Flow til å opprette logikk som utfører én eller flere oppgaver når en hendelse forekommer i en app. Du kan for eksempel konfigurere en knapp slik at når en bruker velger den, opprettes et element i en SharePoint-liste, en e-postmelding eller møteinvitasjon sendes, en fil legges til i skyen, eller alt dette. Du kan konfigurere en kontroll i appen for å starte flyten, som fortsetter å kjøre selv om du lukker PowerApps.

## <a name="prerequisites"></a>Forutsetninger

* [Registrer deg](../signup-for-powerapps.md) for PowerApps.
* Finn ut hvordan du kan [konfigurere en kontroll](add-configure-controls.md).

## <a name="create-a-flow"></a>Å opprette en flyt
1. Logg deg på [powerapps.com](http://web.powerapps.com), og klikk eller trykk deretter på **Flyter** i navigasjonsfeltet til venstre.

2. Velg **Opprett fra tom** på **Mine flyter**-siden.

    ![Alternativ for å opprette en flyt uten å bruke en mal](./media/using-logic-flows/create-from-blank.png)

    **PowerApps** er lagt til som standardutløser.

    ![PowerApps som utløseren som starter flyten](./media/using-logic-flows/set-trigger.png)

3. Velg **Nytt trinn**, og velg deretter **Legg til en handling**.

    ![Alternativ for å legge til en handling](./media/using-logic-flows/add-action.png)

4. Angi en handling for flyten i boksen som heter **Søk i alle tjenester og handlinger**, som i dette eksemplet:

   1. Skriv inn **SharePoint** i boksen, og velg deretter **SharePoint – opprett element** i listen under **Handlinger**.

       ![Alternativ for å opprette et SharePoint-element](./media/using-logic-flows/create-sharepoint-item.png)

   2. Hvis du blir bedt om det, kan du angi legitimasjon for å koble til SharePoint.

   3. I **Områdeadresse**-boksen skriver eller limer du inn nettadressen til et SharePoint-område som inneholder en liste.

       > [!NOTE]
      > Angi nettadressen for området som ikke inkludert i listen.

   4. I **Listenavn**-boksen merker du listen som du vil bruke.

   5. Klikk eller trykk på **Tittel**-boksen, og velg deretter **Legg til dynamisk innhold**.

       ![Å legge til Ask i PowerApps-parameteren i Tittel-feltet](./media/using-logic-flows/ask-in-powerapps.png)

   6. Velg **Spør i PowerApps** i listen over parametere.

       ![Å legge til parameter](./media/using-logic-flows/add-parameter.png)

5. (valgfritt) Angi én eller flere ytterligere handlinger, for eksempel å sende e-post for godkjenning til en adresse du angir, eller å opprette en relatert post i en annen datakilde.

6. Nær toppen av skjermen skriver eller limer du inn et navn for flyten, og deretter velger du **Opprett flyt**.

    ![Å navngi og lagre flyten](./media/using-logic-flows/name-flow.png)

## <a name="add-a-flow-to-an-app"></a>Å legge til en flyt i en app
1. I PowerApps velger du **Ny** i **Fil**-menyen.

2. Velg **Telefonoppsett** på **Tom app**-flisen.

3. Legg til en **[Tekstinndata](controls/control-text-input.md)**-kontroll, og gi den navnet **RecordTitle**.

4. Legg til en **[Knapp](controls/control-button.md)**-kontroll, og flytt den under **RecordTitle**.

5. Velg **Flyter** på **Handlinger**-fanen, med **[Knapp](controls/control-button.md)**-kontrollen valgt.

    ![Alternativer for flyter på Handlinger-fanen](./media/using-logic-flows/action-tab.png)

6. Velg flyten som du opprettet i forrige trinn, i ruten som vises.

    > [!NOTE]
   > Hvis flyten du opprettet ikke er tilgjengelig, må du kontrollere om PowerApps er satt til miljøet som du opprettet flyten i.

    ![Å legge til en flyt fra tilpassingsruten](./media/using-logic-flows/add-flow-from-pane.png)

7. Skriv eller lim inn **RecordTitle.Text)** i formellinjen på slutten av formelen som automatisk har blitt lagt til.

    ![OnSelect-egenskap, som inkluderer flyten](./media/using-logic-flows/onselect-with-flow.png)

## <a name="test-the-flow"></a>Å teste flyten
1. Åpne forhåndsvisningsmodus ved å trykke på F5 (eller ved å velge pilen nær det øvre høyre hjørnet).

    ![OnSelect-egenskap, som inkluderer flyten](./media/using-logic-flows/open-preview.png)

2. Skriv eller lim inn tekst i **RecordTitle**, og klikk eller trykk på **[Knapp](controls/control-button.md)**-kontrollen.

    Et SharePoint-element er opprettet i listen du har angitt, med teksten har angitt som tittel. Hvis listen var åpen da flyten ble kjørt, må du kanskje oppdatere nettleseren for å vise endringene.
