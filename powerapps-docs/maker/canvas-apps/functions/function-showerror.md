---
title: ShowError-funksjonen i Microsoft Docs
description: Referanseinformasjon for ShowError-funksjonen i PowerApps, inkludert syntaks og eksempler
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 06/05/2018
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 5e18b64910bbc7efca8c460100163e1a0716a089
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71992143"
---
# <a name="notify-function-in-powerapps"></a>Funksjonen Notify i PowerApps
Viser en bannermelding til brukeren.

## <a name="description"></a>Beskrivelse
**Notify**-funksjonen viser en bannermelding til brukeren øverst i skjermen, overlappende med det som vises for øyeblikket.  

Passende farge og ikon brukes avhengig av type melding.   Typen er angitt av det andre argumentet til funksjonen:

| NotificationType-argumentet | Beskrivelse |
| --- | --- |
| **NotificationType.Error** | Viser meldingen som en feil. |
| **NotificationType.Information** (standard) | Viser meldingen som informativ.  |
| **NotificationType.Success** | Viser meldingen som fullført. |
| **NotificationType.Warning** | Viser meldingen som en advarsel. |

Meldinger vises både når du redigerer appen og når sluttbrukerne bruker appen.

**Notify** kan bare brukes i [formler for virkemåte](../working-with-formulas-in-depth.md).

**Notify** kan pares med [**IfError**](function-iferror.md)-funksjonen for å oppdage og rapportere feil med en tilpasset feilmelding.

PowerApps kan også sende push-varslinger ved hjelp av en helt annen mekanisme fra **Notify**.  Hvis du vil ha mer informasjon, kan du se [Å sende et varsel i PowerApps](../add-notifications.md).

**Notify** returnerer alltid *sann*.

Debetnotaforslag Denne funksjonen har tidligere fått navnet **ShowError** når den bare kunne vise feil meldinger.

## <a name="syntax"></a>Syntaks
**Notify**( *Message*, [ *NotificationType* ] )

* *Melding* – obligatorisk.  Meldingen som skal vises til brukeren.
* *NotificationType* – valgfritt.  Type melding som skal vises fra tabellen ovenfor.  **NotificationType.Information** (standard).  

## <a name="examples"></a>Eksempler

### <a name="step-by-step"></a>Trinn for trinn

1. Legg til en **Knapp**-kontroll på skjermen.

2. Angi **OnSelect**-egenskapen for **knappen** til:

    **Notify( "Hello, World" )**

3. Klikk eller trykk på knappen.  

    Hver gang knappen trykkes på, vises **Hello, World** til brukeren (informativt).

    ![I redigeringsmiljøet vil Button.OnSelect, oppkalle Notify og vise den resulterende Hello, World-meldingen som en rød bannermelding for brukeren](media/function-showerror/hello-world.png)

4. Endre typen melding for å angi en feil.  Legg til et annet argument til formelen:

    **Notify ("Hello, World", NotificationType.Error)**

5. Klikk eller trykk på knappen.

    Hver gang knappen trykkes på, vises meldingen **Hello, World** til brukeren, som en feil.

    ![I redigeringsmiljøet vil Button.OnSelect, oppkalle Notify og vise den resulterende Hello, World-meldingen som en rød bannermelding for brukeren](media/function-showerror/hello-world-error.png)

4. Endre typen melding for å angi en advarsel.  Endre det andre argumentet i formelen:

    **Notify ("Hello, World", NotificationType.Warning)**

5. Klikk eller trykk på knappen.

    Hver gang knappen trykkes på, vises nå meldingen **Hello, World** til brukeren, som en advarsel.

    ![I redigeringsmiljøet vil Button.OnSelect, oppkalle Notify og vise den resulterende Hello, World-meldingen som en rød bannermelding for brukeren](media/function-showerror/hello-world-warning.png)

4. Endre typen melding for å angi vellykket prosess.  Endre det andre argumentet i formelen:

    **Notify ("Hello, World", NotificationType.Success)**

5. Klikk eller trykk på knappen.

    Hver gang knappen trykkes på, vises nå meldingen **Hello, World** til brukeren, som en vellykket prosess.

    ![I redigeringsmiljøet vil Button.OnSelect, oppkalle Notify og vise den resulterende Hello, World-meldingen som en rød bannermelding for brukeren](media/function-showerror/hello-world-success.png)
