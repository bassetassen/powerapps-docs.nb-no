---
title: 'Kontroller for Visningsskjema og Redigeringsskjema: referanse | Microsoft Docs'
description: Informasjon, inkludert egenskaper og eksempler, om kontroller for Visningsskjema og Redigeringsskjema
author: aneesmsft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 07/06/2017
ms.author: aneesa
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 4d7b21286f793aefdcc66a3dcbb027ab8f9ac4e7
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/23/2019
ms.locfileid: "61544318"
---
# <a name="edit-form-and-display-form-controls-in-powerapps"></a>Kontroller for Redigeringsskjema og Visningsskjema i PowerApps
Vis, rediger og opprett en post i en datakilde.

## <a name="description"></a>Beskrivelse
Hvis du legger til en **Visningsskjema**-kontroll, kan brukeren vise alle feltene i en post eller bare angitte felt. Hvis du legger til en **Redigeringsskjema**-kontroll, kan brukeren redigere disse feltene, opprette en post og lagre disse endringene i en datakilde.

![Eksempelskjema og kontroller for skjemavisning](./media/control-form-detail/form-detail-intro.png)

Hvis du legger til en **[Galleri](control-gallery.md)**-kontroll, kan du konfigurere den til å vise en tabell i en datakilde og deretter konfigurere et skjema så det viser posten brukeren velger i galleriet. Du kan også legge til én eller flere **[Knapp](control-button.md)**-kontroller som brukeren kan velge for å lagre endringer, avbryte redigeringer og opprette poster. Du kan opprette en [komplett løsning](../working-with-forms.md) ved å bruke kontrollene sammen.

### <a name="record-selection"></a>Postutvalg
Du angir **DataSource**-egenskapen til en tabell med poster, og du angir **Element**-egenskapen for skjemaet til å vise en bestemt post i den aktuelle tabellen, uansett skjematype. Du kan for eksempel angi **Element**-egenskapen for et skjema til **SelectedItem**-egenskapen for en **[Galleri](control-gallery.md)**-kontroll. Når brukeren velger en post i galleriet, vises den samme posten i skjemaet, bortsett fra at skjemaet kan vise flere felt. Hvis brukeren returnerer til galleriet og velger en annen post, endres **SelectedItem**-egenskapen for galleriet. Denne endringen oppdaterer **Element**-egenskapen for skjemaet, som deretter viser den nylig valgte posten.

Du kan også angi **Element**-egenskapen for et skjema ved hjelp av **Rullegardinliste**-kontrollen, som [Vis, rediger eller legg til en post](../add-form.md) beskriver, eller en funksjon som for eksempel **Oppslag** eller **Først**. Du kan for eksempel angi den **element** egenskapen til en av disse formlene for å vise den Fabrikam-oppføringen i den **kontoer** enhet i Common Data Service:

```First(Accounts)```

```Lookup(Accounts, "Fabrikam" in name)```

Hver enkelt skjemakontroll inneholder én eller flere **[Kort](control-card.md)**-kontroller. Ved å angi **[DataField](control-card.md)**-egenskapen for et kort [angir du hvilket felt kortet viser samt andre detaljer](../add-form.md).

### <a name="create-a-record"></a>Å opprette en post
Når en **Redigeringsskjema**-kontroll er i **Redigeringsmodus**, kan brukeren oppdatere posten som er angitt i **Element**-egenskapen for skjemaet. Ved inspeksjon returnerer **Modus**-egenskapen **Rediger**.

Når en **Redigeringsskjema**-kontroll er i **Ny**-modus, ignoreres imidlertid **Element**-egenskapen. Skjemaet viser ikke en eksisterende post, i stedet samsvarer verdiene i hvert felt med standardverdiene for datakilden du har konfigurert skjemaet med. **[NewForm](../functions/function-form.md)**-funksjonen gjør at et skjema bytter til denne modusen.

Du kan for eksempel angi **[Tekst](properties-core.md)**-egenskapen for en knapp, slik at den viser **Ny** og **[OnSelect](properties-core.md)**-egenskapen til en formel som inneholder **[NewForm](../functions/function-form.md)**-funksjonen. Hvis brukeren velger denne knappen, bytter skjemaet til **Ny**-modus, slik at brukeren kan opprette en post som begynner med kjente verdier.

Et skjema bytter tilbake til **Redigeringsmodus**-modus hvis **[ResetForm](../functions/function-form.md)**-funksjonen eller **[SubmitForm](../functions/function-form.md)**-funksjonen kjører.

