---
title: Slik oppretter du en regel i Microsoft Docs
description: Trinnvise instruksjoner for bygging av app-logikken ved oppretting av regler
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 11/10/2017
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 4a3682a913dbbdf0c1848378dad9ab06ccc78aaf
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/23/2019
ms.locfileid: "61557231"
---
# <a name="create-a-rule-in-powerapps"></a>Slik oppretter du en regel i PowerApps
Opprett regler for å automatisk endre en app som er basert på vilkår du angir. Du kan for eksempel vise listeelementer i rødt, gult eller grønt, basert på status, eller vise en knapp for godkjenning bare for enkelte brukere (for eksempel ledere).

Du kan legge til regler i en rekke kontroller. Legg til en regel for å endre tekstfargen for en **Etikett**-kontroll i dette emnet, hvis verdien for en **Glidebryter**-kontroll er større enn 70.

## <a name="add-a-rule"></a>Slik legger du til en regel
1. Velg en kontroll (eller legg til en kontroll og la den være valgt).

    [Legg til en etikett og en glidebryter](add-configure-controls.md) for dette emnet. Angi etiketten sin **Tekst**-egenskap til **Slider1.Value**, og velg deretter glidebryteren.

1. Klikk i det høyre panelet, eller trykk på **Regler**, og klikk eller trykk på **Ny regel**.

    ![Oppretting av en ny regel](./media/working-with-rules/new-rule.png)

    Hvis du velger en kontroll der én eller flere regler allerede er definert, kan du redigere dem, hvis du klikker eller trykker på den.  

## <a name="add-a-condition"></a>Slik legger du til en betingelse
En betingelse er et uttrykk som returneres til sann eller usann, for eksempel om en verdi er større enn 70. Du kan skrive uttrykket basert på en mal, eller starte fra grunnen av, og du kan tilpasse uttrykket basert på veiledning i brukergrensesnittet (Intellisense).

1. Klikk eller trykk på **Legg til en betingelse**, og klikk deretter på en mal, eller en **Egendefinert betingelse**.

    Klikk eller trykk på **Større enn**, for dette emnet.

    ![Slik legger du til en betingelse](./media/working-with-rules/rule-conditions.png)

1. Oppdater uttrykket for å definere når regelen skal gjelde.

    For dette emnet, kan du endre 0 til 70 for å få dette uttrykket:  <br>**Slider1.Value > 70**

## <a name="add-an-action"></a>Slik legger du til en handling
Handlinger definerer hva som skjer når regelen brukes. PowerApps kan opprette handlinger automatisk, basert på endringer du gjør i kontroller.

1. Klikk eller trykk på **Definer handlinger**.

    ![Definering av handlinger](./media/working-with-rules/rule-define-actions.png)

1. Klikk eller trykk på **La oss sette i gang** i bekreftelsesdialogboksen, slik at PowerApps vil fange opp neste endring, eller endringer, som én eller flere handlinger.

1. Konfigurer én eller flere kontroller, for å samsvare med forventningene når betingelsen er sann.

    Endre etikettfargen for dette emnet.

    ![Slik fanger du opp egenskaper](./media/working-with-rules/rule-capture-properties.png)

1. Se gjennom endringene ved å klikke eller trykke på **Vis handlinger** (valgfritt).

    ![Se gjennom handlinger](./media/working-with-rules/rule-review-actions.png)

1. Klikk eller trykk på **Fullført**, når du er ferdig med å legge til handlinger.

1. Se gjennom betingelsen og handlinger for regelen.

    ![Se gjennom regel](./media/working-with-rules/rule-review.png)

## <a name="rename-the-rule"></a>Gi nytt navn til regelen

1. Hold pekeren over **Rule1**, og klikk eller trykk på Rediger-knappen.

    ![Hold pekeren over navnet på en regel](./media/working-with-rules/hover-over-rules_name.png)

1. Angi et nytt navn for regelen.

    ![Gi regelen et nytt navn](./media/working-with-rules/rename-rule.png)

1. Klikk eller trykk på **Ferdig** for å lukke redigeringsprogrammet.

## <a name="test-the-rule"></a>Testing av regelen
1. Forhåndsvis appen ved å trykke på F5 (eller ved å klikke på Avspillingsknappen nær øvre høyre hjørne).

    ![Åpner forhåndsvisningen](./media/working-with-rules/open-preview.png)

1. Angi betingelsen du spesifiserte som sann, og bekrefter deretter at handlingene fungerer som forventet.

    Angi en verdi som er større enn 70 for glidebryteren for dette emnet, og bekreft at etikett-teksten endrer farge.

## <a name="see-all-rules"></a>Se alle regler
**Regler**-fanen viser bare reglene for den merkede kontrollen og alle underordnede kontroller som brukes i en regelbetingelse, eller handling, som standard. Hvis du vil vise alle reglene i appen, kan du tømme avmerkingsboksen for **Vis regler for bare denne kontrollen**.

![Fjern filter](./media/working-with-rules/rules-filter.png)

## <a name="known-limitations"></a>Kjente begrensninger
I skrivende stund:

* Du kan ikke angi **ThisItem**-egenskapen for et skjema eller et galleri, som en del av en betingelse.
