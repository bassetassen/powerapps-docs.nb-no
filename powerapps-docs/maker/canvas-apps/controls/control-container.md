---
title: 'Container-kontroll: referanse | Microsoft Docs'
description: Informasjon, inkludert egenskaper og eksempler, om beholder kontrollen
author: emcoope-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.component: canvas
ms.date: 9/20/2019
ms.author: emcoope
ms.reviewer: tapanm-msft
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 758d986660137d4e513919911589cbbc0dc304a2
ms.sourcegitcommit: 7016ff837eff2cb0985fc71edab95cbf99335677
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 09/20/2019
ms.locfileid: "71160160"
---
# <a name="container-control-in-powerapps-experimental"></a>Container-kontrollen i PowerApps (eksperimentell)
Gir muligheten til å opprette hierarki.

> [!IMPORTANT]
> Dette er en eksperimentell funksjon. Eksperimentelle funksjoner kan endres radikalt eller forsvinne fullstendig når som helst.
> Hvis du vil ha mer informasjon, kan du lese [Forstå funksjonene eksperimentell og forhånds visning i powerapps](https://docs.microsoft.com/en-us/powerapps/maker/canvas-apps/working-with-experimental-preview).

## <a name="description"></a>Beskrivelse
 Beholderen kan inneholde et sett med kontroller og har egne egenskaper. 

Du kan begynne med å sette inn en tom beholder, tilpasse den ved å legge til kontroller i den, endre størrelsen på den, flytte den, skjule den og gjøre andre endringer. Du kan også begynne med en rekke kontroller, velge dem og legge dem til i en beholder via hurtig menyen i tre visningen eller høyre klikk på lerretet. 

## <a name="properties"></a>Egenskaper
**[BorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje.

**[BorderStyle](properties-color-border.md)** – om kontrollens kantlinje er satt til **Heltrukket**, **Stiplet**, **Prikket** eller **Ingen**.

**[BorderThickness](properties-color-border.md)** – tykkelsen til kontrollens kantlinje.

**[Fyll](properties-color-border.md)** – bakgrunnsfargen på kontrollen.

**[Høyde](properties-size-location.md)** – avstanden mellom kontrollens øvre og nedre kant.

**[Bredde](properties-size-location.md)** – avstanden mellom kontrollens venstre og høyre kant.

**[Synlig](properties-core.md)** – om kontrollen vises eller skjules.

**[X](properties-size-location.md)** – avstanden mellom kontrollens venstre kant og den venstre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder). 

**[Y](properties-size-location.md)** – avstanden mellom kontrollens øvre kant og den øvre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder). 


## <a name="known-limitations"></a>Kjente begrensninger

Beholdere fungerer ikke med lerrets komponenter eller i skjemaer. 

## <a name="frequently-asked-questions"></a>Vanlige spørsmål

**Hva er forskjellen mellom en beholder og en gruppe?**
Redigerings gruppen er et lett konsept som brukes til å flytte rundt kontroller og masse redigering av lignende egenskaper for kontroller i gruppen. Redigerings gruppen har ingen innvirkning på oppsettet til appen. 

Beholder kontrollen ble tidligere levert i eksperimentell som erstatning for redigerings gruppens navn som utvidet gruppe. Det fikk endret navn til beholder kontrollen fordi det finnes en verdi i både en lett redigerings gruppe og en strutured container-kontroll med flere egenskaper. 

