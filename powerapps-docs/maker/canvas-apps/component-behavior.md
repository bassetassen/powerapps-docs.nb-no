---
title: Virke måte formler for komponenter | Microsoft Docs
description: Utløs en app for å utføre én eller flere oppgaver når en komponent BAS ert handling utføres.
author: yifwang
ms.service: powerapps
ms.topic: article
ms.date: 05/24/2019
ms.author: yifwang
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: c8ec4edd835f12fb6fccf04ba0fb27f1e755cac0
ms.sourcegitcommit: ea3ab5926541c60a9e7c17f52f937c9812d48c71
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 09/05/2019
ms.locfileid: "70310072"
---
# <a name="behavior-formulas-for-components"></a>Virke måte formler for komponenter

> [!IMPORTANT]
> Denne funksjonen er fremdeles eksperimentell og deaktivert som standard. Se [funksjonene eksperimentell og forhånds visning](working-with-experimental.md)hvis du vil ha mer informasjon.

Angi én eller flere [virke måte formler](working-with-formulas-in-depth.md) som kjøres når en hendelse utløser en endring i komponent forekomster. Du kan for eksempel angi **OnReset** -egenskapen for en komponent til én eller flere formler som utfører initialisering, slette inn data og tilbakestille verdier når funksjonen **reset** kjøres på komponent forekomstene.

## <a name="onreset"></a>OnReset

Når en komponent er valgt, velger du **OnReset** i rulle gardin listen over egenskaper (på høyre side av formel linjen), og deretter skriver du inn én eller flere formler.

> [!div class="mx-imgBorder"]
> ![OnReset, eksempel](./media/component-behavior/example-onreset.png)

Hvis du vil teste **OnReset**, må du konfigurere en kontroll for å tilbakestille komponenten. Du kan for eksempel angi **OnSelect** -egenskapen for en knapp til denne formelen: **Tilbakestill** (*ComponentName*)

> [!div class="mx-imgBorder"]
> ![Tilbakestill-knapp](./media/component-behavior/reset-button.png)
