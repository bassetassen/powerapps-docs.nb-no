---
title: 'Kort-kontroll: referanse | Microsoft Docs'
description: Informasjon, inkludert egenskaper og eksempler, om Kort-kontrollen
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.component: canvas
ms.date: 10/25/2016
ms.author: gregli
ms.reviewer: anneta
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: cc4338e37b7ecde2e2e2e9ad5c5ac6e96d116b58
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/23/2019
ms.locfileid: "61559489"
---
# <a name="card-control-in-powerapps"></a>Kort-kontroll i PowerApps
Ved bruk av Kort-kontrollen kan du vise og redigere et enkelt felt i **[Visningsskjema](control-form-detail.md)**- eller **[Redigeringsskjema](control-form-detail.md)**-kontrollen.

## <a name="description"></a>Beskrivelse
**[Visningsskjema](control-form-detail.md)**- og **[Redigeringsskjema](control-form-detail.md)**-kontrollene fungerer som beholdere for å vise hele poster. Hver beholder kan inneholde et sett med **Kort**-kontroller som viser individuelle felt, eller gjør det mulig å oppdatere disse feltene. Hvert kort har en **DataField**-egenskap som angir hvilke felt i posten som brukes.  

Forhåndsdefinerte kort defineres for ulike datatyper og brukeropplevelser.  Det finnes for eksempel et kort som kan redigere et tallfelt med en **[Tekstinndata](control-text-input.md)**-kontroll, noe som er perfekt for bruk med tastaturet. Det kan hende at et annet kort heller støtter redigering av et tall ved bruk av en **[Glidebryter](control-slider.md)**-kontroll. Når Skjema-kontrollen er valgt, kan du enkelt velge et kort basert på et felt, fra ruten til høyre.

Kortene selve inneholder kontroller. Kontrollene til kortet utgjør opplevelsen for å vise og redigere et enkelt felt. Et kort kan for eksempel bestå av en **[Etikett](control-text-box.md)**-kontroll for å angi visningsnavnet til feltet, og en **[Tekstinndata](control-text-input.md)**-kontroll for å kunne redigere verdien for feltet. Kortet kan også ha en **[Etikett](control-text-box.md)**-kontroll som viser eventuelle godkjenningsfeil som oppstår, og en **[Etikett](control-text-box.md)**-kontroll for vanlige stjerner for å angi at feltet er obligatorisk.

Du kan egendefinere kontrollene til et forhåndsdefinert kort ved å endre størrelsen på det, flytte det, skjule det, legge til kontroller for kortet og foreta andre endringer. Du kan også starte med et helt tomt kort, et «egendefinert kort», som du kan legge til kontroller i fra grunnen av.

Forhåndsdefinerte kort er *låst* som standard. I et låst kort kan du bare endre enkelte egenskaper for kortet eller kontrollene i selve kortet, og du kan ikke slette et låst kort. Du kan vise kortlåsen og låse den opp på **Vis**-fanen i **Avansert**-visningen. Hvis en egenskap er låst og ikke kan endres, vises den med et låseikon ved siden av navnet. Det er ganske avansert å låse opp et kort og bør derfor gjøres med forsiktighet, fordi automatisk formelgenerering ikke lenger skjer for kortet og du kan ikke låse et kort på nytt.

**ThisItem**-posten er tilgjengelig i skjemabeholderen, og den inneholder alle feltene til posten.  Kortets **[Standard](properties-core.md)**-egenskap er for eksempel ofte angitt til **ThisItem**.*FieldName*.

Du kan bruke **Overordnet**-referansen til å konfigurere en kontroll til å referere til kortets egenskaper.  En kontroll skal for eksempel bruke **Parent.Default** for å lese den innledende tilstanden til feltet fra datakilden. Hvis du bruker **Overordnet** i stedet for å hente informasjonen du ønsker direkte, er kortet bedre innkapslet, og du kan endre det til et annet felt uten å ødelegge interne formler.

Hvis du vil se eksempler på hvordan du egendefinerer, låser opp og oppretter kort, kan du se [Slik forstår du datakort](../working-with-cards.md).

## <a name="key-properties"></a>Nøkkelegenskaper
**DataField** – navnet på feltet i en post som dette kortet viser og redigerer.

* Angi navnet som en enkelt statisk streng som er omsluttet av doble anførselstegn (for eksempel, **"Name"**), og ikke en formel.
* Frigjør et kort ved å angi **DataField**-egenskapen som *tom*. Egenskapen **Gyldig** og **Oppdater** ignoreres for kort som ikke er frigitt.

**[Standard](properties-core.md)** – startverdien for en kontroll før den er endret av brukeren.

* Du angir denne egenskapen for hver kontroll i et kort til **Parent.Default**, og den skal henvise til standardverdien til feltet ifølge datakilden. Du kan for eksempel angi **[Standard](properties-core.md)**-egenskapen for en glidebryter til **Parent.Default** for å sikre at brukeren begynner med en generisk verdi for glidebryteren.

