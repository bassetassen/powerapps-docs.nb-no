---
title: Oppretting av apper som er enkle å forstå | Microsoft Docs
description: Slik lager du apper som er enkle å forstå for folk med funksjonshemninger
services: ''
suite: powerapps
documentationcenter: na
author: fikaradz
manager: anneta
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/03/2018
ms.author: fikaradz
ms.openlocfilehash: bc8a014909ceb817397107b4f64b59aa0c2013f2
ms.sourcegitcommit: 97c0db2968dc07d1bcb21d02e6a6a5c345daa2d2
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/05/2018
ms.locfileid: "30998322"
---
# <a name="create-accessible-apps"></a>Oppretting av apper som er enkle å forstå
En app som er enkel å forstå gjør det enklere for brukere med syns-, hørsel- og andre typer hemminger å bruke appen.  I tillegg til at det er et krav for mange myndigheter og organisasjoner, økes brukervennligheten for brukerne, uavhengig av funksjonsnivå, ved å følge retningslinjene nedenfor.

## <a name="layout-and-color"></a>Oppsett og farger
Sunn fornuft og ukomplisert utforming gjør det enkelt for alle brukere å forstå appene.  Legg merke til forslagene nedenfor når du skal gjøre vanskelige tilpasninger i apper.  Alle PowerApps-temaer er enkle å forstå som standard.
- Kontroller at alle elementene er godt synlige, og at teksten er stor nok.  Alt innhold må være lett å lese og forstå med det blotte øye.
- Unngå å bruke Visibility-egenskapen til å vise frem et element.  Hvis du vil vise noe med forbehold, oppretter du innholdet i en ny skjerm og navigerer hit og tilbake.
- Kontroller at inndataelementene er merket på skjermen. **[AccessibilityLabel](controls/properties-accessibility.md)**-egenskapen bestemmer hva skjermleseren skal si.
- Hvis du tilpasser farger, må du kontrollere at kontrasten mellom tekst og bakgrunn er 4,5:1 eller større.  Programvareverktøy som gjør denne prosessen enklere, er lett tilgjengelig.
- Kontroller at oppsettet følger en logisk flyt når du leser fra topp til bunn, og venstre mot høyre.


## <a name="keyboard-support"></a>Tastaturstøtte
Når du tester appens tilgjengelighet, må du kontrollere at appen kan brukes med tastaturet, tilgjengelighets modiene på iOS og Android, samt at du klarer å navigere selv om skjermleseren er aktivert.

Kontroller at du bruker en logisk rekkefølge for tastaturnavigasjon (med eller uten skjermleser) når du bruker tabulatortasten for å navigere til inndatafeltene, ved å angi **[TabIndex](controls/properties-accessibility.md)**-egenskapen for hver kontroll:
- Etikett-, bilde-, ikon- og formkontroller – Angi TabIndex til 0 hvis de representerer interaktive elementer (det vil si knapper). Hvis de er dekorative elementer eller tekst, kan du angi TabIndex til -1.
- Unngå å angi tabulatorindeks som er høyere enn null.

## <a name="screen-reader-support"></a>Kundestøtte for skjermlesere
Følgende programvarekombinasjoner er støttede anbefalinger for bruk av PowerApps med en skjermleser:

- **Windows**: Edge / Skjermleser
- **macOS**: Safari / VoiceOver
- **Android**: PowerApps-app / Talkback
- **iOS**: PowerApps-app / VoiceOver

For å sikre en tilfredsstillende opplevelse med skjermleseren, anbefales det å:

- Kontrollere at alle inndatakontroller har angitt **[AccessibilityLabel](controls/properties-accessibility.md)**-egenskapen.
- Angi en passende beskrivelse for **[AccessibilityLabel](controls/properties-accessibility.md)** for bilder.
  - Hvis et bilde ikke brukes som en knapp eller en kobling (det vil si ikonet bare er til pynt) og ikke skal leses av skjermleseren, må du kontrollere at **[AccessibilityLabel](controls/properties-accessibility.md)** er tom eller ikke angitt.
  - Hvis et bilde eller et ikon brukes som en knapp, angir du **[TabIndex](controls/properties-accessibility.md)** til 0 og **[AccessibilityLabel](controls/properties-accessibility.md)** til beskrivelsen i koblingen.


## <a name="multimedia"></a>Multimedia
Kontroller at alle videoer har undertekster, og at en utskrift av alle lydopptakene er tilgjengelig for brukeren.  **Video**-kontroll støtter teksting for hørselshemmede i formatet WebVTT via **ClosedCaptionsUrl**-egenskapen.

Vær oppmerksom på at når skjermleseren er aktivert, leser ikke **Tidtaker** knappeteksten, men gir beskjed om hvor mye tid som har gått.  Kunngjøringene kan ikke slås av, selv om tidtakeren er skjult med lav ugjennomsiktighet.

## <a name="working-with-signatures"></a>Arbeid med signaturer
Hvis du har et signaturfelt som bruker PenInput-kontrollen, må du aktivere en alternativ metode for signaturinndata.  Den anbefalte måten er å vise en TextInput-kontroll der en bruker kan skrive inn navnet sitt.  Kontroller at signeringsinstruksjonene er plassert i **[AccessibilityLabel](controls/properties-accessibility.md)**-egenskapen, og at kontrollen er plassert nær penneinndataene, til høyre eller rett nedenfor.



Relatert: **[Egenskaper for tilgjengelighet](controls/properties-accessibility.md)**
