---
title: Formler for virkemåte for komponenter | Microsoft Docs
description: Utløs en app for å utføre en eller flere oppgaver når det oppstår en komponentbaserte handling.
author: yifwang
ms.service: powerapps
ms.topic: article
ms.date: 05/24/2019
ms.author: yifwang
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 7275395a4c21afaebc60e9635461afc08f5e84a0
ms.sourcegitcommit: afe958805d8e1cfa4fdf02c7bceea947185f71f2
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 05/30/2019
ms.locfileid: "66420318"
---
# <a name="behavior-formulas-for-components"></a>Formler for virkemåte for komponenter

> [!IMPORTANT]
> Denne funksjonen er fremdeles eksperimentell og deaktivert som standard. Hvis du vil ha mer informasjon, se [Experimental og forhåndsvisning av funksjoner](working-with-experimental.md).

Angi én eller flere [formler for virkemåte](working-with-formulas-in-depth.md) som kjøres når en hendelse utløser en endring i komponentforekomster. Angi for eksempel en komponent **OnReset** egenskapen til én eller flere formler som utfører initialisering, fjerner du inndata og tilbakestille verdiene når den **tilbakestille** funksjonen kjører på komponentforekomster.

## <a name="onreset"></a>OnReset ##

Med en komponent som er valgt, velger **OnReset** i rullegardinlisten for egenskaper (på høyre side av formellinjen), og skriv deretter inn én eller flere formler.

> [!div class="mx-imgBorder"]
> ![OnReset eksempel](./media/component-behavior/example-onreset.png)

Å teste **OnReset**, konfigurere en kontroll for å tilbakestille komponenten. For eksempel angi den **OnSelect** egenskapen for en knapp til denne formelen: **Tilbakestill**(*ComponentName*)

> [!div class="mx-imgBorder"]
> ![Tilbakestill-knappen](./media/component-behavior/reset-button.png)
