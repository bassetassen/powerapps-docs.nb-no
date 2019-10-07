---
title: Tilgjengelighets egenskaper for lerret apper | Microsoft Docs
description: Referanse informasjon om egenskaper som TabIndex og ToolTip
author: fikaradz
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 01/26/2017
ms.author: fikaradz
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 2c11e05c93d5a505408948178bf3efbd31f2dbf7
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71986157"
---
# <a name="accessibility-properties-for-canvas-apps"></a>Tilgjengelighets egenskaper for lerret apper

Konfigurasjon av egenskaper som tilbyr alternative måter å arbeide interaktivt med kontroller som er egnet for brukere med funksjonshemninger på.

## <a name="properties"></a>Egenskaper

**AccessibleLabel** – etikett for skjermlesere. En tom verdi for kontroller av typen Bilde, Ikon og Figur gjør dem usynlige for skjermleseren og fører til at de behandles som dekorasjoner.

**Live** – hvordan skjerm lesere bør annonsere endringer til innhold. Bare tilgjengelig i **[etikett](control-text-box.md)** -kontrollen.

* Når det er **merket av**for dette, vil ikke skjerm leseren annonsere endringer.
* Når det er satt til **Polite**, full føres skjerm leseren å snakke før eventuelle endringer som ble funnet mens skjerm leseren ble snakke.
* Når det er satt til **assertive**, avbryter skjerm leseren seg selv for å annonsere eventuelle endringer som oppstod mens skjerm leseren ble snakke.

Lær hvordan du kan [annonsere dynamiske endringer med direktesendte områder](../accessible-apps-live-regions.md).

**TabIndex** – bestemmer om kontrollen deltar i hurtig navigasjon.

Tastatur navigasjon er et viktig aspekt i alle apper.  For mange av tastatur beholdes mer effektivt enn å bruke berøring eller mus, og det gjør det mulig for skjerm lesere for synshemmede.  Navigasjons rekkefølgen bør:
- Speil det som vises visuelt.
- Bare få tabu lat ORS topp på kontroller som er interaktive.
- Følg enten en intuitiv bortover og deretter ned "Z"-rekkefølge, og deretter på tvers av "omvendt"-rekkefølgen.

Kravene ovenfor vil bli oppfylt med standard **TabIndex** -verdier, og vi anbefaler at du ikke endrer dem.  Standard er det meste brukerne forventer visuelt, og den fungerer bra med en skjerm leser.  Men det kan være tilfeller der du vil overstyre standard innstillingen.  Bruk **TabIndex** -egenskapen og den [ **utvidede gruppe** kontrollen](https://powerapps.microsoft.com/en-us/blog/enhanced-group-experimental-control-with-layout-control-and-nesting/) (eksperimentell) til å foreta justeringer i navigasjons rekkefølgen.  

Egenskapen **TabIndex** har to anbefalte verdier:

| TabIndex-verdi | Virkemåte | Standard for |
|----------------|----------|-------------|
| 0 | Kontrollen deltar i hurtig navigasjon. | [**Knapp**](control-button.md), [**tekst inn data**](control-text-input.md), [**kombinasjons boks**](control-combo-box.md)og andre vanlige interaktive kontroller. |
| @no__t – 01 | Kontrollen deltar ikke i hurtig navigasjon. | [**Etikett**](control-text-box.md), [**bilde**](control-image.md), [**ikon**](control-shapes-icons.md)og andre vanligvis ikke-interaktive kontroller. |

Navigasjons rekkefølge kommer vanligvis fra venstre mot høyre, deretter fra topp til bunn, i et «Z»-mønster. Rekkefølgen er basert på verdiene for **X** -og **Y** -egenskapen til kontrollene. Hvis kontroller dynamisk flyttes på skjermen, for eksempel ved å ha en formel for **X** eller **Y** basert på en tidtaker eller en annen kontroll, endres navigasjons rekkefølgen dynamisk også.

Bruk den [ **forbedrede gruppe** kontrollen](https://powerapps.microsoft.com/en-us/blog/enhanced-group-experimental-control-with-layout-control-and-nesting/) (eksperimentell) til å bunte kontroller som skal navigeres sammen, eller for å opprette kolonner i et "reverst"-mønster.  Øverst i eksemplet nedenfor er navne feltene plassert i en utvidet gruppe kontroll som fører til at navigasjonen går ned før det går over.  Nederst i eksemplet brukes ingen gruppe kontroller, og navigasjonen fortsetter på tvers, og deretter ned som vanlig som ikke er intuitivt, gitt kontroll grupperinger. 

![Animasjon som viser utvidet gruppe kontroll som fører til at navigasjonen går ned i en gruppe før den går over](media/properties-accessibility/enhanced-group.gif)

På samme måte vil kategorier gjennom beholdere som [**skjema**](control-form-detail.md) -og [**Galleri**](control-gallery.md) -kontroller, navigere gjennom alle elementene i beholderen før den neste kontrollen går utenfor beholderen.  

Kontroller som har en **synlig** egenskaps verdi som *Usann* , eller som har en **Display Mode** -egenskaps verdi **deaktivert** , er ikke inkludert i navigasjonen.  

Når du bruker en nett leser, flyttes den siste kontrollen av skjermen til nett leserens innebygde kontroller, for eksempel URL-adressen.  

> [!WARNING]
> Unngå **TabIndex** -verdier som er større enn 0. Kontrollene for kontrollen gjengis i HTML, men selv om [W3C har advart](https://www.w3.org/TR/wai-aria-practices/#kbd_general_between) «forfattere er sterkt forbrukt for å ikke bruke disse verdiene.» Mange HTML-verktøy advarer seg etter verdier som er større enn 0, som gjør at [appen](../accessibility-checker.md) ser når den rapporterer rekkefølgen av elementene på skjermen.»  Alt for gode grunner: ved å bruke **TabIndex** på denne måten kan det være veldig vanskelig å få tilgang til dem, slik at skjerm lesere ikke kan brukes.
> 
> Når det finnes kontroller med **TabIndex** som er større enn 0, vil brukerne navigere til kontroller med økende **TabIndex** -verdier (1, 2 og så videre). Når brukere har navigert alle kontroller med positive **TabIndex** -verdier, vil de til slutt navigere til kontrollene med **TabIndex** -verdien 0, inkludert nett leserens innebygde kontroller. Når det er flere kontroller med samme **TabIndex**, bestemmer **X** -og **Y** -posisjonen sin relative rekkefølge.