* Du kan angi **[Tekst](properties-core.md)**-egenskapen for en knapp, slik at den viser **Avbryt** og dens **[OnSelect](properties-core.md)**-egenskap til en formel som inneholder **[ResetForm](../functions/function-form.md)**-funksjonen. Hvis brukeren velger denne knappen, forkastes eventuelle endringer i fremdrift, og verdiene i skjemaet samsvarer med standardverdiene for datakilden igjen.
* Du kan angi **[Tekst](properties-core.md)**-egenskapen for en knapp så den viser **Lagre endringer** og **[OnSelect](properties-core.md)**-egenskapen til en formel som inneholder **[SubmitForm](../functions/function-form.md)**-funksjonen. Hvis brukeren velger denne knappen og datakilden oppdateres, tilbakestilles verdiene i skjemaet til standardverdiene for datakilden.

### <a name="save-changes"></a>Å lagre endringer
Hvis du oppretter en **Lagre endringer**-knapp, som den forrige delen beskriver, kan brukeren opprette eller oppdatere en post og deretter velge denne knappen for å lagre disse endringene i datakilden. Du kan i stedet konfigurere en **[Bilde](control-image.md)**-kontroll eller en annen kontroll til å utføre den samme oppgaven, så lenge du konfigurerer kontrollen med **[SubmitForm](../functions/function-form.md)**-funksjonen. I alle tilfeller gir egenskapene **Feil**, **ErrorKind**, **OnSuccess** og **OnFailure** tilbakemelding på resultatet.

Når **[SubmitForm](../functions/function-form.md)**-funksjonen kjører, validerer den først dataene brukeren vil sende inn. Hvis et påkrevd felt ikke inneholder en verdi, eller en annen begrensning ikke overholdes, angis **ErrorKind**-egenskapene, og **OnFailure**-formelen kjører. Du kan konfigurere **Lagre endringer**-knappen eller en annen kontroll, slik at brukeren kan velge den bare hvis dataene er gyldige (det vil si hvis **Gyldig**-egenskapen for skjemaet er **sann**). Vær oppmerksom på at brukeren ikke bare må løse problemet, men også velge **Lagre endringer**-knappen igjen (eller forkaste endringene ved å velge en **Avbryt**-knapp, som beskrevet tidligere) for å tilbakestille egenskapene **Feil** og **ErrorKind**.

Hvis dataene består valideringen, sender **[SubmitForm](../functions/function-form.md)** dem til datakilden. Dette kan ta litt tid avhengig av ventetiden på nettverket.

* Hvis innsendingen lykkes, fjernes **Feil**-egenskapen, **ErrorKind**-egenskapen angis til **ErrorKind.None**, og **OnSuccess**-formelen kjører. Hvis brukeren har opprettet en post (det vil si hvis skjemaet tidligere var i **Ny**-modus), bytter skjemaet til **Redigeringsmodus**, slik at brukeren kan redigere den nyopprettede posten eller en annen post.
* Hvis sendingen mislykkes, inneholder **Feil**-egenskapen en brukervennlig feilmelding fra datakilden, som forklarer problemet. **ErrorKind**-egenskapen er angitt riktig, avhengig av problemet, og **OnFailure**-formelen kjører.

Noen datakilder kan oppdage når to personer prøver å oppdatere samme post samtidig. I dette tilfellet er **ErrorKind** angitt til **ErrorKind.Conflict**, og løsningen er å oppdatere datakilden med endringene til den andre brukeren og bruke endringene som er gjort av denne brukeren på nytt.

> [!TIP]
> Hvis du tilbyr en **Avbryt**-knapp på skjemaet, slik at brukeren kan forkaste endringer i fremdrift, legger du **[ResetForm](../functions/function-form.md)**-funksjonen til i **[OnSelect](properties-core.md)**-egenskapen for knappen, selv som egenskapen også inneholder en **[Navigate](../functions/function-navigate.md)**-funksjon for å endre skjerm. Hvis ikke, beholder skjemaet brukerens endringer.

### <a name="layout"></a>Oppsett
Som standard plasseres kortene i en enkeltkolonne for telefonapper og tre kolonner for nettbrettapper. Du kan angi hvor mange kolonner et skjema har, og om kortene skal festes til dem, etter hvert som du konfigurerer skjemaet. Disse innstillingene eksponeres ikke som egenskaper fordi de bare brukes til å angi egenskapene **X**, **Y**, og **Bredde** for kortene.

Hvis du vil ha mer informasjon, kan du se [Forstå oppsett av dataskjema](../working-with-form-layout.md).

## <a name="key-properties"></a>Nøkkelegenskaper
**DataSource** – datakilden som inneholder posten brukeren vil vise, redigere eller opprette.

* Hvis du ikke angir denne egenskapen, kan ikke brukeren vise, redigere eller opprette en post, og ingen ekstra metadata eller validering er oppgitt.

