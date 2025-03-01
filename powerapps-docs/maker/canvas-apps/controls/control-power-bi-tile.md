---
title: 'Kontrollen Power BI-flis: referanse | Microsoft Docs'
description: Informasjon, inkludert egenskaper og eksempler, om kontrollen for Power BI-flis
author: fikaradz
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 07/07/2016
ms.author: fikaradz
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: f258beee317fcdad46d71b504f9c8a3046bb3641
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71993377"
---
# <a name="power-bi-tile-control-in-powerapps"></a>Kontrollen for Power BI-flis i PowerApps

En kontroll som viser en [Power BI](https://powerbi.microsoft.com)-flis i en app.

Har du ikke Power BI? [Registrer deg](https://docs.microsoft.com/power-bi/service-self-service-signup-for-power-bi).

## <a name="description"></a>Beskrivelse

Dra nytte av eksisterende dataanalyser og rapportering ved å vise **[Power BI-flisene](https://docs.microsoft.com/power-bi/service-dashboard-tiles)** i appene dine. Angi flisen du ønsker å vise, ved å angi egenskapene **Arbeidsområde**, **Instrumentbord** og **Flis** i **Data**-fanen i panelet for alternativer.

## <a name="sharing-and-security"></a>Deling og sikkerhet

Når du deler en app som inneholder Power BI-innhold, må du dele både selve appen og [instrumentbordet](https://docs.microsoft.com/power-bi/service-how-to-collaborate-distribute-dashboards-reports) hvor flisen kommer fra. Ellers vises ikke Power BI-innholdet, selv ikke for brukere som åpner appen. Apper som inneholder Power BI-innhold respekterer tillatelsene for det innholdet.

## <a name="performance"></a>Ytelsen

Det er ikke anbefalt å ha mer enn tre Power BI-fliser lastet inn samtidig i appen. Du kan kontrollere hvordan du laster og fjerner fliser ved å stille inn **LoadPowerBIContent**-egenskapen.

## <a name="pass-a-parameter"></a>Send en parameter

Ved å sende en enkelt parameter fra appen, kan du filtrere resultatene som vises i en Power BI flis. Men bare string-verdier og operatoren Equals støttes, og filteret fungerer kanskje ikke hvis tabell navnet eller Kol onne navnet inneholder mellomrom.

Hvis du vil sende en enkelt filter verdi, kan du endre verdien for **TileURL** -egenskapen, som følger denne syn tak sen:

```
"https://app.powerbi.com/embed?dashboardId=<DashboardID>&tileId=<TileID>&config=<SomeHash>"
```

Til denne verdien, kan du tilføye denne syn tak sen:

```
&$filter=<TableName>/<ColumnName> eq '<Value>'
```

Parameteren vil filtrere en verdi i data settet i rapporten der flisen stammer.

## <a name="key-properties"></a>Nøkkelegenskaper

**Workspace** – Power BI-arbeidsområdet flisen kommer fra.

**Dashboard** – Power BI-instrumentbordet flisen kommer fra.

**Flis** – navnet på Power BI-flisen du vil vise.

**LoadPowerBIContent** – når den er angitt til sann, lastes Power BI-innholdet og vises. Når den er angitt til usann, fjernes Power BI-innholdet, noe som frigir minne og optimaliserer ytelsen.

## <a name="additional-properties"></a>Tilleggsegenskaper

**[BorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje.

**[BorderStyle](properties-color-border.md)** – om kontrollens kantlinje er satt til **Heltrukket**, **Stiplet**, **Prikket** eller **Ingen**.

**[BorderThickness](properties-color-border.md)** – tykkelsen til kontrollens kantlinje.

**[DisplayMode](properties-core.md)** – Hvorvidt kontrollen tillater brukerinndata (**Edit**), bare viser data (**View**) eller er deaktivert (**Disabled**).

**[Høyde](properties-size-location.md)** – avstanden mellom kontrollens øvre og nedre kant.

**[OnSelect](properties-core.md)** – hvordan appen responderer når brukeren klikker eller trykker på en kontroll. Power BI-rapporten som er tilknyttet med flisen åpnes som standard.

**TileUrl** – nettadressen som Power BI-tjenesten bruker til å spørre om flisen. Du kan sende en enkelt parameter til Power BI-flisen ved å legge til parameteren i nettadressen (eksempel: ... & "&$filter=Town/Province eq '" & ListBox1.Selected.Abbr & "'"). Du kan bruke bare Er lik-operatoren i parameteren.

**[Synlig](properties-core.md)** – om kontrollen vises eller skjules.

**[Bredde](properties-size-location.md)** – avstanden mellom kontrollens venstre og høyre kant.

**[X](properties-size-location.md)** – avstanden mellom kontrollens venstre kant og den venstre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder).

**[Y](properties-size-location.md)** – avstanden mellom kontrollens øvre kant og den øvre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder).

## <a name="example"></a>Eksempel

1. Åpne **Kontroller**-menyen på **Sett inn**-fanen, og legg deretter til en **Power BI tile**-kontroll.

    Lurer du på hvordan du [legger til og konfigurerer en kontroll](../add-configure-controls.md)?

2. Klikk eller trykk på **Mitt arbeidsområde** for **Arbeidsområde**-innstillingen, på **Data**-fanen til Innstillinger-panelet.

3. Velg et instrumentbord i listen over instrumentbord, og velg deretter en flis i listen over fliser.

    Kontrollen gjengir Power BI-flisen.

## <a name="accessibility-guidelines"></a>Retningslinjer for tilgjengelighet

**Power BI-flisen** er ganske enkelt en beholder for Power BI innhold. Finn ut hvordan du oppretter tilgjengelig innhold med disse [tilgjengelighetstipsene for Power BI](https://docs.microsoft.com/power-bi/desktop-accessibility).

Vurder å legge til en overskrift ved hjelp av en **[Etikett](control-text-box.md)** -kontroll for å støtte skjermlesere, hvis Power BI-innholdet ikke har en tittel. Du kan plassere etiketten rett før Power BI-flisen.
