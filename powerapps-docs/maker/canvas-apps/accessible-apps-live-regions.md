---
title: Kunngjøre dynamiske endringer med live områder i lerretsapper | Microsoft Docs
description: Slik bruker live områder til å varsle skjermlesere av dynamiske endringer i lerret-apper
author: tahoon-ms
ms.service: powerapps
ms.topic: article
ms.custom: canvas
ms.date: 10/22/2018
ms.author: tahoon
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 9a886b1c585f4fc07efc29bc1166ce4aca5586b5
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/23/2019
ms.locfileid: "61549954"
---
# <a name="announce-dynamic-changes-with-live-regions-for-canvas-apps"></a>Kunngjøre dynamiske endringer med live områder for lerretsapper

Dynamiske endringer utgjøre utfordringene til de visuelt personer. Brukere som har tilgang til en app gjennom en skjermleser fokuserer på én del av appen. Hvis en endring skjer et annet sted, vil disse brukerne ikke klar over den.

Du kan løse dette problemet ved å legge til live områder, som sporer for skjermlesere. Hvis innholdet endres i et dynamisk område, kan en skjermleseren skal si denne endringen.

Den underliggende mekanismen for live områder er [aria live-områder](https://www.w3.org/TR/wai-aria-1.1/#dfn-live-region), slik at de samme retningslinjene gjelder.

## <a name="example-uses-of-live-regions"></a>Eksempler på bruk av live områder

Du kan bruke live områder til å varsle brukere når det oppstår hendelser som disse:

* En feil ved validering forekommer i et skjema.
* En handling som utløses av en knapp er vellykket. For eksempel en bruker kan velge en knapp for å legge til et element i en samling, og et dynamisk område kan vise meldingen «Element lagt til».
* Brukeren har valgt en annen kategori.
* En tidtaker som bakgrunn oppdaterer en nyhetsfeed.

## <a name="create-and-configure-a-live-region"></a>Opprette og konfigurere et dynamisk område

Du kan konfigurere bare en **[etikett](controls/control-text-box.md)** kontrollen som et dynamisk område. Den **Live** -egenskapen bestemmer hva slags dynamiske området det er.

* **Off**: Ikke et dynamisk område. Skjermlesere lese opp ikke endringer.
* **Polite**: Skjermlesere lese opp endringer etter fullfører snakke. Bruk denne verdien for ikke-kritiske varsler som ikke krever umiddelbar oppmerksomhet.
* **Assertive**: Skjermlesere avbryte seg selv for å informere om endringer umiddelbart. Bruk denne for kritiske varsler som krever umiddelbar oppmerksomhet.

Hvis tekstinnholdet i et dynamisk område endres, vil skjermlesere lese opp innholdet i hele teksten, ikke bare den endrede delen. Hvis verdien for den **[tekst](controls/properties-core.md)** egenskapen er satt til en tom streng **""**, skjermleseren ikke si noe.

Hvis du vil gjenta en melding, fjerne tekst innholdet ved å angi verdien for den **[tekst](controls/properties-core.md)** egenskapen til den tomme strengen **""** og angi deretter verdien til meldingen på nytt.

## <a name="best-practices"></a>Anbefalte fremgangsmåter

* Alltid satt **[Visible](controls/properties-core.md)** til sann. Noen skjermlesere søk ikke live områder som forsvinner og vises på nytt.
* Unngå å endre verdien for  **[Live](controls/properties-accessibility.md)**. Noen lesere ikke søk når en live-området blir live-skjermen, og omvendt.
* Plasser det dynamiske området i en logisk posisjon i appen, selv om den ikke er synlig. Kontroller at innholdet er fornuftig i kontekst med elementene før og etter seg. Brukere kan få tilgang til et dynamisk område når som helst gjennom vanlige navigasjon med skjermleseren, ikke bare når endringer skjer.

## <a name="next-steps"></a>Neste trinn

Lær hvordan du [Vis innhold bare for skjermlesere](accessible-apps-content-visibility.md) Hvis det dynamiske området skal skjules fra innholdsformidling.