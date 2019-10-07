---
title: 'Kontroll for PDF-visningsprogram: referanse | Microsoft Docs'
description: Informasjon, inkludert egenskaper og eksempler, om kontrollen for PDF-visningsprogrammet
author: fikaradz
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 10/25/2016
ms.author: fikaradz
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 9fdd7f25a729fa71111e1fd5d82e04b7cea874f3
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71986430"
---
# <a name="pdf-viewer-control-experimental-in-powerapps"></a>Kontroll for PDF-visningsprogram (eksperimentell) i PowerApps
En eksperimentell kontroll som viser innholdet i en PDF-fil.

## <a name="description"></a>Beskrivelse
Vis tekst, grafikk og annet innhold i en PDF-fil ved å legge til denne typen kontroll, og sette inn den tilhørende **dokument**-egenskapen til nettadressen, omsluttet av doble anførselstegn, av filen som du vil vise.

## <a name="limitations"></a>Begrensninger
1. Sikkerhets arkitekturen for PowerApps krever at PDF-visningsprogrammet støtter bare HTTPS-koblinger, ikke HTTP.  

2. **Dokument** egenskapen må koble direkte til PDF-filen. Mappeomadressering eller HTML-visninger av dokumentet støttes ikke.

3. Serveren som er vert for dokumentet, må ikke kreve godkjenning.

4. Det kan hende at du ikke kan vise et PDF-dokument i appen Hvis dokumentet ligger på en server som har restriktive innstillinger for ressurs deling (CORS). Hvis du vil løse dette problemet, må serveren som er vert for PDF-dokumenter tillate forespørsler på tvers av data fra powerapps.com.

App-brukere kan omgå disse begrensningene ved å åpne PDF-dokumenter i en ekstern nett leser, som du blir spurt om kontrollen ikke kan åpne et dokument. Dette alternativet er også tilgjengelig i systemmenyen for alle eksterne dokumenter.

Apper i appen kan omgå disse begrensningene ved å inkludere PDF-dokumenter som medie ressurser i appen. På den måten kan PDF Viewer-kontrollen alltid vise dokumentet.

## <a name="key-properties"></a>Nøkkelegenskaper
**Dokument** – nettadressen, omsluttet av doble anførselstegn, for en PDF-fil.

## <a name="additional-properties"></a>Tilleggsegenskaper
**ActualZoom** – den faktiske zoomingen for kontrollen, hvor zoomingen som er forespurt kan skille seg fra **Zoom**-egenskapen.

**[BorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje.

**[BorderStyle](properties-color-border.md)** – om kontrollens kantlinje er satt til **Heltrukket**, **Stiplet**, **Prikket** eller **Ingen**.

**[BorderThickness](properties-color-border.md)** – tykkelsen på kontrollens kantlinje.

**CurrentFindText** – det gjeldende søkeordet som er i bruk.

**CurrentPage** – nummeret på siden i en PDF-fil som faktisk vises.

**[DisplayMode](properties-core.md)** – hvorvidt kontrollen tillater brukerinndata (**Rediger**), bare viser data (**Vis**) eller er deaktivert (**Deaktivert**).

**[DisabledBorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje hvis kontrollens **[DisplayMode](properties-core.md)** -egenskap er angitt til **Deaktivert**.

**[Fyll](properties-color-border.md)** – bakgrunnsfargen på en kontroll.

**FindNext** – finner neste forekomst av **FindText** i dokumentet.

**FindPrevious** – finner forrige forekomst av **FindText** i dokumentet.

**FindText** – søkeordet det skal søkes etter i dokumentet.

**[Høyde](properties-size-location.md)** – avstanden mellom den øvre og nedre kanten til en kontroll.

**[HoverBorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje når brukeren holder musepekeren på denne kontrollen.

**[OnSelect](properties-core.md)** – hvordan appen reagerer når brukeren klikker eller trykker på en kontroll.

**OnStateChange** – hvordan en app svarer når statusen for kontrollen endres.

**[PaddingBottom](properties-size-location.md)** – avstanden mellom teksten i en kontroll og den nederste kanten av kontrollen.

**[PaddingLeft](properties-size-location.md)** – avstanden mellom teksten i en kontroll og den venstre kanten av kontrollen.

**[PaddingRight](properties-size-location.md)** – avstanden mellom teksten i en kontroll og den høyre kanten av kontrollen.

**[PaddingTop](properties-size-location.md)** – avstanden mellom teksten i en kontroll og den øverste kanten av kontrollen.

**Side** – nummeret på siden som du vil vise.

**PageCount** – antall sider i et dokument.

**[PressedBorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje når brukeren trykker eller klikker på kontrollen.

**ShowControls** – om en lyd- eller videoavspiller for eksempel viser en avspillingsknapp og en glidebryter for volum, og om en pennekontroll for eksempel viser ikoner for tegning, sletting og fjerning.

**[Verktøytips](properties-core.md)** – forklarende tekst som vises når brukeren holder pekeren over en kontroll.

**[Synlig](properties-core.md)** – om kontrollen vises eller skjules.

**[Bredde](properties-size-location.md)** – avstanden mellom kontrollens venstre og høyre kant.

**[X](properties-size-location.md)** – avstanden mellom kontrollens venstre kant og den venstre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder).

**[Y](properties-size-location.md)** – avstanden mellom kontrollens øvre kant og den øvre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder).

**Zoom** – hvor mye et bilde fra et kamera prosentvis forstørres eller hvor mye som vises i et PDF-visningsprogram.

## <a name="example"></a>Eksempel

Legg til en kontroll for et **PDF-visningsprogram**, og angi **Dokument**-egenskapen til nettadressen, omsluttet av doble anførselstegn for en PDF-fil som i dette eksemplet:

  **"https://blog.mozilla.org/security/files/2015/05/HTTPS-FAQ.pdf"**

Kontrollen viser PDF-filen.

Lurer du på hvordan du [legger til og konfigurerer en kontroll](../add-configure-controls.md)?

## <a name="accessibility-guidelines"></a>Retningslinjer for tilgjengelighet

Ikke alle tilgjengelighetsfunksjonene i PDF-dokumenter støttes fordi **PDF-visningsprogrammet** fremdeles er på det eksperimentelle stadiet. Derfor bør **ShowControls** være angitt til **sann**, slik at brukere får muligheten til å åpne dokumentet i et eksternt program.

Slik finner du ut hvordan man oppretter tilgjengelige PDF-dokumenter med standardene [WCAG 2.0](https://www.w3.org/TR/WCAG-TECHS/pdf.html) og [PDF/UA](https://www.pdfa.org/pdfua-the-iso-standard-for-universal-accessibility/).

### <a name="screen-reader-support"></a>Kundestøtte for skjermlesere
* Vurder å legge til en overskrift ved hjelp av en **[etikett](control-text-box.md)** hvis PDF-dokumentet ikke har en tittel. Overskriften kan plasseres rett før **Power BI-visningsprogrammet**.
