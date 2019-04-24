---
title: Start en flyt i en lerretsapp | Microsoft Docs
description: Opprett en flyt som utfører en eller flere oppgaver etter en hendelse som forekommer i en lerretsapp, for eksempel at en bruker velger en knapp.
author: stepsic-microsoft-com
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 12/07/2018
ms.author: stepsic
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 5439399a22b47fcf4195cf878208e0e0bd4e0764
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/23/2019
ms.locfileid: "61532115"
---
# <a name="start-a-flow-in-a-canvas-app"></a>Start en flyt i en lerretsapp

Du kan bruke Microsoft Flow til å opprette logikk som utfører én eller flere oppgaver når en hendelse forekommer i en lerretsapp. Du kan for eksempel konfigurere en knapp slik at når en bruker velger den, opprettes et element i en SharePoint-liste, en e-postmelding eller møteinvitasjon sendes, en fil legges til i skyen, eller alt dette. Du kan konfigurere en kontroll i appen for å starte flyten, som fortsetter å kjøre selv om du lukker PowerApps.

> [!NOTE]
> Når en bruker kjører en flyt fra innenfor en app, må brukeren ha tillatelse til å utføre oppgaver som er angitt i flyten. Ellers vil flyten mislykkes.

## <a name="prerequisites"></a>Forutsetninger

- [Registrer deg](../signup-for-powerapps.md) for PowerApps.
- Finn ut hvordan du kan [konfigurere en kontroll](add-configure-controls.md).

## <a name="create-a-flow"></a>Å opprette en flyt

1. Logg deg på [PowerApps](http://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).

1. I navigasjonsfeltet til venstre velger du **forretningslogikk**, og velg deretter **flyter**.

1. I hjørnet øverst til venstre i den **Mine flyter** velger **ny**, og velg deretter **Opprett fra tom**.

    ![Alternativ for å opprette en flyt uten å bruke en mal](./media/using-logic-flows/create-from-blank.png)

1. Nær bunnen av siden som vises, velger **Søk hundrevis av koblinger og utløsere**.

1. Skriv inn i søkeboksen, **PowerApps**, og velg deretter den **PowerApps** ikonet.

    ![Opprette en PowerApps-utløser](./media/using-logic-flows/set-trigger.png)
    
1. På neste side, velger du ikonet PowerApps på nytt, og velg deretter **nytt trinn**.

1. I boksen som heter **Søk i koblinger og handlinger**, angi en handling for flyten, som i dette eksemplet:

   1. Typen **SharePoint** i boksen, og velg deretter **Opprett element** i listen under **handlinger**.

       ![Alternativ for å opprette et SharePoint-element](./media/using-logic-flows/create-sharepoint-item.png)

   1. Hvis du blir bedt om det, kan du angi legitimasjon for å koble til SharePoint.

   1. I **Områdeadresse**-boksen skriver eller limer du inn nettadressen til et SharePoint-område som inneholder en liste.

       > [!NOTE]
       > Ikke Legg til navnet på listen i URL-adressen.

   1. I den **listenavnet** angir listen som du vil bruke.
   
       ![Angi liste](./media/using-logic-flows/list-fields.png)

   1. Velg tekstinndata-boksen for et felt i listen (som **tittel**), og velg **se mer** i dynamisk innhold-ruten, og velg deretter **spør i PowerApps**. 

       ![Å legge til Ask i PowerApps-parameteren i Tittel-feltet](./media/using-logic-flows/ask-in-powerapps.png)

1. (valgfritt) Angi én eller flere flere trinn, for eksempel sende e-post for godkjenning til en adresse du angir, eller opprette en relatert post i en annen datakilde.

1. Nær hjørnet øverst til venstre, Skriv eller Lim inn et navn for flyten, og velg deretter **lagre** nær hjørnet øverst til høyre.

## <a name="add-a-flow-to-an-app"></a>Å legge til en flyt i en app
1. I navigasjonsfeltet til venstre velger du **Opprett**.

1. Hold pekeren over den **lerretsapp fra tom** side ved side, og velg deretter **lag denne appen**.

1. Legg til en **[Tekstinndata](controls/control-text-input.md)**-kontroll, og gi den navnet **RecordTitle**.

1. Legg til en **[Knapp](controls/control-button.md)**-kontroll, og flytt den under **RecordTitle**.

1. Velg **Flyter** på **Handlinger**-fanen, med **[Knapp](controls/control-button.md)**-kontrollen valgt.

    ![Alternativer for flyter på Handlinger-fanen](./media/using-logic-flows/action-tab.png)

1. Velg flyten som du opprettet i forrige trinn, i ruten som vises.

    > [!NOTE]
   > Hvis flyten du opprettet ikke er tilgjengelig, må du kontrollere om PowerApps er satt til miljøet som du opprettet flyten i.

    ![Å legge til en flyt fra tilpassingsruten](./media/using-logic-flows/add-flow-from-pane.png)

1. Skriv eller lim inn **RecordTitle.Text)** i formellinjen på slutten av formelen som automatisk har blitt lagt til.

    ![OnSelect-egenskap, som inkluderer flyten](./media/using-logic-flows/onselect-with-flow.png)

## <a name="test-the-flow"></a>Å teste flyten
1. Dobbeltklikk den **tekstinndata** kontrollen, og Skriv inn eller lime inn tekst i den.

1. Mens du holder nede Alt-tasten, velg den **[knappen](controls/control-button.md)** kontroll.

    Et SharePoint-element er opprettet i listen som du har angitt med teksten at du har angitt som tittel. Hvis listen var åpen da flyten ble kjørt, må du kanskje oppdatere nettleseren for å vise endringene.