**DefaultMode** – opprinnelig modus for skjemakontrollen.  Se beskrivelsen av **Modus** for de godkjente verdiene og deres betydning, nedenfor. 

**DisplayMode** – modusen som brukes for datakort og kontroller i skjemakontrollen.  

Avledet fra **Modus**-egenskapen grunnen og kan ikke angis uavhengig:

| Modus | DisplayMode | Beskrivelse |
| --- | --- | --- |
| **FormMode.Edit** |**DisplayMode.Edit** |Datakort og kontroller er redigerbare og klare for å godta endringer i en post. |
| **FormMode.New** |**DisplayMode.Edit** |Datakort og kontroller er redigerbare og klare for å godta en ny post. |
| **FormMode.View** |**DisplayMode.View** |Datakort og kontroller er ikke redigerbare eller optimalisert for visning. |

**Feil** – en brukervennlig feilmelding vises for dette skjemaet når **[SubmitForm](../functions/function-form.md)**-funksjonen mislykkes.

* Denne egenskapen gjelder bare for **Redigeringsskjema**-kontrollen.
* Denne egenskapen endres bare når funksjonene **[SubmitForm](../functions/function-form.md)**, **EditForm** eller **[ResetForm](../functions/function-form.md)** kjører.
* Hvis det ikke oppstår feil, er denne egenskapen *tom*, og **ErrorKind** angis til **ErrorKind.None**.
* Når dette er mulig, vil feilmeldingen returneres på brukerens språk. Noen feilmeldinger kommer direkte fra datakilden, og vises kanskje ikke på brukerens språk.

**ErrorKind** – hvis det oppstår en feil når **SubmitForm** kjører, typen feil som har oppstått.

* Gjelder bare for **Redigeringsskjema**-kontroller.
* Denne egenskapen har samme opplisting som **[Errors](../functions/function-errors.md)**-funksjonen. En **Redigeringsskjema**-kontroll kan returnere disse verdiene:

| ErrorKind | Beskrivelse |
| --- | --- |
| **ErrorKind.Conflict** |En annen bruker endret samme post, noe som resulterer i en endringskonflikt. Kjør **[Refresh](../functions/function-refresh.md)**-funksjonen for å laste inn posten på nytt, og prøv endringen på nytt. |
| **ErrorKind.None** |Feilen er av ukjent type. |
| **ErrorKind.Sync** |Datakilden har rapportert en feil. Kontroller **Feil**-egenskapen for å få mer informasjon. |
| **ErrorKind.Validation** |Det ble oppdaget en generell valideringsfeil. |

**Element** – posten i **DataSource** som brukeren vil vise eller redigere.

**LastSubmit** – siste innsendte post, inkludert eventuelle servergenererte felt.

* Denne egenskapen gjelder bare for **Redigeringsskjema**-kontrollen.
* Hvis datakilden automatisk genererer eller beregner felt, slik som et **ID**-felt med et unikt nummer, får **LastSubmit**-egenskapen denne nye verdien etter kjøring av **SubmitForm**.
* Verdien for denne egenskapen er tilgjengelig i **OnSuccess**-formelen.

**Modus** – kontrollen er i **Redigeringsmodus** eller **Ny**-modus.

| Modus | Beskrivelse |
| --- | --- |
| **FormMode.Edit** |Brukeren kan redigere en post ved hjelp av skjemaet. Verdiene i kortene til skjemaet er forhåndsutfylt med den eksisterende posten, som kan endres av brukeren. Hvis **[SubmitForm](../functions/function-form.md)**-funksjonen kjører, endres den eksisterende posten. |
| **FormMode.New** |Brukeren kan opprette en post ved hjelp av skjemaet. Verdiene i kontrollene til skjemaet er forhåndsutfylt med standarder for en post i datakilden. Hvis **[SubmitForm](../functions/function-form.md)**-funksjonen kjører, opprettes en post. |
| **FormMode.View** |Brukeren kan vise en post ved hjelp av skjemaet. Verdiene i kontrollene til skjemaet er forhåndsutfylt med standarder for en post i datakilden. |

Skjemaet bytter fra **Ny**-modus til **Redigeringsmodus** når noen av disse endringene forekommer:

* Skjemaet er sendt inn, og en post opprettes. Hvis galleriet er angitt til automatisk flytting av utvalget til denne nye posten, settes skjemaet i **Redigeringsmodus** for den opprettede posten, slik at brukeren kan foreta ytterligere endringer.
* **[EditForm](../functions/function-form.md)**-funksjonen kjører.
* **[ResetForm](../functions/function-form.md)**-funksjonen kjører. Brukeren velger kanskje en **Avbryt**-knapp som er konfigurert med denne funksjonen.

