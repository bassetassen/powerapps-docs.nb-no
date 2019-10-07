---
title: Start en flyt i en lerretsapp | Microsoft Docs
description: Opprett en flyt som utfører en eller flere oppgaver etter en hendelse som forekommer i en lerretsapp, for eksempel at en bruker velger en knapp.
author: stepsic-microsoft-com
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 12/07/2018
ms.author: stepsic
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 1e5c90fcc6e4f8d4c8e1d73eadc9a31fdbfe48ef
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71988312"
---
# <a name="start-a-flow-in-a-canvas-app"></a>Start en flyt i en lerretsapp

Du kan bruke Microsoft Flow til å opprette logikk som utfører én eller flere oppgaver når en hendelse forekommer i en lerretsapp. Du kan for eksempel konfigurere en knapp slik at når en bruker velger den, opprettes et element i en SharePoint-liste, en e-postmelding eller møteinvitasjon sendes, en fil legges til i skyen, eller alt dette. Du kan konfigurere en kontroll i appen for å starte flyten, som fortsetter å kjøre selv om du lukker PowerApps.

> [!NOTE]
> Når en bruker kjører en flyt i en app, må denne brukeren ha tillatelse til å utføre oppgavene som er angitt i flyten. Hvis ikke, vil flyten mislykkes.

## <a name="prerequisites"></a>Forutsetninger

- [Registrer deg](../signup-for-powerapps.md) for PowerApps.
- Finn ut hvordan du kan [konfigurere en kontroll](add-configure-controls.md).

## <a name="create-a-flow"></a>Å opprette en flyt

1. Logg deg på [PowerApps](http://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).

1. Velg **forretningslogikk**i navigasjons feltet til venstre, og velg deretter **flyter**.

1. Velg **ny**i hjørnet øverst til venstre på **mine flyter** -siden, og velg deretter **Opprett fra Tom**.

    ![Alternativ for å opprette en flyt uten å bruke en mal](./media/using-logic-flows/create-from-blank.png)

1. Velg **Søk i hundrevis av tilkoblinger og utløsere**nederst på siden som vises.

1. Skriv inn **powerapps**i søke boksen, og velg deretter **powerapps** -ikonet.

    ![Opprett en PowerApps-utløser](./media/using-logic-flows/set-trigger.png)
    
1. Velg PowerApps-ikonet på neste side, og velg deretter **nytt trinn**.

1. Angi en handling for flyten i boksen som gir **søke koblinger og handlinger**, som i dette eksemplet:

   1. Skriv inn **SharePoint** i boksen, og velg deretter **Opprett element** i listen under **handlinger**.

       ![Alternativ for å opprette et SharePoint-element](./media/using-logic-flows/create-sharepoint-item.png)

   1. Hvis du blir bedt om det, kan du angi legitimasjon for å koble til SharePoint.

   1. I **Områdeadresse**-boksen skriver eller limer du inn nettadressen til et SharePoint-område som inneholder en liste.

       > [!NOTE]
       > Ikke Tilføy navnet på listen til Netta dressen.

   1. Angi listen du vil bruke, i **liste navn** -boksen.
   
       ![Angi liste](./media/using-logic-flows/list-fields.png)

   1. Velg inn data boksen for et felt i listen (for eksempel **Tittel**), velg **se mer** i dynamisk innhold-ruten, og velg deretter **spør i powerapps**. 

       ![Å legge til Ask i PowerApps-parameteren i Tittel-feltet](./media/using-logic-flows/ask-in-powerapps.png)

1. valg fritt Angi ett eller flere tilleggs trinn, for eksempel sende godkjenning av e-post til en adresse du angir, eller opprette en relatert oppføring i en annen data kilde.

1. Skriv eller lim inn et navn for flyten nær hjørnet øverst til venstre, og velg deretter **Lagre** nær hjørnet øverst til høyre.

## <a name="add-a-flow-to-an-app"></a>Å legge til en flyt i en app
1. Velg **Opprett**i navigasjons feltet til venstre.

1. Beveg pekeren over **lerretet fra en tom** flis, og velg deretter **gjør denne appen**.

1. Legg til en **[Tekstinndata](controls/control-text-input.md)** -kontroll, og gi den navnet **RecordTitle**.

1. Legg til en **[Knapp](controls/control-button.md)** -kontroll, og flytt den under **RecordTitle**.

1. Velg **Flyter** på **Handlinger**-fanen, med **[Knapp](controls/control-button.md)** -kontrollen valgt.

    ![Alternativer for flyter på Handlinger-fanen](./media/using-logic-flows/action-tab.png)

1. Velg flyten som du opprettet i forrige trinn, i ruten som vises.

    > [!NOTE]
   > Hvis flyten du opprettet ikke er tilgjengelig, må du kontrollere om PowerApps er satt til miljøet som du opprettet flyten i.

    ![Å legge til en flyt fra tilpassingsruten](./media/using-logic-flows/add-flow-from-pane.png)

1. Skriv eller lim inn **RecordTitle.Text)** i formellinjen på slutten av formelen som automatisk har blitt lagt til.

    ![OnSelect-egenskap, som inkluderer flyten](./media/using-logic-flows/onselect-with-flow.png)

## <a name="test-the-flow"></a>Å teste flyten
1. Dobbelt klikk **tekst inn data** -kontrollen, og skriv eller lim inn tekst i den.

1. Velg **[knapp](controls/control-button.md)** -kontrollen mens du holder nede Alt-tasten.

    Det opprettes et SharePoint-element i listen som du har angitt, med teksten du har angitt som tittel. Hvis listen var åpen da flyten ble kjørt, må du kanskje oppdatere nettleseren for å vise endringene.