**DisplayMode** – verdiene kan være **Rediger, Vis,** eller **Deaktivert**. Konfigurerer om kontrollen i kortet tillater brukerinndata (**Rediger**), bare viser data (**Vis**) eller er deaktivert (**Deaktivert**).  

* Gjør at et enkelt kort kan brukes i både redigerings- og visningsskjema. Det gjør du ved å konfigurere denne egenskapen som er knyttet til skjemaatferden som standard.
* I **Vis**-modus viser underordnede kontroller som **[Tekstinndata](control-text-input.md)**, **[Rullegardin](control-drop-down.md)** og **[Datovelger](control-date-picker.md)** bare tekstverdien, og gjengir ikke eventuelle interaktive elementer eller dekorasjoner.

**DisplayName** – brukervennlig navn for et felt i en datakilde.

* **[DataSourceInfo](../functions/function-datasourceinfo.md)**-funksjonen henter denne metadataen fra datakilden.
* Kontroller i kortet skal bruke **Parent.DisplayName** for å henvise til feltnavnet.

**Feil** – den brukervennlige feilmeldingen som vises for dette feltet når validering mislykkes.

* Denne egenskapen angis når **SubmitForm** påkalles.  
* Meldingen beskriver valideringsproblemer basert på datakildens metadata og ved kontroll av kortets **Obligatorisk**-egenskap.

**Obligatorisk** – om et kort, som redigerer feltet til en datakilde, må inneholde en verdi.

* **[DataSourceInfo](../functions/function-datasourceinfo.md)**-funksjonen henter den obligatoriske metadataen fra datakilden.
* Kontrollen i kortet skal bruke **Parent.Required** for å bestemme om kortfeltet er obligatorisk.

**Oppdater** – verdien som skrives tilbake i datakilden for et felt.

* Bruk formelen til denne egenskapen for å hente verdier fra redigeringskontrollene til kortet for å kunne skrive tilbake til datakilden. Angi for eksempel kortets **Oppdater**-egenskap til **Slider.Value** for å oppdatere datakilden med en verdi fra kortets glidebryter.

**[Bredde](properties-size-location.md)** – avstanden mellom kontrollens venstre og høyre kant.

**[WidthFit](properties-size-location.md)** – om en kontroll automatisk vokser horisontalt å fylle ut et tomt område i en beholderkontroll, som eksempelvis en **[Redigeringsskjema](control-form-detail.md)**-kontroll. Hvis flere kort har denne egenskapen er satt til **sann**, deles plassen mellom dem. Hvis du vil ha mer informasjon, kan du se [Å forstå oppsett for dataskjema](../working-with-form-layout.md).

## <a name="additional-properties"></a>Tilleggsegenskaper
**[BorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje.

**[BorderStyle](properties-color-border.md)** – om kontrollens kantlinje er satt til **Heltrukket**, **Stiplet**, **Prikket** eller **Ingen**.

**[BorderThickness](properties-color-border.md)** – tykkelsen til kontrollens kantlinje.

**[Fyll](properties-color-border.md)** – bakgrunnsfargen på kontrollen.

**[Høyde](properties-size-location.md)** – avstanden mellom kontrollens øvre og nedre kant.

**Gyldig** – om kontrollene **Kort** eller **[Redigeringsskjema](control-form-detail.md)** inneholder gyldige oppføringer, klare til å sendes til datakilden.

**[Synlig](properties-core.md)** – om kontrollen vises eller skjules.

**[X](properties-size-location.md)** – avstanden mellom kontrollens venstre kant og den venstre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder). Denne egenskapen angir kolonnen som vises i kortet for en **[Kort](control-card.md)**-kontroll i en beholder som har flere kolonner.

**[X](properties-size-location.md)** – avstanden mellom kontrollens øvre kant og den øvre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder). Denne egenskapen angir raden der kortet vises for en **[Kort](control-card.md)**-kontroll i en beholder som har flere rader.

## <a name="examples"></a>Eksempler
Se [Slik forstår du datakort](../working-with-cards.md) and [Slik forstår du oppsettet av dataskjemaer](../working-with-form-layout.md) for eksempler.


## <a name="accessibility-guidelines"></a>Retningslinjer for tilgjengelighet
### <a name="color-contrast"></a>Fargekontrast
Det må være tilstrekkelig fargekontrast mellom:
* **[Fyll](properties-color-border.md)** og alle underordnede kontroller. Hvis for eksempel et kort inneholder en **[etikett](control-text-box.md)** og etiketten har gjennomsiktig fyll, blir kortets **[fyll](properties-color-border.md)** den fungerende bakgrunnsfargen for etiketten. Det bør derfor være tilstrekkelig kontrast mellom kortets **[fyll](properties-color-border.md)** og etikettens **[farge](properties-color-border.md)**.

### <a name="screen-reader-support"></a>Kundestøtte for skjermlesere
* **DisplayName** må være tilstede.