**OnFailure** – hvordan en app reagerer når en dataoperasjon mislykkes.

* Denne egenskapen gjelder bare for **Redigeringsskjema**-kontrollen.

**OnReset** – hvordan en app reagerer når en **Redigeringsskjema**-kontroll tilbakestilles.

* Denne egenskapen gjelder bare for **Redigeringsskjema**-kontrollen.

**OnSuccess** – hvordan en app reagerer når en dataoperasjon er vellykket.

* Denne egenskapen gjelder bare for **Redigeringsskjema**-kontrollen.

**Unsaved** – sann hvis **Redigeringsskjema**-kontrollen inneholder brukerendringer som ikke er lagret.

* Denne egenskapen gjelder bare for **Redigeringsskjema**-kontrollen.
* Bruk denne egenskapen for å gi brukeren en advarsel før de mister eventuelle endringer som ikke er lagret.  Du hindrer at brukeren velger en annen post i en **[Galleri](control-gallery.md)**-kontroll før endringene lagres i gjeldende post, ved å angi **[Deaktivert](properties-core.md)**-egenskapen til **Form.Unsaved** og på samme måte deaktivere oppdateringsoperasjoner.

**Oppdateringer** – verdiene du skriver tilbake til datakilden for en post som er lastet inn i en skjemakontroll.  

* Denne egenskapen gjelder bare for **Redigeringsskjema**-kontrollen.
* Bruk denne egenskapen for å trekke ut feltverdiene fra kortene i kontrollen.  Deretter kan du bruke disse verdiene til å oppdatere datakilden manuelt med et **[Patch](../functions/function-patch.md)**-funksjonskall eller en annen metode som eksponeres av tilkoblingen.  Du trenger ikke å bruke denne egenskapen hvis du bruker **[SubmitForm](../functions/function-form.md)**-funksjonen.
* Denne egenskapen returnerer en post med verdier.  For eksempel, hvis skjemakontrollen inneholder kortkontroller for **navnet** og **antall** felt og verdiene i den **[oppdateringen](control-card.md)** egenskapene for disse kortene returnerer henholdsvis "Widget" og 10 og deretter den **oppdateringer** egenskapen for skjemakontrollen **{navn: "Widget", Quantity: 10 }**.

**Valid** – om kontrollene **[Kort](control-card.md)** eller **Redigeringsskjema** inneholder valide oppføringer, klare til å sendes til datakilden.

* Denne egenskapen gjelder bare for **Redigeringsskjema**-kontrollen.
* **Gyldig**-egenskapen til en **Skjema**-kontroll samler **Gyldig**-egenskapene for alle **[Kort](control-card.md)**-kontrollene i skjemaet. **Gyldig**-egenskapen for et skjema er **sann** bare hvis dataene i alle kortene i skjemaet er gyldige. Hvis ikke er **Gyldig**-egenskapen for skjemaet **usann**.
* Angi **DisplayMode** for knappen til denne formelen for å aktivere en knapp så den lagrer endringer bare når dataene i et skjema er gyldige, men fremdeles ikke har blitt sendt inn:
  
    **SubmitButton.DisplayMode = If(IsBlank( Form.Error ) || Form.Valid, DisplayMode.Edit, DisplayMode.Disabled)**

## <a name="additional-properties"></a>Tilleggsegenskaper
**[BorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje.

**[BorderStyle](properties-color-border.md)** – om kontrollens kantlinje er satt til **Heltrukket**, **Stiplet**, **Prikket** eller **Ingen**.

**[BorderThickness](properties-color-border.md)** – tykkelsen til kontrollens kantlinje.

**[Fyll](properties-color-border.md)** – bakgrunnsfargen på kontrollen.

**[Høyde](properties-size-location.md)** – avstanden mellom den øvre og nedre kanten til en kontroll.

**[Synlig](properties-core.md)** – om kontrollen vises eller skjules.

**[Bredde](properties-size-location.md)** – avstanden mellom kontrollens venstre og høyre kant.

**[X](properties-size-location.md)** – avstanden mellom kontrollens venstre kant og den venstre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder).

**[Y](properties-size-location.md)** – avstanden mellom kontrollens øvre kant og den øvre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder).

## <a name="more-information"></a>Vil ha mer informasjon
Du kan se [Dataskjemaer](../working-with-forms.md) for å få en omfattende oversikt over hvordan skjemaer fungerer.

## <a name="accessibility-guidelines"></a>Retningslinjer for tilgjengelighet
### <a name="screen-reader-support"></a>Kundestøtte for skjermlesere
* Vurder å legge til en overskrift i skjemaet ved bruk av en **[etikett](control-text-box.md)**.
