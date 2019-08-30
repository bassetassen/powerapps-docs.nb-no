---
title: Gjennomgå en lerretsapp for tilgjengelighet | Microsoft Docs
description: Identifiser måter å gjøre en lerretsapp mer tilgjengelig på for brukere med syns-, hørsel- og andre typer hemminger
author: emcoope-msft
ms.service: powerapps
ms.topic: article
ms.date: 07/05/2018
ms.author: emcoope
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 05ac3d3705fc56b5714d6cb704d2d3cc3dc87124
ms.sourcegitcommit: b4df7d781cda50dfe2f6609f1cc4d2b531428b3c
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/29/2019
ms.locfileid: "70161286"
---
# <a name="review-a-canvas-app-for-accessibility-in-powerapps"></a>Gjennomgå en lerretsapp for tilgjengelighet i PowerApps

Brukere med syns-, hørsel- eller andre hemminger kan lettere bruke lerretsappen hvis du tar tilgjengelighet i betraktning når du utformer hvordan appen skal se ut og fungere. Hvis du ikke er sikker på hvordan du gjør appen mer tilgjengelig, kan du kjøre tilgjengelighetskontrollen i PowerApps Studio. Dette verktøyet finner ikke bare potensielle tilgjengelighetsproblemer, men forklarer også hvorfor hvert av dem kan være et potensielt problem for brukere som har en bestemt funksjonshemning, og tilbyr forslag til hvordan du løser hvert problem.
Tilgjengelighetskontrollen oppdager problemer med skjermleser og tastatur for deg, og du kan finne informasjon om hvordan du løser problemer med fargekontrast ved hjelp av [tilgjengelige farger](accessible-apps-color.md).

Tilgjengelighetskontrollen hjelper deg med å identifisere innstillinger du kanskje vil endre, men du bør alltid vurdere forslagene i forbindelse med det appen trenger å gjøre. Mange forslag kan være nyttige, men du kan ignorere dem som gjør mer skade enn nytte.

## <a name="find-accessibility-issues"></a>Finn tilgjengelighetsproblemer

1. Velg ikonet for appkontrollen i øverste høyre hjørne av PowerApps Studio.

    ![Ikon for appkontroll](./media/accessibility-checker/app-checker-icon.png)

2. Velg **Tilgjengelighet** i menyen som vises.

    ![Liste over alternativer for appkontrollrute](./media/accessibility-checker/app-checker-menu.png)

    En liste over problemer vises, først sortert etter alvorsgrad og deretter etter skjerm.

    ![Tilgjengelighetskontrollrute og liste over elementer](./media/accessibility-checker/accessibility-checker-pane.png)

3. Velg pilen ved siden av et element for å vise detaljer om det.

    ![Tilgjengelighetskontrolldetaljer](./media/accessibility-checker/details-pane.png)

4. Velg Tilbake-pilen for å gå tilbake til listen over elementer.

5. Hvis du bestemmer deg for å ta for deg et problem, merker du det for å åpne den berørte egenskapen.

6. Når du endrer en eller flere egenskaper, velger du **Merk av på nytt** for å oppdatere listen over problemer.

    Reparerte enheter forsvinner fra listen, og nye enheter kan vises.

## <a name="severity-of-issues"></a>Alvorsgrad for problemer

Tilgjengelighetskontrollen klassifiserer hvert problem som en feil, en advarsel eller et tips, basert på alvorsgraden for problemet.

- **Feil** identifiserer problemer som gjør appen vanskelig eller umulig å bruke og forstå for brukere som har en funksjonshemming.
- **Advarsler** identifiserer problemer som gjør appen vanskelig å bruke eller forstå for de fleste, men ikke for alle brukere som har en funksjonshemming.
- **Tips** hjelper deg med å forbedre opplevelsen for brukere som har en funksjonshemming.

## <a name="types-of-issues"></a>Ulike typer problemer

