---
title: Virke måte formler for komponenter | Microsoft Docs
description: Utløs en app for å utføre én eller flere oppgaver når en komponent BAS ert handling utføres.
author: yifwang
ms.service: powerapps
ms.topic: article
ms.date: 9/30/2019
ms.author: yifwang
ms.reviewer: tapanm
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: baf7e74581819b3ea21542f30f96a0a6f517c0d5
ms.sourcegitcommit: 60fd1792430b9f3da08ec161cb2277506d795e3a
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/01/2019
ms.locfileid: "71705039"
---
# <a name="behavior-formulas-for-components"></a>Virke måte formler for komponenter

> [!IMPORTANT]
> Denne funksjonen er fremdeles eksperimentell og deaktivert som standard. Se [funksjonene eksperimentell og forhånds visning](working-with-experimental.md)hvis du vil ha mer informasjon.

Angi én eller flere [virke måte formler](working-with-formulas-in-depth.md) som kjøres når en hendelse utløser en endring i komponent forekomster. Du kan for eksempel angi **OnReset** -egenskapen for en komponent til én eller flere formler som utfører initialisering, slette inn data og tilbakestille verdier når funksjonen **reset** kjøres på komponent forekomstene.

## <a name="onreset"></a>OnReset

Velg **OnReset** i rulle gardin listen med egenskaper (på venstre side av formel linjen), og angi deretter én eller flere formler når en overordnet komponent er valgt.

> [!div class="mx-imgBorder"]
> @no__t – 0OnReset eksempel @ no__t-1

Hvis du vil teste **OnReset**, må du konfigurere en kontroll for å tilbakestille komponenten. Du kan for eksempel angi **OnSelect** -egenskapen for en knapp til denne formelen: **Tilbakestill**(*ComponentName*).

### <a name="example---reset-timer"></a>Eksempel – Tilbakestill tidtaker

> [!div class="mx-imgBorder"]
> @no__t – 0OnReset eksempel @ no__t-1

I denne tids velgings komponenten brukes to variabler for å vise time _selectedHour og _selectedMinute. Når velgeren blir tilbakestilt, bør disse variablene tilbakestilles til en standard verdi, for eksempel 12: dagene.  OnReset-egenskapen for komponenten har følgende formel: **Angi (_selectedHour, 12); Angi (_selectedMinute, 12)**

Hvis du vil utløse tilbakestilling, kan du gå til en skjerm og sette inn en forekomst av komponenten. Legg til en knapp, og Konfigurer OnSelect for knappen for å kalle **tilbake Reset (TimerComponent_instance)** for å utløse OnReset.

> [!div class="mx-imgBorder"]
> @no__t 0Reset knapp @ no__t-1

## <a name="update-onreset-using-custom-property"></a>Oppdater OnReset ved hjelp av egen definert egenskap

I tillegg til å tilbakestille en komponent forekomst fra utsiden av komponenten, finnes det en annen metode for å utløse OnReset fra innsiden. «**Øk OnReset når verdi endringer**» er et alternativ når du oppretter en egen definert inn data egenskap, og den tillater verdi endringer av denne egenskapen for å utløse OnReset i komponenten. Denne metoden er utformet for enkelt å angi og tilbakestille standard verdier. 

> ![OnReset, eksempel](./media/component-behavior/property-trigger.png)

### <a name="example"></a>Eksempel

> [!div class="mx-imgBorder"]
> @no__t – 0OnReset eksempel @ no__t-1

Dette er et eksempel på gjennomgang av ordre numre og oppdatering av tall. Den numeriske opp-og ned-komponenten brukes til å øke eller redusere antall ordrer. Når du velger galleriet til venstre, tilbakestilles standard antallet numeriske opp-og nedbrutte komponenter for å vise ordre nummeret for det valgte verktøyet. «**Øk OnReset når verdi endrer**seg» gjør det mulig å tilbakestille standard verdien når inn dataene endres. 

Hvis du vil gjøre dette, merker du av for**Øk OnReset når verdi endres**for standard inn data-egenskapen. **OnReset** for komponenten er satt til **Angi (_numericValue, numerisk opp ned». DefaultValue)** . _numericValue er variabelen for å lagre verdien for den gjeldende ordre verdien. Og angi **standarden** for tekst inn data-kontrollen til **IF (IsBlank (_NumericValue), numerisk opp ned. DefaultValue, _numericValue)** . 