| Problemtittel                            | Alvors grad | Problembeskrivelse  | Slik løser du et problem | Derfor løser du et problem|
| ------------------------------         |:---------| -----| ------|------ |
| **Mangler tilgjengelig etikett**           | Feil    | Når den tilgjengelige etikettegenskapen til en interaktiv kontroll ikke inneholder tekst. En interaktiv kontroll kan være interaktiv i seg selv, som en knapp, eller ha interaktive egenskaper. Du kan for eksempel ha angitt **OnSelect**-egenskapen til et bilde eller angitt **TabIndex**-egenskapen til 0 eller høyere.  | Rediger den tilgjengelige etikettegenskapen for å beskrive elementet. | Hvis den tilgjengelige etikettegenskapen ikke inneholder tekst, forstår ikke personer som ikke kan se skjermen, hva som vises på bilder og i kontroller. |
| **Fokus vises ikke**                | Feil    | Når **FocusBorderThickness** for en kontroll er angitt til 0. Det er god praksis å påse at det er god fargekontrast mellom fokuskantlinjen og selve kontrollen, slik at det er lett å se. | Endre egenskapen **FocusedBorderThickness** til en verdi som er høyere enn 0.  | Hvis fokus ikke vises, kan ikke personer som ikke bruker mus, se fokus når de samhandler med appen.   |
| **Manglende teksting for hørselshemmede**                   | Åtvaringa  | Når egenskapen **ClosedCaptionsURL** for en **Lyd**- eller **Video**-kontroll er tom. | Angi egenskapen **ClosedCaptionsURL** til nettadressen for teksting for hørselshemmede. | Uten teksting for hørselshemmede er det ikke sikkert funksjonshemmede vil oppfatte informasjonen fra et video- eller lydsegment. |
| **Mangler nyttige kontrollinnstillinger**   | Åtvaringa  | Når én eller flere innstillinger (for eksempel å vise etiketter og markører for diagrammer og vise standardkontroller for **Lyd**-, **Video**- og **Penneinndata**-kontroller) er slått av. | Velg advarselen, og angi deretter **sann** for egenskapen. | Når du endrer denne egenskapsinnstillingen, gir du brukeren bedre informasjon om hvordan kontrollene i appen fungerer. |
| **HTML er ikke tilgjengelig**           | Åtvaringa  | Når en annen kontroll enn en HTML-tekstkontroll inneholder HTML. I så fall støtter ikke PowerApps tilgjengeligheten til egendefinerte HTML-elementer. | Bruk en annen metode enn HTML, eller fjern HTML fra dette elementet. | Appen vil ikke fungere på riktig måte, eller være tilgjengelig, hvis du legger til interaktive HTML-elementer. |
| **Slå av autostart**                 | Åtvaringa  | Når **Lyd**- eller **Video**-kontrollens **Autostart**-egenskap er angitt til **sann**. | Angi kontrollens **Autostart**-egenskap til **usann**. | Video- og lydfiler som spilles av automatisk, kan forstyrre brukerne. La dem velge om de vil spille av et klipp. |
| **Endre skjermnavn**                 | Tips      | Når en skjerm har et standardnavn som leses opp av skjermlesere når brukere navigerer i appen. | Gi skjermen et navn som beskriver hva som er på skjermen, eller hva den brukes til.| Blinde, svaksynte eller personer med lesevansker er avhengige av skjermnavn for å navigere med skjermleseren. |
| **Legg til tekst for tilstandsindikasjon**          | Tips      |  Når en kontroll har en tilstand, for eksempel en veksleknapp, men verdietikettene er slått av. | Angi **ShowValue**-egenskapen til kontrollen til **sann** for å vise gjeldende tilstand. | Brukere får ikke bekreftelse på handlingene sine hvis ikke tilstanden for kontrollen vises. |
| **Kontroller rekkefølgen til skjermelementene**| Tips      | Når egenskapen **TabIndex** er større enn 0. App-opprettere kan angi egen definerte tabulatorrekkefølge ved å angi **TabIndex** -egenskapen til en verdi som er større enn 0, men det er svært godt å forhindre at det er vanskelig å få rett, vedlikeholde og bryte skjerm lesere. | Sett alle egenskaper for **TabIndex** til 0 eller-1 når det er mulig.  I stedet for å bruke **TabIndex**, kan du bruke **utvidet gruppe** -kontrollen til å endre navigasjons rekkefølgen fra standard.  Hvis verdiene i **TabIndex** er større enn 0 må brukes, kontrollerer du at skjerm elementene Sams varer med rekkefølgen du vil bla gjennom dem i. | Navigasjons rekkefølgen skal speiles i rekkefølgen som kontrollene vises på skjermen, som er standard.  Hvis manuelle justeringer utføres, er det vanskelig å holde den riktige rekkefølgen spesielt avhengig av nett leserens adresse linje og andre kontroller utenfor appen.  Dette kan gjøre det vanskelig å bruke en skjerm leser.  Når de leses av skjerm leseren, bør kontrollene vises i samme rekkefølge som de vises på skjermen, i stedet for en rekkefølge som er mindre intuitiv.  |
| **Legg til en annen inndatametode**           | Tips      | Når en app inneholder en **Penne**-kontroll. Dette tipset minner deg på å inkludere en separat inndatametode. | Legg til en **Tekstinndata**-kontroll i tillegg til **Penne**-kontrollen for en tilgjengelig opplevelse. | Enkelte brukere kan ikke bruke penn og krever en annen måte å gi informasjon på (for eksempel ved å skrive inn en signatur). |

## <a name="next-steps"></a>Neste trinn

- [Opprett apper som er enkle å forstå](accessible-apps.md)
- [Tilgjengelige farger](accessible-apps-color.md)
- [Egenskaper for tilgjengelighet](controls/properties-accessibility.md)
